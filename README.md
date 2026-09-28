# 📚 Treinando uma IA de Aprendizagem: Explore o Poder do NotebookLM

> **Projeto Prático - Desafio DIO & NotebookLM**  
> Caderno Temático desenvolvido como ferramenta de aprendizagem ativa com o apoio de Inteligência Artificial para curadoria, síntese e resolução de problemas técnicos em engenharia de software.

---

## 1. 📌 Contexto e Objetivos

* **Tema Escolhido:** Arquitetura de Software: Da Evolução do Monólito aos Microsserviços e Event-Driven Architecture (EDA).

* **Contexto:** Com o crescimento e a complexidade das aplicações modernas, a escolha do estilo arquitetural e dos padrões de comunicação entre serviços tornou-se decisiva para garantir escalabilidade, resiliência e facilidade de manutenção. Compreender quando utilizar monólitos, como decompô-los em microsserviços e quando adotar arquiteturas orientadas a eventos é fundamental para o desenvolvimento backend.

* **Objetivos de Estudo:**

  1. Compreender a evolução histórica e técnica dos sistemas monolíticos para microsserviços, analisando trade-offs, custos operacionais e padrões de decomposição.

  2. Mapear e comparar os principais protocolos e estilos de comunicação entre APIs (REST, gRPC, GraphQL e Mensageria assíncrona).

  3. Explorar padrões de resiliência e persistência distribuída (Circuit Breaker, Saga Pattern, CQRS, Banco de Dados por Serviço).

  4. Validar o **NotebookLM** como assistente de estudos para sintetizar conceitos complexos de arquitetura e extrair diretrizes técnicas ancoradas em documentações confiáveis.

---

## 2. 🗂️ Curadoria de Fontes e Referências Arquiteturais

Para alimentar este Caderno Temático no **NotebookLM**, foram selecionadas e importadas **4 fontes de referência aberta em texto/PDF**:

---

