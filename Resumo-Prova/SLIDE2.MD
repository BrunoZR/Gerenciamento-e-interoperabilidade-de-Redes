**ARQUITETURAS DE APLICAÇÃO DE REDE**
- É projetada pelo programador e determina como a aplicacão é organizada nos vários sistemas finais.

**ARQUITETURA DE REDE **
- Modelo cliente servidor: Hospedeiro fixo chamado servidor que atende requisições de outros hospedeiros. Muitas vezes um servidor precisa de auxílio para atender todas as requisições (Data center, Servidor de distribuição de conteúdo)
- Modelo peer-to-peer : Como os hospedeiros podem assumir o comportamento de servidor e depois cliente, tem uma alta escalabilidade. 

**WEB E HTTP**
- Protocolo de aplicação
- Uma página Web é constituída de objetos.
- Um objeto é apenas um arquivo que se pode acessar com um único URL
- Camada de transporte: USA O TCP
- Servidor Proxy: o cache WEB. Um intermediário que atua entre um cliente e um servidor. O cache Web salva dentro dele cópias de objetos recentemente requisitados, como a estrutura da página (imagens,formatação), consulta DNS, etc.
  - Reduz o tempo de resposta da requisição do cliente
  - Diminui o tráfego da internet
  - Utiliza GET CONDITIONAL , mecanismo que garante que apenas o conteúdo atualizado seja transferido entre o cliente (ou proxy) e o servidor. Isso economiza largura de banda e acelera o acesso, especialmente quando combinado com o cache.

** CORREIO ELETRÔNICO (EMAIL)*
- Camada de aplicação
- Estruturado por:
    - Agentes de usuário: são os que viabilizam as ações do usuário, como ler, escrever e salvar mensagens. 
    - Agentes de correio: São os que captam a mensagem, viabilizam a interação de um correio com o outro para chegar na caixa postal correta do usuário ou manter ela em fila.
- SMTP : PROTOCOLO DE USO PELOS/PARA CORREIOS
  - Protocolo de comunicação entre/para OS CORREIOS. 
  - Utiliza o protocolo UDP na camada de transporte.
  - Conexão feita na porta 25
  - Push protocol: Um protocolo de envio de informações -o servidor de correio remetente envia o arquivo para o servidor de correio destinatário

- PROTOCOLOS DE ACESSO AO CORREIO:
  - POP3 (RFC 1939) : Autorização com usuário e senha , operação dentro do email e atualização a partir das operações feitas. UTILIZA TCP, conexão na porta 110
  - IMAP (RFC 3501): Associa cada mensagem a uma pasta, permite criar uma pasta e transferir mensagem entre elas
  - HTTP : Acesso pelo navegador.


- DNS : É um banco de dados distribuído executado em uma hierarquia de servidores de DNS, e um protocolo de camada de aplicação que permite que hospedeiros consultem o banco de dados distribuído.
    - Utiliza UDP, sua conexão é na porta 53
    - Além da tradução dos nomes dos hospedeiros para o IP, também realiza:
        - Aliasing(Apelidos): Um hospedeiro com nome complicado pode ter "apelidos" (nomes alternativos). Pode ser para sites quanto para emails(um email com diversos endereços para melhor organização).
        - Distribuição de carga: O DNS também distribui as cargas de servidores web replicados.
        - Cache DNS: Usa muito o cache citado, para evitar tráfego desnecessário na internet.
    - Mensagens DNS:
      - Registro de Recurso (RR) : Fornecem mapeamentos de nomes de hospedeiros para endereços IP. 
        - É uma tupla de quatro elementos: Name,Value,Type e TTL . Name e Value dependem do Type , TTL é o tempo de vida.
          - TYPE=A : Mapeamento do nome do hospedeiro e seu endereço IP. Name é o site dele , Value é o IP. Ex:( relay1.bar.foo.com, 154.37.93.126, A).
          - TYPE=NS: Encaminhar consultas DNS ao longo da cadeia de consultas. Name é um domínio , Value é um servidor DNS autoritativo. Ex: (org.com, dns.org.com, NS).
          - TYPE=CNAME: Fornece o nome canônico relativo à um apelido. Name é o apelido e value é o nome canônico. Ex: (foo.com , relay1.bar.foo.com, CNAME)
          - TYPE=MX : permitem que os nomes de servidores de correio tenham apelidos simples. Name é o apelido do hospedeiro e Value o nome canônico de um servidor de correio (ex. foo.com, mail.bar.foo.com, MX).

- DHCP(Dynamic Host Configuration Protocol) : Permite que um hospedeiro obtenha um endereço IP de forma automática
  Possuí quatro etapas:
    - 1: Descoberta do servidor DHCP
    - 2: Oferta dos servidores DHCP
    - 3: Solicitação DHCP
    - 4: DHCP ACK

- NAT (Network Adress Translation): Responsável pelo intermédio da rede privada com a internet.
- IP'S PRIVADOS: três porções do espaço de endereço IP reservado pelo (RFC 1918) para uma rede privada:
de 10.0.0.0 a 10.255.255.255 (10.0.0.0/8)
de 172.16.0.0 a 172.31.255.255 (172.16.0.0/12)
de 192.168.0.0 a 192.168.255.255 (192.168.0.0/16)

- Tradução de endereços NAT:
  - UPnP (Universal Plug and Play) :  Permite que dispositivos dentro de uma rede se descubram automaticamente e estabeleçam comunicação entre si sem a necessidade de configuração manual. 
    - Um hospedeiro novo se conecta à rede e toda sua configuração é feita automaticamente dentro da rede.
    -Quando hospedeiro externo envia um pacote SYN TCP, o NAT alterar o endereço IP destinatário e o número da porta no pacote para e encaminha o pacote pelo NAT.

-ICMP : Protocolo de comunicação das informações na camada de rede, principalmente comunicação de erros.
(VER SLIDES DE CADA CÓDIGO)

