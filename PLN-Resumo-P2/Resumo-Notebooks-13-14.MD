*Engenharia de prompts*** é o processo de criar, ajustar e otimizar comandos (ou "prompts*") dados a modelos de linguagem para obter respostas mais precisas, úteis ou relevantes.
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
     
