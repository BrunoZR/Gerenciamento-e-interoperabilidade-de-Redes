# Probabilidade de sentenças
## A chance de uma frase acontecer é dada por:

![Formula](https://latex.codecogs.com/svg.image?\color{white}P(w_1,w_2,w_3,w_4)=P(w_1)\cdot&space;P(w_2\mid&space;w_1)\cdot&space;P(w_3\mid&space;w_1,w_2)\cdot&space;P(w_4\mid&space;w_1,w_2,w_3))

## Entendendo a notação:
- P(w1) = Probabilidade da palavra 1 , P(w2) = Probabilidade da palavra 2 , P(w3) = Probabilidade da palavra 3....
- P(w2|w1) = Probabilidade de ocorrer a palavra 2 sabendo que ocorreu a palavra 1.

- A forma de calcular uma probabilidade P(A|B) é dada por

  ![Formula](https://latex.codecogs.com/svg.image?\color{white}P(A|B)=\frac{P(A\cap&space;B)}{P(A)})

## N-Gramas
![print](https://private-user-images.githubusercontent.com/174112183/349214910-7d2ebcbb-1137-4625-9e93-65039805eadc.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjExNTE0MjEsIm5iZiI6MTcyMTE1MTEyMSwicGF0aCI6Ii8xNzQxMTIxODMvMzQ5MjE0OTEwLTdkMmViY2JiLTExMzctNDYyNS05ZTkzLTY1MDM5ODA1ZWFkYy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNzE2JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDcxNlQxNzMyMDFaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hNWViYmQwZWY2YmEwYjBlZGQxYmEwZTU4ZDAwNzllMmRhYThkODg2MmZlYmVkYTM4Y2I4NWU2YzMxZDRmYTBlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.aSRIVhi8EWvUj-sL_g4jBtIGudEo4DBQ8emTg65JaPY)

- O que é : Sequência de n elementos/tokens
- Função : Estimar probabilidade de uma sequência de palavras. Geralmente são usados bigramas ou trigramas.

### Exemplo1: Considere o poema:

```
no meio do caminho tinha uma pedra
tinha uma pedra no meio do caminho
tinha uma pedra
no meio do caminho tinha uma pedra
```

#### A) Quantos unigramas tem o poema?

Como são unigramas, cada palavra será um unigrama.\n
Existem 24 palavras no texto, mas a resposta não é 24, pois não valem repetições. \n
Contando todas as palavras apenas uma vez, chega-se em *7 unigramas* .


### B) Qual a probabilidade de cada unigrama?



###
