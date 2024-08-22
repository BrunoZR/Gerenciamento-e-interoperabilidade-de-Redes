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
     

* DADOS ESTRUTURADOS *
- Dados que são organizados e formatados de maneira sistemática, permitindo fácil acesso, análise e manipulação.

- Frequentemente é útil ter um modelo que retorne uma saída que corresponda a um esquema específico.

- Método .with_structured_output()

Esta é a maneira mais fácil e confiável de obter saídas estruturadas. O método with_structured_output() é implementado para modelos que fornecem APIs nativas para estruturar saídas, como chamadas de ferramentas/funções ou modo JSON/Pydantic, e utiliza essas capacidades internamente.

- Escolhendo entre múltiplos esquemas: A maneira mais simples de permitir que o modelo escolha entre vários esquemas é criar um esquema "pai" que tenha um atributo do tipo Union:

```
from typing import Union
# Pydantic
class Piada(BaseModel):
    """Piada para contar ao usuário."""

    introducao: str = Field(description="A introdução da piada")
    arremate: str = Field(description="O desfecho da piada")
    avaliacao: Optional[int] = Field(
        default=None, description="Quão engraçada é a piada, de 1 a 10"
    )

class RespostaConversacional(BaseModel):
    """Responda de maneira conversacional. Seja gentil e prestativo."""

    resposta: str = Field(description="Uma resposta conversacional à pergunta do usuário")

class Resposta(BaseModel):
    saida: Union[Piada, RespostaConversacional]
     

modelo_estruturado = modelo.with_structured_output(Resposta)

resposta = modelo_estruturado.invoke("Me conte uma piada sobre gatos")
```




- Few-shot prompting: Técnica onde se fornecem alguns exemplos  no prompt para guiar o modelo na geração de respostas. Em vez de treinar o modelo com uma nova base de dados completa, você apenas inclui alguns exemplos relevantes diretamente no prompt.


* EXTRAÇÃO DE INFORMAÇÃO *
Extração de Informação (EI) é o processo de identificar e extrair dados estruturados a partir de texto não estruturado. 
- Passo 1: Schema : Descrever quais informações extraídas
- Passo 2: Extator: Como as informações serão extraídas (Definir um prompt)

- Como lidar com textos longos ao realizar a extração?
     - Quando trabalhar com arquivos, como PDFs, é provável que você encontre texto que excede a janela de contexto do seu modelo de linguagem. Para processar esse texto, considere estas estratégias:
     
     - Mudar o LLM: escolha um LLM diferente que suporte uma janela de contexto maior.
     - Força Bruta: divida o documento em partes e extraia o conteúdo de cada parte.
     - RAG (Retrieval-Augmented Generation): divida o documento em partes, indexe as partes e extraia conteúdo apenas de um subconjunto de partes que pareçam "relevantes".
