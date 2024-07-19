1) Definindo o número de hosts por cada sub-rede.
2^n 
tira um da rede e do broadcast = 2^n - 2
62

2) definindo a máscara da subrede
140.25.0.0/*16* --> em vez de 16, pode ser 24/25

Os últimos 7 bits são utilizados para o host



## Exercício1 : Um bloco de endereços é concedido a uma pequena empresa. Sabemos que um dos endereços é 205.16.37.39/28.
### A) Qual é o primeiro endereço do bloco (endereço da sub-rede)?

PASSO 1: Identificar o endereço IP e a máscara de sub-rede:
```
- Endereço IP: 205.16.37.39
- Máscara de sub-rede: /28
```

PASSO 2: Converter o endereço IP  e máscara de subrede para binário:
```
Endereço IP 205.16.37.39 em binário: 11001101.00010000.00100101.00100111

Máscara de sub-rede /28 em binário: 11111111.11111111.11111111.11110000 (28 primeiros bits)
```

PASSO 3: Aplicando a máscara de sub-rede ao endereço IP (*Operação AND entre o ip e a máscara de sub-rede):
```
11001101.00010000.00100101.00100111 (Endereço IP)
              AND
11111111.11111111.11111111.11110000 (Máscara de sub-rede)
___________________________________
11001101.00010000.00100101.00100000 


Endereço de sub-rede em binário: 11001101.00010000.00100101.00100000
Em decimal: 205.16.37.32
```
PASSO 4: Adicionar 1 ao endereço de sub-rede para obter o primeiro endereço de host válido:
```
Endereço de sub-rede: 205.16.37.32
Primeiro endereço de host: 205.16.37.33
```


### Resposta:
Portanto, o primeiro endereço de host do bloco (endereço de sub-rede) é 205.16.37.33



___________________________________________________________________________________________________________________________

### B) Qual é o último endereço do bloco (endereço de broadcast)?

PASSO 1: Identificar o endereço IP e a máscara de sub-rede:
```
Endereço IP: 205.16.37.39
Máscara de sub-rede: /28 (ou 255.255.255.240 em decimal)
```

PASSO 2: Converter para binário:
```
Endereço IP 205.16.37.39 --> 11001101.00010000.00100101.00100111
Máscara de sub-rede /28 em binário: 11111111.11111111.11111111.11110000
```

PASSO 3: Calcular o endereço da sub-rede (operação AND entre o ip e a máscara de sub-rede):
```
Aplicando a máscara de sub-rede ao endereço IP:
11001101.00010000.00100101.00100111 (Endereço IP)
              AND
11111111.11111111.11111111.11110000 (Máscara de sub-rede)
_______________________________________________________________________________________________________________________
11001101.00010000.00100101.00100000 (Endereço final)
```

PASSO 4: Para encontrar o endereço de broadcast, todos os bits na parte do host devem ser definidos como 1.
O último endereço de host dentro da sub-rede é obtido ajustando-se os últimos 4 bits do endereço de sub-rede para 1.
```
Endereço de sub-rede em binário: 11001101.00010000.00100101.0010**0000**
Endereço de broadcast em binário:11001101.00010000.00100101.0010**1111**
```

PASSO 5: Converter o endereço de broadcast de volta para decimal:
```
11001101.00010000.00100101.00101111 --> 205.16.37.47
```
### Resposta:
Portanto, o endereço de broadcast da sub-rede com o endereço IP 205.16.37.39/28 é 205.16.37.47.

____________________________________________________________________________________________________________________

## Exercício 2 : Aplicando VLSM (Variable Length Subnet Masking) para a rede 140.25.0.0/16

#### A) Dividir a rede em 16 blocos iguais
- Rede inicial: 140.25.0.0/16
- Máscara padrão: 255.255.0.0 (ou /16 em CIDR)

Para dividir em 16 blocos iguais, precisamos de uma máscara /20 (porque 16 + 4 = 20).

#### Detalhamento dos blocos:

1. **Primeiro bloco:**
   - Máscara de sub-rede: /20
   - Endereço de rede: 140.25.0.0
   - Primeiro endereço de host: 140.25.0.1
   - Último endereço de host: 140.25.15.254
   - Endereço de broadcast: 140.25.15.255

2. **Segundo bloco:**
   - Endereço de rede: 140.25.16.0
   - ...

3. **Terceiro bloco:**
   - Endereço de rede: 140.25.32.0
   - ...

E assim por diante até o décimo sexto bloco.

#### 2. Dividir o bloco #1 em 32 blocos

- Focando no primeiro bloco (140.25.0.0/20) e dividindo em 32 sub-redes, usaremos uma máscara /25.

#### Detalhamento dos blocos dentro do bloco #1:

1. **Primeira sub-rede do bloco #1:**
   - Máscara de sub-rede: /25
   - Endereço de rede: 140.25.0.0
   - Primeiro endereço de host: 140.25.0.1
   - Último endereço de host: 140.25.0.126
   - Endereço de broadcast: 140.25.0.127

2. **Segunda sub-rede do bloco #1:**
   - Endereço de rede: 140.25.0.128
   - ...

3. **Terceira sub-rede do bloco #1:**
   - Endereço de rede: 140.25.1.0
   - ...

E assim por diante até a trigésima segunda sub-rede.

#### 3. Dividir o bloco #14 em 16 blocos iguais

- Agora, focamos no bloco #14, que corresponde a 140.25.13.0/20. Para dividir em 16 blocos iguais, usaremos uma máscara /24.

#### Detalhamento dos blocos dentro do bloco #14:

1. **Primeira sub-rede do bloco #14:**
   - Máscara de sub-rede: /24
   - Endereço de rede: 140.25.13.0
   - Primeiro endereço de host: 140.25.13.1
   - Último endereço de host: 140.25.13.254
   - Endereço de broadcast: 140.25.13.255

2. **Segunda sub-rede do bloco #14:**
   - Endereço de rede: 140.25.14.0
   - ...

3. **Terceira sub-rede do bloco #14:**
   - Endereço de rede: 140.25.15.0
   - ...

E assim por diante até a décima sexta sub-rede.

#### 4. Dividir o bloco #14-14 em 8 blocos iguais

- Finalmente, dentro do bloco #14, dividimos em 8 blocos iguais usando uma máscara /27.

#### Detalhamento dos blocos dentro do bloco #14-14:

1. **Primeira sub-rede do bloco #14-14:**
   - Máscara de sub-rede: /27
   - Endereço de rede: 140.25.13.0
   - Primeiro endereço de host: 140.25.13.1
   - Último endereço de host: 140.25.13.30
   - Endereço de broadcast: 140.25.13.31

2. **Segunda sub-rede do bloco #14-14:**
   - Endereço de rede: 140.25.13.32
   - ...

3. **Terceira sub-rede do bloco #14-14:**
   - Endereço de rede: 140.25.13.64
   - ...

E assim por diante até a oitava sub-rede.

