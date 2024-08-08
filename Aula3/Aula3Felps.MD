# Revisando redes...
Modelo cliente-servidor : o cliente realiza uma requisição e o servidor a retorna.

Modelo peer-to-peer : Não há servidores e clientes fixos.

Qual é mais eficiente? é relativo. Peer-to-peer tem menos tendência à perda de arquivos.

Torrent : Overlay , não é exatamente peer-to-peer por estar inserido na rede da internet (que funciona no modelo cliente-servidor)


## Tipos de redes
| **Tipo de Rede**           | **Função**                                                                 | **Exemplos**                                         | **Características**                                                                                                                                                              |
|----------------------------|----------------------------------------------------------------------------|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Rede de Acesso**          | Conecta usuários finais à rede principal da operadora ou à Internet        | ADSL, fibra óptica, 4G/5G, Wi-Fi                      | Parte mais próxima do usuário final; primeiro ponto de acesso à rede mais ampla; inclui tecnologias como DSL, FTTH, redes móveis e Wi-Fi.                                         |
| **Rede de Backbone**        | Fornece o principal caminho de comunicação entre diferentes redes          | Cabos submarinos, fibras ópticas de alta capacidade   | Enlaces de alta capacidade e baixa latência; conecta grandes centros de dados e redes de acesso; transporta dados em grandes distâncias.                                          |
| **Rede de Provedor de Conteúdo (CDN)** | Otimiza a entrega de conteúdo para os usuários finais                       | Redes de servidores distribuídos, como Akamai, Cloudflare | Composta por servidores espalhados geograficamente; armazena cópias de conteúdo popular; entrega conteúdo com baixa latência e melhora a experiência do usuário.                   |
| **Rede Empresarial**        | Conecta diferentes locais e departamentos dentro de uma empresa            | Redes locais (LAN), redes de área ampla (WAN), VPN    | Suporta comunicação interna; atende às necessidades de aplicativos empresariais e segurança de dados; inclui firewalls, VPNs, e soluções de rede em nuvem.                        |






## Tecnologias de rede: classificações baseadas no escopo da rede/distância:
| Nome da rede  | Tamanho/escopo |Tecnologias usadas|
| --------------| ---------------| -----------------|
| CAN's         | rede corporal  |(smartwatchs, por exemplo). Mencionada por alguns autores apenas.|
| PAN's         | 5 metros       | Tecnologias : Wifi,Ethernet|
| LAN's         |depende do tamanho, mas se trata de uma rede local. | Tecnologias : Wifi,Ethernet|
| MAN's         | regiões metropolitanas| tecnologias : Wifi, 4g,5g,fibra|
| WAN's         | Países/continentes | tecnologias : Fibra, satélite|
| Internet      | "Rede de redes"| Tecnologias : Todas |



## DNS - REGISTROS DE RECURSO
| **Tipo de Registro** | **Função**                                                | **Exemplo**                             | **Uso**                                                                                                      |
|----------------------|-----------------------------------------------------------|-----------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **Registro A**       | Associa um nome de domínio a um endereço IPv4             | `example.com -> 192.0.2.1`              | Tradução de nome de domínio para um endereço IP, permitindo a conexão a um servidor específico.              |
| **Registro NS**      | Define quais servidores DNS são autoritativos para o domínio | `example.com -> ns1.example.com, ns2.example.com` | Indica os servidores DNS responsáveis por manter as informações do domínio.                                   |
| **Registro CNAME**   | Cria um alias para outro nome de domínio                  | `www.example.com -> example.com`        | Facilita a manutenção de múltiplos nomes de domínio apontando para o mesmo endereço, utilizando um único registro A. |
| **Registro MX**      | Direciona o tráfego de e-mail para servidores específicos | `example.com -> mail.example.com (prioridade 10)` | Define quais servidores de e-mail devem receber mensagens para um domínio, com suporte a prioridades.        |


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
