## Redes de computadores : Protocolos e camadas
* É um conjunto de computadores autônomos interconectados por uma única tecnologia (entende-se que interconectar é quando ambos os computadores podem trocar informação, seja essa tecnologia por cabo ou por rede wireless.

* Internet não é uma rede de computadores seguindo essa definição, mas sim, um conjunto de várias redes.

## Existem dois modelos de redes de computadores:
* Modelo Cliente-Servidor
- Existem dois computadores e um servidor fixo, sendo todo eles ligados pela rede. Alguns exemplos são aplicações web. Whats app por exemplo é um modelo cliente servidor (por ter um servidor central que centraliza as informações), contudo, a comunicação é feita de cliente para cliente.
- Para acessar um servidor, é necessário utilizar uma URL, transformando o IP do servidor em uma rota de acesso público, utilizando o protocolo DNS.

* Modelo Peer-to-Peer
- Nesse modelo, não existem clientes e servidores fixos, então a comunicação é realizada diretamente entre dois dispositivos, sem intermédio de um servidor. Apesar de ser peer-to-peer entre os usuários, normalmente ele está sob uma infra-estrutura de servidor. No momento que você está pegando os dados, você age como cliente e o outro como servidor, mas isso depende do referencial do fluxo de dados.
- O gerenciamento e os problemas de segurança para cada modelo são diferentes, além da efetividade deles. O modelo peer-to-peer é um sistema distribuído, então tem o arquivo mais disponível em diferentes pontos e possui algumas vantagens do que o modelo de servidor, que é centralizado e pode possibilitar um acesso mais rápido da informação, mas com menos disponibilidade, porque se der pau no servidor, acaba tudo.

## Tipos de redes:

* Rede de acesso:
- Banda larga -> Rede conectada via cabo oferecida por um provedor (cabo fibra, principalmente),
- Sem fio -> Acessar internet totalmente sem fio, com sinal de rádio frequência ou satélite (starlink))
- Redes móveis -> Pacote de dados do celular, com 4G ou 5G.

* Rede de provedor de conteúdo:
- É utilizado uma rede de distrbuição CDN, na qual o grupo de acesso está mais "próximo" do conteúdo e otimiza o tempo de carregamento, baixando menos dados.

* Rede backbone:
- Pode ser entendida como o core da internet, visto que toda a informação passada entre todos os provedores é feita através dessa forma. Em geral, utiliza-se fibra para constuir uma rede backbone.

* Rede empreserial:
- Consiste em toda forma de rede mínima, seja ela corporativa, faculdade, entre outras. No contexto geral, ela pode ser conectada totalmente via cabo ou através de rede wi-fi.

## Tecnologia das redes:
* BAN (Body Area Network) -> Alguns pequenos pesquisadores consideram uma nova rede menor do que a pessoal, que é a corporal, que são os relógios e fones de ouvidos conectados na pessoa.
* PANs (Personal Area Networks) -> Área de uso pessoal, utilizado principalmente rede Wi-Fi e cabo ethernet, consiste em uma casa ou uma sala.
* LAN (Local Area Network) -> Chega até cerca de 12km, que consiste na rede de uma faculdade, empresa, entre outras. Utilizando um modelo de rede específico.
* MAN (Metropolitan Area Network) -> Área metropolitana, para realizar a conversa entre um cliente e o servidor na escala municipal, conectado principalmente com rede 5G e cabo de fibra.
* WAN (Wide Area Network) -> É o maior tamanho de área que uma rede pode existir, consistindo basicamente em comunicação sem fio, para que seja realizada comunicação, por exemplo, entre uma empresa brasileira e sua filial no Canada.
* Internet -> É a maior rede existente, utilizando diferentes tecnologias.

## Existem dois padrões de internet:
* ISO -> Modelo de referência da internet, para quem fosse projetar um protocolo, soubesse a sua função e quais serviços ele irá fornecer. Contudo, esse modelo não roda diretamente na internet
As 7 camadas são:
Application
Presentation
Ssession
Transport
Network
Data link
Physical

* TCP/IP -> Esse modelo é o que é mais executado hoje na internet, apesar de não existir algumas camadas.
Application
Transport
Internet
Link
Não possui -> Presentation, Session e Physical, apesar de serem cruciais para o funcionamento da internet.

* No modelo da internet, uma mensagem criada na camada de aplicação precisará percorrer por todo o resto do pilar (transporte, principalmente), comunicando-se por modo físico para a outra máquina de destino e indo subindo novamente até a aplicação. É de cima para baixo no remetente e de baixo para cima no destino.

## Protocolos de comunicação:
* Application -> HTTP (Comunicação da internet e de aplicações web), SMTP (E-mail), RTP e DNS
* Transport -> TCP e UDP (Enviar dados para outro usuário)
* Internet -> IP e ICMD
* Link -> DSL, SONET, 802.11, Ethernet
* Física -> A camada física não possui nenhum protocolo, pois ligar dois computadores entre fio é basicamente fazer uma conexão, mas é necessário as camadas superior para poder interpretar os dados que serão trazidos até o computador.

## Comandos kathara:
* kathara lstart -> Inicia o lab
* ip address add 195.11.14.5/24 dev eth0 -> Define o ip e a interface de rede
* ip route add default via 200.1.1.1 -> Define qual a rota que você manda o arquivo se não souber o que fazer com ele
* ip link set dev eth0 address 00:00:00:00:00:02 -> Define o mac adress do computador´

## Wireshark:
* Software para analisar o trafego de rede e os protocolos que estão contidos nos pacotes que estão sendo passados pela máquina. Através dele, é possível entender a camada que está dando o erro.
