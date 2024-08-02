O IPV6 vem de uma necessidade : o esgotamento do ipv4.
- Instituições padronizadoras da internet : IETF , ITUT, etc...
- de 32 bits vai para 128

Como lidar com ipv4 e ipv6 , ambos espalhados na internet?

1) Conversão de bases numéricas: Binário/decimal/hexadecimal


CAFE --> 12 10 16 15 = 1100 1010 1111 1100


** PADRÃO IPV8 :
- Feito em 1998 - Definido pela RFC 24600
- Não é necessário alterar a placa de rede, pois tanto o ipv6 quanto o ipv4 são softwares


Cabeçalho IPV4:
- Primeira coisa a ser conferida nos cabeçalhos da camanda de transporte é a versão 
- O tamanho do cabeçalho é um problema, pois ele varia devido às opções de complemento
- O tipo de serviço : Melhor esforço. Não há garantia da entrega de pacotes.
- Tamanho total: A aplicação pode variar em tamanho, e isso pode variar o tamanho total. Há ocasiões em que há a fragmentação dos pacotes, eles são quebrados em outros.
- Protocolo : Indica se é UDP ou TCP
- Soma de verificação: Ele não corrige o pacote, apenas indica se o pacote está integro ou não. Cada vez que passa por um roteador, o TTL é alterado e o roteador recalcula essa soma de verificação, sendo uma função custosa.

Cabeçalho IPV6: Fragmentação apenas na origem e no destino, apesar de não estar incluso no pacote
- Mobilidade do IPV6: Quando um dispositivo troca de rede, existe um dispositivo agente que comunica o servidor que houve essa alteração ou o agente continua encaminhando os pacotes.

- Endereçamento do IPV6
Um ip é formado por 128 bits. Os enbdereços são divididos em oito grupos de 16 bits, em que cada dígito corresponde à 4 bits.

2001:0db8:0100:000a:0000:00bc:abcd:0d0b

fe80:0000:a299:9bff:fe18:50d1

*DIFERENÇAS NOS TIPOS DE ENDEREÇOS DEFINIDOS EM IPV6 E IPV4: ESTUDAR!
