*Engenharia de prompts : é o processo de criar, ajustar e otimizar comandos (ou "prompts*") dados a modelos de linguagem para obter respostas mais precisas, úteis ou relevantes.
- Essa prática envolve a formulação cuidadosa de perguntas ou instruções para garantir que o modelo compreenda e responda de maneira adequada ao que está sendo solicitado.
```
from langchain.prompts import PromptTemplate
from langchain_openai import ChatOpenAI

template = """Question: {question}

Answer: Let's think step by step.
1. Determine the number of terms (n) in the series.
2. Use the formula for the sum of the first n natural numbers: S = n*(n+1)/2.
3. Calculate the result based on the provided n."""

prompt = PromptTemplate(template=template, input_variables=["question"])

modelo = ChatOpenAI()

chain = prompt | modelo

question = "What is the sum of the first 100 natural numbers?"

resposta = chain.invoke({"question": question})
```

** Extração de informação
Extração de Informação

```
from langchain_openai import ChatOpenAI
     

modelo = ChatOpenAI( temperature = 0.1, max_tokens = 256 )
     

prompt = PromptTemplate(
    input_variables=["texto"],
    template =
    'TEXTO: {texto}\n' \
    'Dado o texto acima, extraia informações importantes no formato abaixo:\n' \
    ': '\
    'Preserve a exata formatação apresentada.'
)
     

texto = "Alan Mathison Turing (Londres, 23 de junho de 1912 — Wilmslow, Cheshire, 7 de junho de 1954)"\
        "foi um matemático, cientista da computação, lógico, criptoanalista, filósofo e biólogo teórico "\
        "britânico. Turing foi altamente influente no desenvolvimento da moderna ciência da computação "\
        "teórica, proporcionando uma formalização dos conceitos de algoritmo e computação com a máquina "\
        "de Turing, que pode ser considerada um modelo de um computador de uso geral. Ele é amplamente "\
        "considerado o pai da ciência da computação teórica e da inteligência artificial. Apesar dessas "\
        "realizações ele nunca foi totalmente reconhecido em seu país de origem durante sua vida por ser "\
        "homossexual e porque grande parte de seu trabalho foi coberto pela Lei de Segredos Oficiais."
     

chain = prompt | modelo

resposta = chain.invoke({"texto": texto})
```
     
