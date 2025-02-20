# Probabilidade de sentenças
## A chance de uma frase composta pelas palavras w1,w2,w3,w4 (nessa ordem) acontecer é dada por:

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

### Exemplo 1 - Considere o poema:

```
no meio do caminho tinha uma pedra
tinha uma pedra no meio do caminho
tinha uma pedra
no meio do caminho tinha uma pedra
```

#### A) Quantos unigramas tem o poema?

- Como são unigramas, cada palavra será um unigrama.
- Existem 24 palavras no texto, mas a resposta não é 24, pois não valem repetições. \n
- Contando todas as palavras apenas uma vez, chega-se em *7 unigramas* .


#### B) Qual a probabilidade de cada unigrama no poema?
- Basta contar quantas vezes cada unigrama aparece e dividr pelo número total de palavras.

    | Unigrama  | Probabilidade                                      |
    |-----------|----------------------------------------------------|
    | P(no)     | ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{3}{24})     |
    | P(meio)   | ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{3}{24})     |
    | P(do)     | ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{3}{24})     |
    | P(caminho)| ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{3}{24})     |
    | P(tinha)  | ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{4}{24})     |
    | P(uma)    | ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{4}{24})     |
    | P(pedra)  | ![fração](https://latex.codecogs.com/svg.image?\color{white}\frac{4}{24})     |


### C) Quantos bigramas existem no poema?
- No caso de bigrama, marcadores iniciais e finais de texto devem ser considerados.
```
<s> no meio do caminho tinha uma pedra <s>
<s> tinha uma pedra no meio do caminho <s>
<s> tinha uma pedra <s>
<s> no meio do caminho tinha uma pedra <s>
```

- Bigramas totais: 11
```
(<s>, no), (no, meio), (meio, do),
(do, caminho), (caminho, tinha),
(tinha, uma), (uma, pedra),
(pedra, </s>), (<s>, tinha),
(pedra, no), (caminho, </s>)
```

### D) Como calcular a probabilidade de um bigrama ocorrer?
Como exemplo, vamos calcular a probabilidade de P(meio|no) , correspondente ao bigrama (no,meio):
- Precisamos saber a probabilidade de aparecer a palavra "meio", sabendo que apareceu a palavra "no" antes.
- Para isso, contamos quantas vezes a palavra "meio" apareceu depois de "no" (3)
- Depois, contamos quantas vezes a palavra "no" apareceu em algum bigrama (3)
- Agora, basta dividir 2/4 = 2.
- O raciocínio resulta na mesma coisa que aplicar a fórmula:

![a](https://latex.codecogs.com/svg.image?\color{white}\;P(no|meio)=\frac{P(no\cap&space;meio)}{P(no)}\Leftrightarrow\frac{\frac{3}{11}}{\frac{3}{11}}\Leftrightarrow&space;1\Leftrightarrow&space;100%)

- A única diferença é que a probabilidade que é utilizada (em vez de 3/3 , fica 3/11 / 3/11 , que resulta em 1 também.) Então, podemos escrever de forma mais simples a fórmula, valendo para qualquer caso:                                                                               
        ![b](https://latex.codecogs.com/svg.image?\bg{white}\color{white}\;P(no|meio)=\frac{contar(no\&space;meio)}{contar(no)}\Leftrightarrow\frac{3}{3}\Leftrightarrow&space;1\Leftrightarrow&space;100%)


## Observação
No final desses slides, tem uma parte "prática" que julguei não ser útil para a prova, então não inseri no resumo. Ele ensina métodos para calcular o quão eficiente um modelo de linguagem é bom, utilizando uma fórmula chamada "perplexidade" e mostrando alguns modelos de análises frequentemente utilizados (*Laplace add 1 smoothing & Lidstone add k smoothing*)

## Importante para a prova
- Em muitas ocasiões, o cálculo da probabilidade de uma frase envolva uma sequência de duas palavras que nunca aconteceu na sua base de texto. Nesse caso, a probabilidade dessa sequência é 0, e não importa o quanto seja a probabilidade dos outros pedaços/n-gramas , a probabilidade dessa frase ocorrer é ZERO!


