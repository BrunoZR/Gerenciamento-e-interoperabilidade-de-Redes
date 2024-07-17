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
-------- | ------
cachorro | [1,0,0,0,0,0]
morde    | [0,1,0,0,0,0]
homem    | [0,0,1,0,0,0]
come     | [0,0,0,1,0,0]
carne    | [0,0,0,0,1,0]
comida   | [0,0,0,0,1,0]


