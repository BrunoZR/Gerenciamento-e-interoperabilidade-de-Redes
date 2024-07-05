## Arquitetura de aplicação de rede
* Camada de aplicação : Faz mais sentido a arquitetura cliente-servidor, com o servidor sempre com um endereço fixo. Imagina ter que fazer requisições à um servidor que muda constantemente.
* Caso UOL: Servidor de email e servidor web. Como reconhecem e encaminham o pacote para o lugar certo? Pelas PORTAS, informadas no pacote.


## A web e o HTTP:
* A página web é constituída de objetos. Objetos é um arquivo que pode se acessar com um único URL.
* Cada objeto tem seu próprio endereço.
* A maioria das páginas web tem um arquivo-base html (página inicial).
* o HTTP usa o TCP. Professor falou sobre TCP "Stateful" e "Stateless".

## Caches web:
### Servidor proxy : 
* armazena as requisições do cliente e um servidor web de origem. Quando um usuário repete uma requisição, em vez do servidor original ser consultado, o proxy já retorna a resposta. Isso reduz o congestionamento da rede.
* GET condicional.

### Correio eletrônico na internet :
* Agente de usuário : Permite que usuários leiam,respondam,encaminhem e salvem mensagens.
* Servidores de correio : Mensagem sai do remetente até o destinatário e chega na caixa postal
* Protocolo SMTP : Transfere as mensagens usando o protocolo TCP(porta 25) . Denominado como "push protocol"

## Protocolos de acesso ao correio : Browsers não tem. Possuem apenas HTTP. Os servidores precisam traduzir para HTTP.
* PO3 : Utiliza TCP e conexão porta 110  Três fases: autorização, transação e atualização
* IMAP

## DNS:
* Banco de dados dsitribuído hierarquicamente que traduz URL's para os respectivos endereços IP's.
* NICBR : responsável pelos domínios no brasil
* Revisar como funciona a consulta hierárquica
* Caso específico: Consulta recursiva, não performa tão bem quanto a hierárquica.
* Registro de recurso : Mapeamentos de nomes de hospedeiros para endereços IP. Cada resposta DNS arrega registros de recursos:
  Nome
  Valor : Tipo A , NS, CNAME, MX (ver nos slides cada um)
  Tipo
  TTL


## DHCP
* Permite que um hospedeiro receba um IP automaticamente. Usa IP's DINÂMICOS!
* Broadcasts: Revisar como acontece.

##NAT
* Tradução de IP's privados para públicos
