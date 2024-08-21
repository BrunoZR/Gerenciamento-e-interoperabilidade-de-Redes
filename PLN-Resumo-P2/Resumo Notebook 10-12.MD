* Word embeddings*
- Palavras representadas por vetores que tem 30 dimensões.
- Permite operações aritméticas e lógicas entre eles.
- Similaridade por cosseno entre duas palavras: Produto escalar: cos = a.b/|a|.|b|
- Inferência lógica para: odiar está para odiando, assim como amar está para...


**LangChain** :  framework projetado para desenvolver aplicações que utilizam Grandes Modelos de Linguagem de maneira integrada e eficiente.
- No LangChain, uma cadeia é uma sequência de operações que conecta vários componentes, como modelos de linguagem, parsers de saída para criar um fluxo de trabalho coeso. A cadeia permite combinar diferentes passos de processamento e manipulação de dados de maneira estruturada e eficiente.
As cadeias são configuradas para permitir um fluxo contínuo de dados entre os componentes, facilitando a construção de aplicações complexas de PLN.
Ex: Prompt com mensagem para o sistema e escolha de variável a ser a mensagem do usuário | modelo

Podemos então inicializar o modelo:
- PromptTemplates são um conceito no LangChain projetado para auxiliar nessa transformação. Eles recebem a entrada bruta do usuário e retornam dados (um prompt) que estão prontos para serem passados para um modelo de linguagem.

-MessagesPlaceholder: modelo de prompt é responsável por adicionar uma lista de mensagens em um determinado local.
   - Classe usada no LangChain para representar um espaço reservado dentro de um modelo de prompt, onde mensagens dinâmicas podem ser inseridas posteriormente. Ele atua como um marcador que indica onde as mensagens devem ser incluídas na estrutura do prompt.

- Coerção: Combina a resposta recebida de um prompttemplate para fazer outro prompttemplate.
RunnableParallels facilitam a execução de múltiplos runnables em paralelo e o retorno da saída desses runnables como um mapa.

-LCEL, ou LangChain Expression Language, é uma linguagem declarativa desenvolvida para compor facilmente chains (cadeias de tarefas) dentro do ecossistema LangChain. Ela oferece uma interface unificada que simplifica a criação de pipelines complexos envolvendo modelos de linguagem, extração de dados, e outras operações relacionadas ao processamento de linguagem natural.
  - O LCEL permite que os desenvolvedores conectem diferentes componentes, como prompts, modelos de linguagem, e parseadores de forma intuitiva usando operadores simples como o pipe (|). Isso não só facilita a leitura e a manutenção do código, mas também garante suporte completo para operações síncronas, assíncronas e de streaming, tornando-o ideal para aplicações de produção que exigem robustez e escalabilidade.
- Runnables são uma abstração no ecossistema LangChain que permitem criar componentes reutilizáveis e encadeáveis, os quais executam tarefas específicas em um fluxo de dados. Eles são fundamentais para manipular o fluxo de informações em pipelines criados com LangChain, possibilitando a execução de operações em paralelo, o processamento de entradas e saídas, e a customização das funções usadas em um chain (cadeia).
  Aqui estão alguns pontos-chave sobre runnables:
  - Flexibilidade: Runnables permitem que você modifique o fluxo de dados ou as próprias informações que estão sendo passadas entre os componentes de um pipeline. Isso é útil quando você precisa ajustar ou transformar dados antes de passá-los para o próximo estágio.
  
  - Reuso: Como runnables são componentes isolados, eles podem ser facilmente reutilizados em diferentes partes do seu pipeline ou mesmo em diferentes pipelines, o que facilita a manutenção e a modularidade do código.
  
  - Paralelismo e Encadeamento: Com runnables, é possível executar várias operações em paralelo ou encadeá-las de maneira eficiente, garantindo que todas as partes do pipeline funcionem de maneira sincronizada e otimizada.

RunnableLambda: Este é um tipo específico de runnable que permite transformar funções Python em funções compatíveis com pipes dentro de um pipeline LangChain. Isso amplia a capacidade de personalização, permitindo que qualquer função Python seja integrada ao fluxo de dados.
**COHERE**
- Empresa de IA especializada em fornecer soluções de PLN.
- Conversas de Múltiplas Interações (Multi-turn): Ter o contexto de conversas anteriores pode permitir que o modelo de linguagem forneça respostas mais relevantes. Em conversas de múltiplas interações, reter o contexto das interações anteriores é essencial para gerar respostas coerentes e pertinentes. A API do Cohere facilita isso, permitindo-nos incluir o histórico do chat através do parâmetro chat_history.

**GROQ**
Groq é uma empresa de tecnologia que desenvolve hardware e software voltados para computação de alto desempenho, particularmente em aplicações de IA e aprendizado de máquina. Fundada por ex-engenheiros da Google, a Groq é conhecida por seus chips de processamento (chamados de "Tensor Streaming Processor" ou TSP) que são projetados para acelerar tarefas de IA, como a inferência de modelos de aprendizado profundo.

