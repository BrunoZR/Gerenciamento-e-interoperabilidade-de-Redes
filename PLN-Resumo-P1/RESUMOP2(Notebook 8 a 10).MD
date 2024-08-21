AULA 8 A 10

*OPEN AI*
**Modo *JSON***
Uma maneira comum de usar o endpoint chat completions é instruir o modelo a sempre retornar um objeto JSON que faça sentido para o seu caso de uso, especificando isso na mensagem do sistema. Embora isso funcione em alguns casos, ocasionalmente os modelos podem gerar uma saída que não é analisada em objetos JSON válidos.

Para evitar esses erros e melhorar o desempenho do modelo, ao usar gpt-4o, gpt-4-turbo ou gpt-3.5-turbo, você pode definir response_format como { "type": "json_object" } para ativar o modo JSON. Quando o modo JSON está ativado, o modelo é restrito a gerar apenas cadeias de caracteres que são analisadas em objetos JSON válidos.

Texto para Fala (Text to Speech)
A API da OpenAI também fornece um endpoint para gerar aúdio com base no modelo TTS (text-to-speech). O modelo oferece suporte a vários idiomas.

O endpoint de fala recebe três entradas principais: o modelo, o texto que deve ser transformado em áudio e a voz a ser usada para a geração do áudio.

Experimente diferentes vozes (alloy, echo, fable, onyx, nova e shimmer) para encontrar uma que corresponda ao tom e ao público desejados. As vozes atuais são otimizadas para inglês.

O formato de resposta (response_format) padrão é mp3, mas outros formatos como opus, aac, flac e pcm estão disponíveis. A velocidade (speed) do áudio gerado pode variar entre 0.25 e 4.



*GEMINI*
O método generate_content pode lidar com uma ampla variedade de casos de uso, incluindo chat com vários turnos e entrada multimodal, dependendo do suporte do modelo subjacente. Os modelos disponíveis aceitam apenas texto e imagens como entrada e texto como saída.
O Gemini pode gerar várias respostas possíveis para um único comando. Essas possíveis respostas são chamadas de candidates e você pode analisá-las para selecionar a mais adequada como resposta.
Conversas por Chat

Com o Gemini, você pode ter conversas livres em vários turnos. A classe ChatSession simplifica o processo gerenciando o estado da conversa. Assim, ao contrário de generate_content, não é necessário armazenar o histórico de conversas como uma lista.
Geração de Texto

A maneira mais simples de gerar texto usando a API Gemini é fornecer ao modelo uma única entrada somente de texto, como mostrado neste exemplo:

```

import google.generativeai as genai

genai.configure(api_key = GOOGLE_API_KEY)

modelo = genai.GenerativeModel("gemini-1.5-flash")

resposta = modelo.generate_content("Escreva uma história sobre uma mochila mágica")

resposta.text
```

Nesse caso, o comando ("Escreva uma história sobre uma mochila mágica") não inclui exemplos de saída, instruções do sistema ou informações de formatação. É uma abordagem zero-shot. Em alguns casos de uso, um comando one-shot ou few-shot pode produzir um resultado mais alinhado às expectativas do usuário.

Zero-shot: esses prompts não contêm exemplos para o modelo replicar. Os comandos zero-shot mostram essencialmente a capacidade do modelo de concluir o comando sem outros exemplos ou informações. Significa que o modelo precisa do conhecimento pré-existente para gerar uma resposta plausível.

One-shot: esses prompts fornecem ao modelo um único exemplo para replicar e continuar o padrão. Isso permite a geração de respostas previsíveis do modelo.

few-shot: esses comandos fornecem ao modelo vários exemplos para replicar. Use comandos few-shot para concluir tarefas complicadas, como sintetizar dados com base em um padrão.

A API Gemini oferece suporte a entradas multimodais que combinam texto com arquivos de mídia. O exemplo abaixo mostra como gerar texto com base em uma entrada de texto e imagem:

Visão
A API Gemini pode executar inferência em imagens e vídeos transmitidos a ela. Ao transmitir uma imagem, uma série de imagens ou um vídeo, o Gemini pode:

Descrever ou responder a perguntas sobre o conteúdo
Resumir o conteúdo
Extrapolar o conteúdo
Receber uma transcrição do arquivo de áudio


chat = modelo.start_chat()

modelo = genai.GenerativeModel("gemini-1.5-pro")

resposta = modelo.generate_content((
    'Qual é a soma dos primeiros 10 números primos? '
    'Gere e execute o código para o cálculo e certifique-se de obter todos os 10.'),
    tools = 'code_execution')

modelo = genai.GenerativeModel(
    model_name = 'gemini-1.5-pro',
    tools = 'code_execution')

resposta = modelo.generate_content((
    'Qual é a soma dos primeiros 50 números primos? '
    'Gere e execute o código para o cálculo e certifique-se de obter todos os 50.'))
     