### 1. Event-Driven Microservices Architectures: Principles, Patterns and Best Practices
* **Autor:** Sandeep Kumar *(State University of New York at Buffalo)*
* **Publicação:** *World Journal of Advanced Engineering Technology and Sciences* (2025)
* **Links:** 
  * 📄 [Artigo Completo / DOI (WJAETS)](https://doi.org/10.30574/wjaets.2025.15.3.1137)
  * 📥 [Visualizar / Download PDF (WJAETS PDF Direct)](https://wjaets.com/content/event-driven-microservices-architectures-principles-patterns-and-best-practices)
  * 🔬 [ResearchGate Publication](https://www.researchgate.net/publication/393168722_Event-Driven_Microservices_Architectures_Principles_Patterns_and_Best_Practices)
* **Resumo:**
  Análise abrangente de arquiteturas baseadas em eventos (EDA), abordando desde fundamentos teóricos (Teoria dos Sistemas Distribuição, Teorema CAP, *Domain-Driven Design* / DDD) até padrões práticos:
  * **Padrões Chave:** *Event Sourcing*, CQRS (*Command Query Responsibility Segregation*), Sagas (*Choreography* vs. *Orchestration*) e Processamento de Streams de Eventos.
  * **Estratégias Técnicas:** Governança e versionamento de schemas de eventos (Avro, JSON, Protobuf), comparação entre brokers (Apache Kafka, RabbitMQ) e modelos de persistência.
  * **Desafios & Resiliência:** Gestão de consistência eventual (*eventual consistency*), idempotência, ordenação de eventos, tolerância a falhas (*Circuit Breakers*, *Bulkheads*) e observabilidade (*OpenTelemetry*, tracing distribuído).

---

### 2. Microservice Architecture: Aligning Principles, Practices, and Culture

* **Autores:** Irakli Nadareishvili, Ronnie Mitra, Matt McLarty & Mike Amundsen
* **Publicação:** O'Reilly Media (2016)
* **Links:**
  * 📖 [Página Oficial na O'Reilly](https://www.oreilly.com/library/view/microservice-architecture/9781491956243/)
  * 📄 [Acesso / Leitura em PDF](https://www.corisys.ru/wp-content/uploads/2020/10/microservice-architecture-aligning-principles-practices-and-culture.pdf)
* **Resumo:**
  Obra focada no alinhamento entre a arquitetura de microserviços, operações e cultura organizacional. Aborda os princípios essenciais para decomposição de sistemas monolíticos, autonomia de equipes, entrega contínua com velocidade/segurança (*Speed and Safety at Scale*) e transição de sistemas legados para ecossistemas distribuídos e escaláveis.

---

### 3. Release It! Design and Deploy Production-Ready Software

* **Autor:** Michael T. Nygard
* **Publicação:** The Pragmatic Bookshelf (2ª Edição, 2018 / 1ª Edição, 2007)
* **Links:**
  * 📖 [Página Oficial (Pragmatic Bookshelf)](https://pragprog.com/titles/mne2/release-it-second-edition/)
  * 📚 [Visualização no Google Books](https://books.google.com/books/about/Release_It.html?id=UW7jAQAACAAJ)
* **Resumo:**
  Guia essencial focado em estabilidade, resiliência e prontidão operatividade em produção de sistemas distribuídos:
  * **Estudos de Caso:** Análise detalhada de falhas reais em ambientes de grande escala (ex: travamentos em cadeias de sistemas de *check-in* aéreo provocados por vazamento de conexões em *pools* de banco de dados após *failover*).
  * **Padrões de Estabilidade (*Stability Patterns*):** Implementação prática de *Timeouts*, *Circuit Breakers*, *Bulkheads*, *Fail Fast*, *Handshaking* e desacoplamento de middlewares.
  * **Anti-padrões de Produção:** Mitigação de reações em cadeia (*chain reactions*), falhas em cascata (*cascading failures*), exaustão de threads/recursos e dependências bloqueantes.

---

### 4. FTGO Application (Pattern Repository)
* **Autor / Fonte:** Chris Richardson *(Microservices Patterns)*
* **Links:**
  * 💻 [Repositório GitHub Oficial (`microservices-patterns/ftgo-application`)](https://github.com/microservices-patterns/ftgo-application)
* **Resumo:**
  Aplicação prática de referência para demonstração de padrões de microserviços e arquiteturas orientadas a eventos. Demonstra a orquestração e coreografia de transações distribuídas através do padrão Saga, segregação de leitura e escrita com CQRS, comunicação assíncrona por mensagens e isolamento de domínios organizacionais.

---

## 🛠️ Seção 1: Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Esta seção documenta o processo iterativo de elaboração de perguntas (*prompts*), a evolução entre buscas genéricas e pesquisas ancoradas em fontes técnicas, e as lições aprendidas na extração de conhecimento via IA.

---

### 🧪 Teste 1: Comparação de Protocolos de API (Prompt Direto vs. Estruturado)

* **Prompt Inicial (Genérico):**
  > *"Qual a diferença entre REST, gRPC e GraphQL?"*
* **Resultado Obtido:** Uma resposta resumida, porém sem detalhes operacionais claros sobre payload, transporte e latência na perspectiva de backend.
* **Prompt Refinado (Com Role-Playing e Tabela):**
  > *"Atue como um Engenheiro de Software Sênior especializado em sistemas distribuídos. Com base EXCLUSIVAMENTE nas fontes do caderno, elabore uma tabela comparativa em Markdown entre REST, gRPC e GraphQL. A tabela deve conter as colunas: Protocolo de Transporte, Formato da MENSAGEM, Performance/Latência, Facilidade de Integração no Frontend e Melhor Caso de Uso. Ao final, apresente um resumo de 2 parágrafos justificando quando optar por gRPC em comunicação interna entre microsserviços."*
* **Resultado Refinado:** O NotebookLM gerou uma tabela detalhada destacando o uso de HTTP/2 e Protocol Buffers no gRPC contra o HTTP/1.1 e JSON no REST, fundamentando exatamente as vantagens de menor latência na comunicação inter-serviços.
* **Lição / Aprendizado:** Especificar o papel do assistente, delimitar as colunas da tabela e solicitar justificativas técnicas baseadas no contexto evita generalizações e foca nos pontos críticos da arquitetura.

---

### 🧪 Teste 2: Gerenciamento de Transações Distribuídas (*Saga Pattern*)

* **Prompt Inicial:**
  > *"Como resolver transações em microsserviços?"*
* **Resultado Obtido (Dificuldade/Troubleshoot):** O modelo explicou o conceito genérico de transações ACID em banco de dados único, ignorando que o ambiente era distribuído com bancos descentralizados.
* **Prompt Refinado (Focado no Problema e Restrição de Contexto):**
  > *"Considere o cenário em que cada microsserviço possui seu próprio banco de dados. Analise o material sobre Microservices Patterns presente no caderno e explique o padrão Saga (Choreography vs. Orchestration). Destaque: (1) O problema da falta de transações ACID globais, (2) Como funcionam as Ações Compensatórias em caso de falha, (3) Um fluxo de exemplo para um pedido em um e-commerce."*
* **Resultado Refinado:** Resposta precisa e dividida em tópicos, detalhando como a Saga Orquestrada utiliza um serviço central para enviar comandos de compensação quando um pagamento falha, anulando a reserva de estoque de forma assíncrona.
* **Lição / Aprendizado:** Para evitar que o modelo traga soluções de arquitetura monolítica, é indispensável explicitar as restrições do ambiente distribuído (*Database-per-Service*) e solicitar o fluxo passo a passo de rollback lógico.

---

### 🩹 Cicatrizes de Pesquisa & Troubleshooting (Resolução de Problemas)

Registro dos principais obstáculos enfrentados na interação com o NotebookLM, as causas raízes identificadas durante as consultas e as estratégias aplicadas para obter respostas precisas e alinhadas aos requisitos técnicos do projeto.

---

#### 📌 Desafio 1: Respostas Abrangentes com Alucinações de Conceitos Monolíticos

* **Dificuldade / Sintoma:** Ao questionar a IA sobre padrões transacionais, ela retornava respostas focadas em transações ACID clássicas (commit/rollback atômico), desconsiderando a natureza distribuída dos microsserviços.
* **Causa Raíz:** Prompts abertos sem restrições explícitas de arquitetura permitem que o modelo utilize conhecimentos gerais de bancos de dados relacionais monolíticos.
* **Ação Corretiva (Troubleshooting):** Inclusão obrigatória de restrições de contorno no prompt, como *"Considere o padrão Database-per-Service em um ambiente distribuído onde transações ACID de duas fases (2PC) não são recomendadas"*.

---

#### 📌 Desafio 2: Omissão de Referências e Fontes Técnicas

* **Dificuldade / Sintoma:** A IA forneceu explicações corretas sobre resiliência (ex: *Circuit Breaker* e *Bulkhead*), mas sem citar os autores ou as obras presentes no caderno de estudo.
* **Causa Raíz:** Ausência de comando explícito exigindo ancoragem do conteúdo nas fontes carregadas.
* **Ação Corretiva (Troubleshooting):** Adição de instrução de ancoragem estrita no início do prompt: *"Com base EXCLUSIVAMENTE nos livros e artigos do caderno (ex: Sandeep Kumar, Michael Nygard em 'Release It!'), explique..."*.

---

#### 📌 Desafio 3: Generalização em Análises Comparativas de Desempenho

* **Dificuldade / Sintoma:** Em comparações de comunicação de dados (REST vs. gRPC), as respostas focavam apenas em sintaxe ou facilidade de uso, omitindo o impacto no transporte e na rede (HTTP/1.1 vs. HTTP/2 e JSON vs. Protobuf).
* **Causa Raíz:** Falta de solicitação de critérios específicos e métricas de infraestrutura de backend.
* **Ação Corretiva (Troubleshooting):** Uso de prompts com delimitadores claros e colunas estruturadas, exigindo tópicos obrigatórios sobre *Protocolo de Transporte*, *Payload/Formato de Mensagem* e *Latência Inter-Serviços*.

---

### 📊 Tabela Resumo de Troubleshooting

| Desafio Encontrado | Causa Raiz Identificada | Solução Aplicada (Fix) |
| :--- | :--- | :--- |
| **Respostas Monolíticas/ACID:** Aplicação de conceitos de banco único em sistemas distribuídos. | Prompts genéricos sem restrição de contexto. | Explicitar a premissa de *Database-per-Service* e desacoplamento de dados. |
| **Falta de Ancoragem Técnica:** Conceitos sem citação dos autores do repositório. | Falta de restrição explícita de fonte no prompt. | Adicionar o comando *"Com base EXCLUSIVAMENTE nos materiais do caderno"*. |
| **Superficialidade em Comparativos:** Falta de métricas de rede e payload. | Ausência de estrutura/formato exigido na resposta. | Utilizar tabelas em Markdown especificando as colunas técnicas necessárias. |

---

## 📖 Seção 2: Miniguia de Estudo Consolidado (Entrega Final)

Este miniguia consolida o conhecimento fundamental sobre **Arquiteturas de Microsserviços, Event-Driven Architecture (EDA) e Resiliência em Produção**, estruturado para servir como referência em revisões técnicas e tomadas de decisão arquiteturais.

---

### 1. Resumos Estruturados do Assunto

#### 🚀 Equilíbrio entre Velocidade e Segurança em Escala (*Speed & Safety at Scale*)
A arquitetura de microsserviços equilibra velocidade e segurança em escala ao transformar sistemas monolíticos em uma rede de componentes autônomos, pequenos e substituíveis:
* **Pilares para Velocidade (*Speed*):** Implantação independente e substitutibilidade baseada em *Bounded Contexts*, pipelines automatizados de CI/CD para múltiplos deploys diários, autonomia de equipes alinhada à **Lei de Conway** e poliglotismo tecnológico.
* **Mecanismos para Segurança e Estabilidade (*Safety*):** Isolamento de falhas através de *Bulkheads*, padrões de resiliência (*Circuit Breakers*, *Timeouts*, retentativas com *backoff* exponencial, *Dead-Letter Queues*), proteção na borda via *API Gateway* e desacoplamento de dados via *Database-per-Service*.
* **Sustentação em Escala (*At Scale*):** Escalabilidade granular e seletiva de serviços sob demanda, comunicação assíncrona orientada a eventos (EDA) para absorção de picos de tráfego e separação de leitura/escrita via **CQRS e Event Sourcing**.

#### 🔄 Gerenciamento de Transações Distribuídas (*Saga Pattern*)
Em ecossistemas com bancos de dados descentralizados, transações ACID tradicionais de duas fases (2PC) não são recomendadas devido ao alto acoplamento e latência. O padrão **Saga** soluciona essa limitação dividindo o fluxo de negócio em uma sequência de transações locais:
* **Coreografia (*Choreography*):** Cada microsserviço reage autonomamente aos eventos emitidos pelos demais participantes e publica novos eventos. Recomendado para fluxos simples e rotineiros com foco em máximo desacoplamento.
* **Orquestração (*Orchestration*):** Um componente centralizador (Orquestrador) coordena explicitamente o fluxo de trabalho e direciona comandos para os serviços participantes. Recomendado para processos complexos, críticos ou longos.
* **Transações Compensatórias:** Em caso de falha intermediária, o sistema executa ações de compensação na ordem inversa para desfazer semanticamente o trabalho já confirmado, retornando o sistema a um estado consistente.

---

### 2. Glossário de Conceitos Fundamentais

* **Bounded Context (Contexto Delimitado):** Conceito central do *Domain-Driven Design* (DDD) que estabelece as fronteiras explícitas dentro das quais um modelo de dados e seus termos possuem significado único.
* **Database-per-Service:** Padrão arquitetural em que cada microsserviço possui o controle exclusivo sobre seu banco de dados, impedindo acessos diretos de outros serviços.
* **Saga Pattern:** Padrão de projeto para gerenciar transações distribuídas em microsserviços por meio de uma sequência de transações locais encadeadas.
* **Transação Compensatória (Compensating Transaction):** Ação lógica executada para desfazer o impacto de uma transação local já confirmada em caso de falha em etapas subsequentes de uma Saga.
* **Circuit Breaker (Disjuntor):** Padrão de resiliência que interrompe temporariamente chamadas a um serviço externo quando a taxa de erros ultrapassa um limite configurado, evitando o esgotamento de recursos.
* **Bulkhead (Compartimentação):** Técnica de isolamento de recursos (ex: pools de threads ou conexões) para evitar que a falha em uma integração consuma os recursos de todo o sistema.
* **CQRS (Command Query Responsibility Segregation):** Padrão que separa os modelos de dados e operações de leitura (*Queries*) das operações de escrita/mutação (*Commands*).
* **Event Sourcing:** Padrão de persistência em que as mudanças de estado são armazenadas como uma sequência cronológica e imutável de eventos de domínio.
* **Dead-Letter Queue (DLQ):** Fila de mensagens secundária utilizada para armazenar e isolar mensagens que não puderam ser processadas com sucesso após múltiplas tentativas.
* **Idempotência:** Propriedade de uma operação que garante que executá-la múltiplas vezes produzirá o mesmo efeito de executá-la uma única vez.

---

### 3. Prompts Reutilizáveis para Futuras Revisões

#### 🟢 Prompt 1: Análise Comparativa de Padrões Arquiteturais

Atue como Engenheiro de Software Sênior especializado em Arquitetura Distribuída.
Com base nas boas práticas de microsserviços, analise o seguinte cenário de negócio: [INSERIR CENÁRIO/REQUISITO].
Elabore uma tabela comparativa em Markdown avaliando a aplicação do padrão [PADRÃO A: ex: Saga Orquestrada] versus [PADRÃO B: ex: Saga Coreografada].
A tabela deve conter as colunas: Nível de Acoplamento, Complexidade Operacional, Estratégia de Observabilidade, Facilidade de Testes e Melhor Caso de Uso.
Ao final, forneça uma recomendação técnica fundamentada em resiliência e escalabilidade.

### 🟡 Prompt 2: Design de Resiliência e Contenção de Falhas em Produção

Atue como Engenheiro de Confiabilidade .
Com base nos padrões de resiliência da literatura técnica (como 'Release It!' de Michael Nygard), projete uma arquitetura defensiva para o seguinte problema: [DESCREVER FALHA].
Especifique detalhadamente:
1. Parâmetros recomendados para Timeout e Retries com Backoff Exponencial.
2. Configuração do Circuit Breaker (Limites de falha, tempo no estado Open e Half-Open).
3. Estratégia de Bulkhead e isolamento de recursos.
4. Mecanismo de Fallback para manter o fluxo do usuário ativo.

🔴 Prompt 3: Modelagem de Eventos e Governança de Domínio.

Atue como Arquiteto de Soluções especializado em Event-Driven Architecture.
Para o contexto delimitado de [INSERIR DOMÍNIO]:
1. Mapeie os principais Eventos de Domínio no tempo verbal passado (ex: PagamentoAprovado, FaturaEmitida).
2. Escreva o Schema JSON do evento principal incluindo cabeçalhos essenciais (Correlation ID, Event ID, Timestamp e Source).
3. Descreva a estratégia para tratamento de mensagens duplicadas ou fora de ordem garantindo a Idempotência nos consumidores.
