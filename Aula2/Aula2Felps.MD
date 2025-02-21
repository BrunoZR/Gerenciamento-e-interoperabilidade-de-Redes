# O kathará: um emulador com ferramentas de rede! 💻
Data : 28/06

Vale lembrar que o arquivo é um resumo topificado da aula do professor. Para melhor compreensão, pode ser interessante entender melhor o que é o Kathará e os conceitos de docker/containers:
* https://wiki.foz.ifpr.edu.br/wiki/index.php/Kathara
* https://www.youtube.com/watch?v=Xb9e4XY1ix8&ab_channel=SimplificandoTI



### Docker vs conteiners: 
* Docker é uma virtualização da virtualização. O conteiner é uma virtualização.
* O Kathará é baseado no Docker



### Colisões virtuais 💥
* Podem ocorrer pelo fato da conexão virtual ser análoga à um "fio que une todos os computadores".
* Para lidar com isso, são utilizados domínios de colisões, que evita que certos computadores interfiram um no outro. Apesar disso, todos são capazes de se comunicar entre si.










## COMANDOS DO KATHARA: 🚩

### Comandos locais e globais
* V : criar dispositivos em tempo real
* L : simula uma criação, sendo mais rápido e em tempo real

#### kathara check :
* Confere a versão do kathará.

#### kathara vstart -n pc1 --eth 0:A :
* Criando um computador pc1. Não pertencem à máquina virtual, mas sim ao conteiner
* Lógica do comando : kathara v start -n "nome do pc" --interface de rede      número da interface/domínio de colisão

#### pc1[0] = A : 
* Computador "pc1" na interface "1" no domínio de colisão "A"








## Outros tópicos sobre o Kathará mencionados em aula...
* O kathará usa diretórios no modelo de árvore

* Cuidado com pastas compartilhadas em um conteiner. O compartilhamento é geral, e o apagamento também

* /share referencia dentro do ubuntu uma pasta de compartilhamento
* /hosthome é o uma pasta dentro da máquina virtual, sendo um repositório para depositar os arquivos que desejam ser compartilhados

* Comando startup : definição prévia das configurações da interface de rede. Salva uma rede criada, com os pc's com seus respectivos ip's, bem como roteadores e switchs.

* Mv "Destino local" "Destino desejado"






## Importando uma rede já feita!
* 1-Baixe um arquivo
* 2-Abra o terminal dentro da pasta com as configurações já feitas
* 3-Execute o comando "kathara lstart".

Com isso, a seguinte rede foi importada:
![imagem pro bruno](https://github.com/fultramari/Gerenciamento-e-interoperabilidade-de-Redes/assets/174112183/fe1fcaa4-e820-4965-b587-d4bd767127f7)




## EXECUTANDO COMANDOS PARA ENTENDER A REDE A PARTIR DE UM ELEMENTO DELA
* comando ping: ping "ip destino" --> Confere a conectividade com o destino

* ip route --> dá as rotas

* ip route add default via 195.11.14.1 dev eth0 : 
Quando o computador desconhece o elemento de destino, o comando diz para ser encaminhado ao ip informado ( no caso, o ip de R1),
que sabe a localização desse elemento que está conectado em outra rede (pc 2 , por exemplo).


* tcpdump : Captura pacotes de determinado ponto da rede e permite análise. É um sniffer.

* Adicionar uma rota ao r2 para ele encaminhar a resposta para algum elemento da rede 1:
ip route add 195.11.14.0/24 via 100.0.0.9 dev eth1


