1) Definindo o número de hosts por cada sub-rede.
2^n 
tira um da rede e do broadcast = 2^n - 2
62

2) definindo a máscara da subrede
140.25.0.0/*16* --> em vez de 16, pode ser 24/25

Os últimos 7 bits são utilizados para o host



## Exercício: Um bloco de endereços é concedido a uma pequena empresa. Sabemos que um dos endereços é 205.16.37.39/28.
### A) Qual é o primeiro endereço do bloco (endereço da sub-rede)?

PASSO 1: Identificar o endereço IP e a máscara de sub-rede:
- Endereço IP: 205.16.37.39
- Máscara de sub-rede: /28

PASSO 2: Converter o endereço IP  e máscara de subrede para binário:
Endereço IP 205.16.37.39 em binário: 11001101.00010000.00100101.00100111

Máscara de sub-rede /28 em binário: 11111111.11111111.11111111.11110000 (28 primeiros bits)


PASSO 3: Aplicando a máscara de sub-rede ao endereço IP (*Operação AND entre o ip e a máscara de sub-rede):
11001101.00010000.00100101.00100111 (Endereço IP)
              AND
11111111.11111111.11111111.11110000 (Máscara de sub-rede)
___________________________________
11001101.00010000.00100101.00100000 

Endereço de sub-rede em binário: 11001101.00010000.00100101.00100000
Em decimal: 205.16.37.32

PASSO 4: Adicionar 1 ao endereço de sub-rede para obter o primeiro endereço de host válido:
Endereço de sub-rede: 205.16.37.32
Primeiro endereço de host: 205.16.37.33

### Resposta:
Portanto, o primeiro endereço de host do bloco (endereço de sub-rede) é 205.16.37.33





### B) Qual é o último endereço do bloco (endereço de broadcast)?

PASSO 1: Identificar o endereço IP e a máscara de sub-rede:
Endereço IP: 205.16.37.39
Máscara de sub-rede: /28 (ou 255.255.255.240 em decimal)

PASSO 2: Converter para binário:
Endereço IP 205.16.37.39 --> 11001101.00010000.00100101.00100111
Máscara de sub-rede /28 em binário: 11111111.11111111.11111111.11110000


PASSO 3: Calcular o endereço da sub-rede (operação AND entre o ip e a máscara de sub-rede):

Aplicando a máscara de sub-rede ao endereço IP:
11001101.00010000.00100101.00100111 (Endereço IP)
              AND
11111111.11111111.11111111.11110000 (Máscara de sub-rede)
____________________________________
11001101.00010000.00100101.00100000 (Endereço final)


PASSO 4: Para encontrar o endereço de broadcast, todos os bits na parte do host devem ser definidos como 1.
O último endereço de host dentro da sub-rede é obtido ajustando-se os últimos 4 bits do endereço de sub-rede para 1.
Endereço de sub-rede em binário: 11001101.00010000.00100101.0010**0000**
Endereço de broadcast em binário:11001101.00010000.00100101.0010**1111**

PASSO 5: Converter o endereço de broadcast de volta para decimal:
11001101.00010000.00100101.00101111 --> 205.16.37.47

### Resposta:
Portanto, o endereço de broadcast da sub-rede com o endereço IP 205.16.37.39/28 é 205.16.37.47.


