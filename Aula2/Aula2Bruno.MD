## Dominio de colisão: 
Quando uma máquina está transmitindo algum sinal, o domínio fica bloqueado, causando colisão. Um bom exemplo disso é a rede Wi-Fi, visto que quando uma máquina está transmitindo sinal em um canal, a outra não consegue (ficando bloqueada). Esse domínio é muito difícil de ocorrer em redes cabeadas. É para imaginar como se tivesse um fio que liga todos os computadores e se um envia sinal, os outros param.

## Comando Kathara Settings no CMD: 
Consegue ver as configurações para serem realizadas na máquina virtual. Com esse comando, é possível selecionar as imagens que você quer carregar, habilitar IPV4, entre outros.

## Kathará providencia três comandos:
* v-prefixed commands -> Para instalar uma máquina em tempo real, são utilizados comandos do tipo V, então com a rede rodando, adicionar um novo dispositivo.

* l-prefixed commands -> Utiliza-se esse comando para adicionar máquinas, ou seja, instancia o próprio cenário e sobe tudo de uma vez, e para isso, usam comandos do tipo L.

* global commands -> Funcionam tanto em tempo real quando em pré configuração, para capturar informações da máquina e da rede

## Comandos kathara:
* Todos os comandos devem ter prefixo kathara e se for instância atual de rede, deve utilizar o prefixo 'v'.

* kathara check -> Validar a rede e o docker que está sendo executado e fazer testes
* kathara vstart -n pc1 --eth 0:A -> Cria uma máquina na sua rede

* Se ocorrer o erro **"DockerPluginError"** Kathara has been left in an incosistent state” significa que a última instância do Kathara não foi finalizada corretamente, sendo necessário que execute o comando **"kathara wipe"**, para limpar a memória.


* **"kathara vclean -n [nomeDispositivo]"**: comando para apagar um elemento da rede. 

* Comando 0:A : significa que :A é o domínio de colisão e 0 porque é o primeiro dispositivo
:B por exemplo seria o domínio de colisão B.





## Anotações gerais válidas... 📗


Sempre que ser criado um container (PC1, PC2, PC3), terá disponível uma pasta /hosthome que terá todos os arquivos. Para acessar as informações compartilhadas no dispositivo host, precisa acessar a pasta /shared.

Para acessar o arquivo de log de uma máquina, é preciso habilitar a pasta do host, copiar o arquivo do PC1 via linha de comando para a pasta do host via /shared.
/shared -> Acessar pelo host
/hosthome -> Acessar pelas máquinas

Agora, para executar um laboratório exemplo completo, utilizamos os comandos do tipo L, visto que iremos realizar toda a configuração previa da máquina e depois subir toda a rede de uma vez.

Interface é a placa de rede do dispositivo:
r1[0]="A"
r1[1]="B"
r1[image]="kathara/base"

Aqui, estamos definindo a interface 0 do roteador no domínio de colisão A, depois estamos definindo a interface 1 do roteador no domínio de colisão B, e por fim, definindo a imagem do dispositivo criado como a imagem base.

Quando tentamos acessar a interface 0 do roteador 1 através da interface 0 do pc1, conseguimos com sucesso. Contudo, quando tentamos acessar a interface 1 do roteador 1 através da interface 0 do pc1, não conseguimos.
Porque não é possível acessar interfaces em diferentes domínios?

É uma questão de configuração. O computador foi configurado apenas na rede 195 e não consegue enviar pacote de dados para outras redes. Precisa adicionar um comando para que, caso ele não consiga alcançar a rede, ele manda para o roteador 1 que ele provavelmente vai saber o que fazer com isso. Basicamente, o que estamos criando é uma tabela de rotas estáticas.
Tabela rotas estáticas -> Qualquer pacote destinado a algum ip específico, deve ser direcionado para outros dispositivo (no nosso caso, uma tabela de rota estática entre o pc1 e o r1.
O r1 está na rede 195.11.14 e 100.0.0.9, então quando o pc1 enviou para a rede 100.0.0.9, ele não sabe o que fazer, então envia para o roteador1, que provavelmente sabe. Como o roteador 1 está conectado na rede 100.0.0.9, ele consegue receber o pacote de dados e transmitir para essa nova rede, constando como ativa.

O pc1 não consegue se comunicar com a interface de rede do r2. Para resolver isso, utiliza o tcpdump -tenni eth1 no roteador 2, para ele se conectar com o pc. Com esse comando, você consegue capturar e analisar o trafego de rede que passa por uma instância de rede em específico, nesse caso, o eth1.

Contudo, o PC1 conseguiu enviar os dados, o R2 recebeu, mas não teve pacote de resposta, então deu falha. Isso ocorre porque o R2 só tem rota para a rede 100.0.0.9 e 200, então é necessário configurar uma rota para alguma outra rede. Nesse caso, utilizamos o comando "ip route add 195.11.14.0/24 via 100.0.0.9 dev eth1". Nesse caso estamos dizendo que a rede "195.11.14.0/24" está acessível através da rede "100.0.0.9" e utilizando a interface "eth1", conforme o desenho esquemático.

O TCDUMP, em resumo, é um sniffer de rede, ou seja, ele recebe os pacotes mas não injeta eles. Em reusmo, ele é passivo na rede, captura todos os pacotes e consegue utilizá-los, mas se não está na rede, ele não dá retorno.

