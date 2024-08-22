*CAMADA DE REDE*
- Transportar pacotes de um hospedeiro remetente para um hospedeiro destinatário.
- Identifica os hospedeiros com um endereço lógico (IP).
- Tabela de repasse: quando um pacote chega ao enlace de entrada de um roteador, este deve conduzi-lo até o enlace de saída apropriado
- Roteamento: a camada de rede deve determinar a rota ou o caminho tomado pelos pacotes ao fluirem de um remetente a um destinatário

- RIP, OSPF, BGP: protocolos de roteamento que calculam as tabelas de repasse e que são usadas para transmitir pacotes pela rede
- ICMP: protocolo de comunicaçãao de erro e de informações da Internet


- Classless Interdomain Routing (CIDR): Generaliza a noção de endereçamento de sub-rede. O endereço IP de 32 bits é dividido em duas partes: a.b.c.d/x, onde x é o prefixo de rede, que indica o os "n" bits que representam o prefixo daquela rede.
Exercício: Qual é o equivalente em notação ponto decimal das seguintes máscaras sub-redes:

  - /24 -> 11111111.11111111.11111111.00000000 -> 11111111 = 2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0 = 1 + 2 + 4 + 8 + 16 + 32 + 64 + 128 = 255 -- > Portanto : 255.255.255.0
  
  - /27  --> 11111111.11111111.11111111.111 00000 --> 11100000 --> 2^7+2^6+2^5 = 32 + 64 + 128 = 224 --> Portanto: 255.255.255.224
  - /16 --> 11111111.11111111.00000000.00000000 --> 255.255.0.0
  - /30 --> 11111111.11111111.11111111.11111100 --> 11111100 = 2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 = 128 + 64 + 32 + 16 + 8 + 4 = 252 --> 255.255.255.252

- Antes da adoção do CIDR, os tamanhos das parcelas de um endereço IP estavam limitados a 8, 16 ou 24 bits, um esquema de endereçamento conhecido como endereçamento com classes (Classfull)
  - CLASSE A:
    - Prefixo de rede : /8
    - Máximo de redes: 2^8 - 2 (0.0.0.0: Este endereço é reservado como endereço de rede padrão | 27.0.0.0: Este endereço é reservado para loopback , então subtraí 2).
    - Número de hosts : 2^24 - 2 ( O primeiro endereço é reservado para identificar a rede| Endereço de Broadcast: O último endereço é reservado para broadcast).


  - CLASSE B:
    - Prefixo de rede: /16
    - Máximo de redes: 2^16 - 2 = 65534
    - Número de hosts: 2^16 - 2 = 65534

  - CLASSE C:
    -Prefixo de rede: /24
    - Máximo de redes: 2^24 - 2 = 16777214
    - Número de hosts: 2^8 - 2 = 254

  - CLASSE D: Multicast

  - CLASSE E: Uso experimental apenas.

  - Faixa de IP de cada classe ( lembre sempre que o primeiro e o último endereço da faixa A são reservados para endereço/gateway padrão e o outro para broadcast, respectivamente).
    | Classe | Prefixo de Rede | Primeiro Octeto | Bits Iniciais      | Faixa IP              | Uso Principal                     |
    |--------|-----------------|-----------------|--------------------|-----------------------|--------------------------------   |
    | A      | 8 bits          | 0-127           | 0                  | 0.x.x.x a 126.x.x.x   | Redes grandes (milhões de hosts)  |
    | B      | 16 bits         | 128-191         | 10                 | 128.x.x.x a 191.x.x.x | Redes médias                      |
    | C      | 24 bits         | 192-223         | 110                | 192.x.x.x a 223.x.x.x | Redes pequenas                    |
    | D      | Multicast       | 224-239         | 1110               | 224.x.x.x a 239.x.x.x | Multicast                         |
    | E      | Reservado       | 240-255         | 1111               | 240.x.x.x a 255.x.x.x | Reservado                         |





    


