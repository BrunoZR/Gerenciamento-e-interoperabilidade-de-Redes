# Como fazer o computador entender mensagens, em específico textos?
Apesar de serem enviados textos, áudios e imagens, o computador interpreta apenas valores matemáticos binários.
Existem diversos métodos para cada tipo de informação. O escopo de análise será entender a *representação de texto* .
No geral, são utilizadas *representações vetoriais*, um espaço algébrico interessante e conveniente.

Para explicarmos cada modelo, considere os seguintes documentos:
```
D1 | cachorro morde homem
D2 | homem morde cachorro
D3 | cachorro come carne
D4 | homem come comida
```
## Modelo 1 : One-Hot encoding
- Cada palavra recebe um ID único:
1 - cachorro
2 - morde
3 - homem
4 - come
5 - carne
6 - comida

- Assim, cada vetor terá 6 digitos, basta colocar 1 na posição correspondente ao ID , e 0 nas restantes:

Palavra  | Vetor              
---------|--------------------
cachorro | [1, 0, 0, 0, 0, 0] 
morde    | [0, 1, 0, 0, 0, 0] 
homem    | [0, 0, 1, 0, 0, 0] 
come     | [0, 0, 0, 1, 0, 0] 
carne    | [0, 0, 0, 0, 1, 0] 
comida   | [0, 0, 0, 0, 0, 1] 


Desse modo, para representar a frase "cachorro morde homem":
[1, 0, 0, 0, 0, 0] [0, 1, 0, 0, 0, 0] [0, 0, 1, 0, 0, 0]


## Modelo 2: Bag of words
- Cada palavra recebe um ID único (igual no modelo 1) : 
1 - cachorro
2 - morde
3 - homem
4 - come
5 - carne
6 - comida



Documento             | Vetor              
----------------------|--------------------
cachorro morde homem  | [1, 1, 1, 0, 0, 0] 
homem morde cachorro  | [1, 1, 1, 0, 0, 0] 
cachorro come carne   | [1, 0, 0, 1, 1, 0] 
homem come comida     | [0, 0, 1, 1, 0, 1] 


- Nesse caso, não é levado em conta a ordem da frase, por isso a frase "cachorro morde homem" tem a mesma representação que a "homem morde cachorro".

## Modelo 3 : Bag of n-grams
- O corpus é dividido em n-gramas (bigramas, por exemplo):
1- cachorro morde 
2- morde homem 
3- homem morde 
4- morde cachorro
5- cachorro come
6- come carne
7- homem come
8- come comida

- Cada digito do vetor representa um bigrama, e o vetor completo também representa uma frase:
| cachorro morde homem | [1,1,0,0,0,0,0,0] |
| homem morde cachorro | [0,0,1,1,0,0,0,0] |
| cachorro come carne  | [0,0,0,0,1,1,0,0] |
| homem come comida    | [0,0,0,0,0,0,1,1] |


## Modelo 4 : TF - IDF

- TF: Uma relação matemática que retorna a frequência que a palavra ocorre em um determinado documento:
![TF](https://latex.codecogs.com/svg.image?\bg{white}\color{white}\text{Tf(palavra,documento)}=\frac{\text{num&space;de&space;ocorrencias&space;da&space;palavra}}{\text{num&space;total&space;de&space;termos&space;no&space;documento}})

- IDF Uma relação que mede a importância de um termo em um conjunto de documentos (corpus) :
![IDF](https://latex.codecogs.com/svg.image?\bg{white}\color{white}\text{Idf(palavra)}=log(\frac{\text{n&space;total&space;de&space;documentos}}{\text{n&space;de&space;documentos&space;contendo&space;a&space;palavra}}))



