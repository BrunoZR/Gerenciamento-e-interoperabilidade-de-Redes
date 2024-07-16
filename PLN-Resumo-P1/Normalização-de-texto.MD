## Normalização de textos
### O que é?
- Conjunto de tarefas computacionais de pré-processamento de texto
- Padroniza os textos para uma forma mais conveniente de serem processados.

### O que é linguagem?
- Sistema de símbolos de um vocabulário que, quando colocados numa determinada ordem e expressos num determinado contexto, emitem um significado.

## Os 3 passos de processamento de texto

## 1) Tokenização: Quebra uma frase/texto em pedaços menores chamados tokens. 
- Cada token pode ser uma palavra só, ou duas palavras, etc. Depende do que é mais conveniente para ocasião.

- Os tokenizadores utilizam como base regras gramaticas/linguísticas para saber o que é uma palavra válida


- Token vs Types : Os tokens são todas as palavras/elementos que constituem a frase. Os types consideram a palavra uma vez só em casos de repetição.
Ex: eu sou eu. Tokens : "eu" , "sou" , "eu" Types: "eu" , "sou"


Algorítmos de tokenização | Funcionamento
------------------------- | --------------
Byte pair encoding| junta os pares de caracteres mais frequentes.
World piece| Par de símbolos que maximiza a probabilidade de ocorrência
Unigram| Usa como base uma grande quantia de caracteres/palavras/subplavras. Com o tempo essa base é reduzida, permanecendo apenas os símbolos mais relevantes.


- Subwords: Divide uma palavra desconhecida em pedaços conhecidos. Decompõe palavras compostas que não são frequentes em dois ou mais pedaços que aparecem com mais frequência. 
Ex: tokenization --> token + ization


- Stopwords: Para facilitar a análise de um texto, são removidas preposições,determinantes,conjunções, para facilitar o processamento e dar foco para as palavras que realmente possuem significado.


## 2) Lematização: Transforma palavras para o seu modo mais canônico possível.

- Verbos: Transforma os verbos para o infinitivo
- Substantivos e adjetivos: Transforma para o masculino singular.

- Exemplos:
 Bonitas, bonita, bonitos --> Bonito
 Ajudaremos, Ajude, Ajudamos --> Ajudar
 Tinhamos,Tive,Tenho --> Ter
 Gato,gatas,gatos --> Gato

Obs: A palavra canônica é dita como *lema* , e as suas derivadas são ditas como *lexemas*



## 3) Radicalização: Pega o radical da palavra. Bonito --> Bonit , jeito --> jeit , felicidade --> felic
Possíveis problemas:

- overstemming: Erro que tira mais letras que o devido.

- Understemming: Erro que tira menos letras que o devido.


