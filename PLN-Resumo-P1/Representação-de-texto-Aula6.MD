# Como fazer o computador entender mensagens, em específico textos?
Apesar de serem enviados textos, áudios e imagens, o computador interpreta apenas valores matemáticos binários.
Existem diversos métodos para cada tipo de informação. O escopo de análise será entender a *representação de texto* .
No geral, são utilizadas *representações vetoriais*, um espaço algébrico interessante e conveniente.

Para explicarmos cada modelo, considere os seguintes documentos:
D1 | cachorro morde homem
D2 | homem morde cachorro
D3 | cachorro come carne
D4 | homem come comida

## Modelo 1 : One-Hot encoding
- Cada palavra se transforma em um vetor
- Cada uma dessas palavras recebe um ID único

