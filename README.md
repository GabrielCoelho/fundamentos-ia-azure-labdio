# Laboratório Prático: Fundamentos de IA do Microsoft Azure

## Resumo do Material Estudado

Este documento apresenta um resumo do conteúdo estudado sobre Fundamentos de IA do Microsoft Azure, abrangendo conceitos fundamentais de IA e processamento de linguagem natural (PLN), com instruções práticas para uso das ferramentas Azure AI Foundry.

### Conceitos Fundamentais de IA

#### Definição de Inteligência Artificial
- **Conceito principal**: IA é a tecnologia que permite prever resultados e reconhecer padrões com base em dados históricos
- **Cargas de trabalho comuns**: Machine Learning, Processamento de Linguagem Natural, Visão Computacional, Mineração de Conhecimento e IA Generativa

#### Tipos de Machine Learning
- **Aprendizado supervisionado**: Utiliza dados rotulados para treinar modelos
  - **Regressão**: O rótulo previsto é um valor numérico (ex: prever vendas de sorvete)
  - **Classificação binária**: O rótulo determina se um item pertence ou não a uma classe específica (ex: risco de diabetes)
  - **Classificação multiclasse**: O rótulo representa uma das várias classes possíveis

#### Princípios de IA Responsável
- **Transparência**: Permitir que usuários entendam como as decisões da IA são tomadas
- **Exclusão**: Evitar discriminação e vieses nos sistemas de IA
- **Preconceito**: Identificar e mitigar vieses nos dados e algoritmos
- **Complexidade**: Lidar com sistemas complexos de forma responsável

### Processamento de Linguagem Natural (PLN)

#### O que é PLN?
- Área da IA que permite a compreensão, interpretação e geração de linguagem humana
- Inclui etapas como pré-processamento, tokenização, treinamento de modelos de linguagem e aplicações diversas

#### Capacidades de PLN no Azure
1. **Análise de Texto**:
   - Detecção de idioma - identifica a língua predominante no texto
   - Reconhecimento de Entidades Nomeadas (NER) - identifica pessoas, locais, organizações, etc.
   - Extração de frases-chave - identifica os principais conceitos do texto
   - Análise de sentimentos - determina a tonalidade emocional do texto (positivo, negativo, neutro)
   - Detecção de PII e PHI - identifica informações pessoais e de saúde sensíveis

2. **Respostas a Perguntas**:
   - Permite criar bases de conhecimento de pares de perguntas e respostas
   - Pode ser criada inserindo perguntas e respostas manualmente
   - Suporta importação de documentos de FAQ existentes
   - Permite construção via bate-papo integrado

3. **Serviço de Fala**:
   - Conversão de fala para texto (speech-to-text)
   - Conversão de texto para fala (text-to-speech)
   - Tradução de fala

4. **Tradutor**:
   - Tradução de texto entre idiomas
   - Tradução personalizada
   - Tradução de documentos

5. **Serviço de Bot do Azure**:
   - Plataforma baseada em nuvem para desenvolvimento e gerenciamento de bots
   - Integração com serviços de IA de Linguagem
   - Conectividade através de vários canais de comunicação

6. **Compreensão da Linguagem Coloquial**:
   - Identifica entidades e intenções em enunciados
   - Permite o processamento de comandos naturais dos usuários

## Guia Prático: Azure AI Foundry Portal

Nesta seção, apresento um passo a passo detalhado de como utilizar as ferramentas do Azure AI Foundry para analisar texto e fala. Estas instruções práticas são essenciais para desenvolver habilidades na criação de soluções baseadas em IA para processamento de linguagem.

### Configuração Inicial do Ambiente

Para utilizar os serviços de IA do Azure, precisamos criar um projeto no Azure AI Foundry:

1. **Acessar o Azure AI Foundry**:
   - Navegue até [Azure AI Foundry](https://ai.azure.com)
   - Faça login com sua conta Microsoft

2. **Criar um novo projeto**:
   - Na página inicial, clique em "Create a project"
   - Aceite o nome gerado automaticamente ou personalize-o
   - Se necessário, crie um novo hub com um nome exclusivo
   - **Importante**: Selecione uma das seguintes localizações: East US, France Central, Korea Central, West Europe ou West US

3. **Recursos criados automaticamente**:
   - Azure AI services
   - Azure AI hub
   - Azure AI project
   - Storage account
   - Key vault
   - Resource group

### Explorando o Serviço de Fala (Speech Studio)

O Azure AI Speech Service permite transcrever fala em texto e converter texto em fala audível, ideal para reuniões, entrevistas e aplicações com interface de voz.

#### Transcrição de Fala em Tempo Real

1. **Acessar o Speech Studio**:
   - No menu lateral do seu projeto, selecione "AI Services"
   - Clique no tile "Speech"
   - Role até a seção "Try out Speech capabilities"
   - Selecione "Real-time transcription"

2. **Transcrever áudio**:
   - Baixe o arquivo de exemplo em: https://aka.ms/mslearn-speech-files
   - Extraia o arquivo speech.zip
   - Clique em "Browse files" e selecione o arquivo "WhatAICanDo.m4a"
   - Observe a transcrição sendo realizada em tempo real

3. **Análise dos resultados**:
   - Verifique o texto transcrito que deve mostrar informações sobre como a IA pode ser utilizada para melhorar diversas áreas
   - O serviço detecta automaticamente o idioma e mostra a transcrição formatada
   - É possível exportar os resultados para uso em outras aplicações

#### Outros recursos do Speech Studio:

- **Text-to-Speech**: Permite converter texto em fala natural
- **Speech Translation**: Traduz áudio de um idioma para outro
- **Custom Voice**: Permite criar vozes personalizadas

### Explorando o Serviço de Linguagem (Language Studio)

O Azure AI Language inclui capacidades avançadas de processamento de linguagem natural (PLN) que permitem extrair informações valiosas de textos não estruturados, como avaliações de hotéis, comentários de produtos, e documentos em geral.

#### Extração de Entidades Nomeadas

1. **Acessar o Language Playground**:
   - No menu lateral, selecione "Playgrounds"
   - Clique no tile "Language playground"
   - Selecione "Extract information" e depois "Extract named entities"

2. **Analisar um texto de exemplo**:
   - Cole o seguinte texto de uma avaliação de hotel:
   ```
   Tired hotel with poor service
   The Royal Hotel, London, United Kingdom
   5/6/2018
   This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
   ```
   - Clique em "Run"

3. **Interpretar os resultados**:
   - Observe como o sistema identifica entidades como:
     - "Royal Hotel" (Local)
     - "London" (Local)
     - "United Kingdom" (Local)
     - "5/6/2018" (Data)
     - "British Museum" (Local)
   - Cada entidade vem com um score de confiança e um tipo associado

#### Extração de Frases-Chave

1. **Acessar a função**:
   - No Language playground, selecione "Extract information"
   - Clique em "Extract key phrases"

2. **Analisar um texto positivo**:
   - Cole o seguinte texto de uma avaliação positiva:
   ```
   Good Hotel and staff
   The Royal Hotel, London, UK
   3/2/2018
   Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian (West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
   ```
   - Clique em "Run"

3. **Interpretar os resultados**:
   - Observe as frases-chave extraídas que representam os principais pontos da avaliação
   - Estas frases capturam a essência do texto sem necessidade de ler todo o conteúdo

#### Sumarização de Texto

1. **Acessar a função**:
   - No Language playground, selecione "Summarize information"
   - Clique em "Summarize text"

2. **Analisar um texto negativo**:
   - Cole o seguinte texto de uma avaliação negativa:
   ```
   Very noisy and rooms are tiny
   The Lombard Hotel, San Francisco, USA
   9/5/2018
   Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
   ```
   - Clique em "Run"

3. **Interpretar os resultados**:
   - Observe o resumo extrativo que seleciona as frases mais relevantes do texto
   - Cada frase recebe uma pontuação de relevância
   - O resumo mantém os pontos principais preservando o contexto original

## Reflexões Sobre a Experiência Prática

Após explorar o Azure AI Foundry portal e suas ferramentas de processamento de linguagem, posso compartilhar algumas reflexões importantes:

1. **Acessibilidade da IA**: A Microsoft realmente democratizou o acesso a ferramentas avançadas de IA, permitindo que profissionais sem profundo conhecimento técnico implementem soluções sofisticadas.

2. **Potencial de aplicação**: Estas ferramentas têm aplicações práticas imediatas em diversos setores:
   - Atendimento ao cliente (análise de feedback)
   - Pesquisa de mercado (extração de insights de opiniões)
   - Transcrição de reuniões e entrevistas
   - Acessibilidade digital (conversão de texto em fala)

3. **Limitações observadas**:
   - A qualidade dos resultados ainda depende muito do contexto e da língua utilizada
   - Para aplicações mais específicas, os modelos personalizados são necessários
   - É importante considerar aspectos éticos ao implementar estas soluções

4. **Aprendizados técnicos**: O processo de criação de recursos no Azure e a configuração do ambiente são tão importantes quanto o entendimento dos algoritmos de IA. A infraestrutura adequada é fundamental para o sucesso dos projetos.

## Questões Práticas Abordadas

### Questões sobre Conceitos Fundamentais de IA
1. **Princípios de IA responsável**: Transparência foi identificada como o princípio que se refere à necessidade de os usuários confiarem em sistemas complexos.
2. **Cargas de trabalho de IA**: Machine Learning foi identificado como o tipo de carga de trabalho associada a modelos preditivos baseados em dados e estatísticas.
3. **Definição de IA**: A definição mais abrangente é "Prever resultados e reconhecer padrões com base em dados históricos".
4. **Regressão**: Forma de aprendizado de máquina supervisionado onde o rótulo previsto é um valor numérico.
5. **Classificação binária**: Forma de aprendizado de máquina supervisionado onde o rótulo determina se o item pertence ou não a uma classe específica.
6. **Cargas de trabalho comuns**: Visão Computacional foi identificada como um exemplo válido de carga de trabalho comum de IA.

### Questões sobre Processamento de Linguagem Natural
1. **Extração de frases-chave**: Funcionalidade que avalia e retorna os principais conceitos em texto não estruturado como uma lista.
2. **Análise de Texto**: Abrange identificação de frases-chave, sentimentos e idioma, mas não análise de rostos em imagens (que pertence à Visão Computacional).
3. **Principais pontos de discussão**: A Extração de frases-chave é o recurso adequado para determinar os principais pontos de discussão em um documento.
4. **Serviço de Fala**: Fornece capacidades de reconhecimento de fala e conversão de texto em fala.
5. **Serviço de Linguagem**: Não é responsável pela conversão de texto em fala (função do Serviço de Fala).
6. **Tradutor**: Serviço de tradução automática neural baseado em nuvem que faz parte dos serviços de IA do Azure.
7. **Language Studio**: Acessível via https://language.cognitive.azure.com
8. **Base de conhecimento para bots**: O serviço de Respostas às Perguntas é a opção adequada para criar bases de conhecimento para bots.

## Recursos Adicionais
- Hands-on com serviço de Fala: https://aka.ms/ai900-speech
- Hands-on com análise de texto: https://aka.ms/ai900-text-analysis
- Página oficial do serviço de Linguagem: [Language service page](https://learn.microsoft.com/azure/ai-services/language-service/)
- Página oficial do serviço de Fala: [Speech page](https://learn.microsoft.com/azure/ai-services/speech-service/)
- Portal Azure: https://portal.azure.com

## Limpeza de Recursos

Ao finalizar os experimentos, é importante excluir os recursos não utilizados para evitar custos desnecessários:

1. Acesse o [Portal do Azure](https://portal.azure.com)
2. Selecione o grupo de recursos que contém os recursos criados
3. Selecione os recursos e clique em "Delete"
4. Confirme a exclusão clicando em "Yes"

---

*Este documento representa minha jornada de aprendizado através dos Fundamentos de IA do Microsoft Azure, focando no processamento de linguagem natural e fala. A experiência prática com estas ferramentas expandiu minha compreensão sobre como implementar soluções baseadas em IA e as possibilidades que elas oferecem para resolver problemas reais.*
