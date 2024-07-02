# Revisando redes...
Modelo cliente-servidor : o cliente realiza uma requisição e o servidor a retorna.

Modelo peer-to-peer : Não há servidores e clientes fixos.

Qual é mais eficiente? é relativo. Peer-to-peer tem menos tendência à perda de arquivos.

Torrent : Overlay , não é exatamente peer-to-peer por estar inserido na rede da internet (que funciona no modelo cliente-servidor)


## Tipos de redes
* Redes de acesso : Banda larga (conexão a cabo) , sem fio (wifi) , móveis (3g~4g~5g)
* Redes de provedor de conteúdo : redes distribuídas próximas ao usuário para facilitar a circulação de arquivos muito requisitados, comos serviços streaming. Otimiza o desempenho da rede
* Rede backbone : Intermédio/esquema de ligações centrais de um sistema de redes mais amplo, tipicamente de elevado desempenho e com dimensões continentais.
* Rede empresarial 


## Tecnologias de rede: classificações baseadas no escopo da rede/distância:
| Nome da rede  | Tamanho/escopo |Tecnologias usadas|
| --------------| ---------------| -----------------|
| CAN's         | rede corporal  |(smartwatchs, por exemplo). Mencionada por alguns autores apenas.|
| PAN's         | 5 metros       | Tecnologias : Wifi,Ethernet|
| LAN's         |depende do tamanho, mas se trata de uma rede local. | Tecnologias : Wifi,Ethernet|
| MAN's         | regiões metropolitanas| tecnologias : Wifi, 4g,5g,fibra|
| WAN's         | Países/continentes | tecnologias : Fibra, satélite|
| Internet      | "Rede de redes"| Tecnologias : Todas |


## Protocolos de rede : Modelo OSI e TCP/IP
* Aplicação : HTTP , SMTP , RTP , DNS
* Transporte : TCP , UDP (Lembrar que um é orientado à conexão e o outro não. Um se preocupa com a ordem dos pacotes e o outro não, etc).
* Internet : IP , ICMP
* Enlace/link : DSL, SONET , 802.11(Wifi) , ETHERNET

## Construindo uma rede simples no Kathará
Inicialize o Kathará -- > Disco local C --> VMBOX
Na pasta do kathará, crie uma pasta "Rede_simples"
Siga os passos do slide do professor.

## Observando os protocolos de uma rede com o wireshark!
* [Download da rede](https://github.com/KatharaFramework/Kathara-Labs/tree/main/main-labs/basic-topics/basic-ipv4)
Em termos de gerenciamento... 
- Ping para testar a conectividade é uma das formas de analisar se a falha de uma comunicação está na rede ou no servidor.
- Uso do wireshark para observar quais pacotes estão circulando
