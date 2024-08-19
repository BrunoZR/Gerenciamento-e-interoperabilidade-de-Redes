**Redes de Computadores**

- Rede de Computadores: um conjunto de computadores autônomos interconectados por uma unica tecnologia.
- Interconectados: dois computadores estão interconectados quando podem trocar informações

- Modelo cliente-servidor: Um servidor fixo recebendo requisições dos dispositivos.
- Modelo Peer-to-Peer: Não há um servidor fixo. Ora um dispositivo pode ser quem requisita a informação, ora o que fornece a informação.


## Tipos de redes
| **Tipo de Rede**           | **Função**                                                                 | **Exemplos**                                         | **Características**                                                                                                                                                              |
|----------------------------|----------------------------------------------------------------------------|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Rede de Acesso**          | Conecta usuários finais à rede principal da operadora ou à Internet        | ADSL, fibra óptica, 4G/5G, Wi-Fi                      | Parte mais próxima do usuário final; primeiro ponto de acesso à rede mais ampla; inclui tecnologias como DSL, FTTH, redes móveis e Wi-Fi.                                         |
| **Rede de Backbone**        | Fornece o principal caminho de comunicação entre diferentes redes          | Cabos submarinos, fibras ópticas de alta capacidade   | Enlaces de alta capacidade e baixa latência; conecta grandes centros de dados e redes de acesso; transporta dados em grandes distâncias.                                          |
| **Rede de Provedor de Conteúdo (CDN)** | Otimiza a entrega de conteúdo para os usuários finais                       | Redes de servidores distribuídos, como Akamai, Cloudflare | Composta por servidores espalhados geograficamente; armazena cópias de conteúdo popular; entrega conteúdo com baixa latência e melhora a experiência do usuário.                   |
| **Rede Empresarial**        | Conecta diferentes locais e departamentos dentro de uma empresa            | Redes locais (LAN), redes de área ampla (WAN), VPN    | Suporta comunicação interna; atende às necessidades de aplicativos empresariais e segurança de dados; inclui firewalls, VPNs, e soluções de rede em nuvem.                        |



##Tecnologias de redes
## Tecnologias de rede: classificações baseadas no escopo da rede/distância:
| Nome da rede  | Tamanho/escopo |Tecnologias usadas|
| --------------| ---------------| -----------------|
| CAN's         | rede corporal  |(smartwatchs, por exemplo). Mencionada por alguns autores apenas.|
| PAN's         | 5 metros       | Tecnologias : Wifi,Ethernet|
| LAN's         |depende do tamanho, mas se trata de uma rede local. | Tecnologias : Wifi,Ethernet|
| MAN's         | regiões metropolitanas| tecnologias : Wifi, 4g,5g,fibra|
| WAN's         | Países/continentes | tecnologias : Fibra, satélite|
| Internet      | "Rede de redes"| Tecnologias : Todas |


## Duas grandes pilhas de protocolos : OSI VS TCP/IP
- TCP/IP : Aplicação, Transporte , Rede , Enlace  
- OSI:Aplicação, Apresentação, Sessão, Transporte, Redes, Enlace(Link), Física

- A informação na internet é enviada por pacotes, um conjunto de bits organizados lidos pelos dispositivos.
- Os pacotes passam primeiro pelo processo de encapsulamento. Existe muito mais do que a informação em si. Nele, estão informações sobre o protocolo de aplicação/transporte/redes/link
- Ao chegar no destino, os pacotes passam pelo processo de desencapsulamento. Eles leêm as informações do link/redes/transporte/aplicação, e depois chegam na informação.


***PROTOCOLOS PRINCIPAIS***:
- Aplicação : HTTP , SMTP , RTP , DNS
- Transporte: TCP , UDP
- Redes/internet : IP e ICMP (existem protocolos internos que devem ser estudados)
- Enlace (Link)  : DSL, SONET, 802.11(wifi) , Ethernet (Existem protocolos internos que devem ser vistos, principalmente no Ethernet)

***HIERARQUIA ISP (Internet Service Provider)***: 
ISP Tier 1
- Os ISPs que pertencem a esse nível hierárquico – que é o mais alto – são chamados de provedores de backbone globais, ou também são conhecidos como Peers.
- Eles têm uma infraestrutura completa e robusta que atua como backbone. Isto é, têm redes de conexão de fibra óptica que cruzam continentes e passam pelo interior dos oceanos, fazendo a conexão dos data centers de maior importância no mundo.
- Por terem esse tipo de atuação, de modo geral os ISPs nível 1 não atendem o cliente final ou empresas de pequeno porte, mas sim provedores nível 2.
- Além disso, os provedores de internet que pertencem a essa hierarquia não contratam serviços de outras operadoras de rede, como é comum com os demais provedores. Afinal, eles têm alta capacidade de conexão, bem como redes seguras e rápidas. Assim, são mais autossuficientes em termos de estrutura.

ISP Tier 2
- Os provedores que estão no nível Tier 2 são nomeados como regionais, pois têm uma atuação voltada a uma área ou região específica. 
- Em geral, costumam trabalhar em um estado ou em um grupo de estados. Alguns até ampliam o foco de atuação e acabam trabalhando em um país todo

ISP Tier 3
- Por fim, um ISP nível 3 é o provedor de internet local. Ele tem atuação focada em uma determinada localidade, como uma pequena cidade ou um bairro, e é indispensável para possibilitar que os usuários locais tenham acesso à internet.
- Afinal, muitas vezes os provedores regionais não têm cobertura local, tampouco os provedores nível 1 que estão direcionados a outro tipo de público.
- Portanto, os ISPs de nível 3 têm uma contribuição indiscutível no mercado de provedores, pois possibilitam que a conexão de internet seja mais difundida e levada a locais onde não há tanta oferta, como cidades de pequeno porte do interior.
