# Arquitetura de Microsserviços

## Sobre a disciplina

Imersão na arquitetura de microsserviços: como particionar aplicações em serviços autônomos, distribuir responsabilidades, lidar com comunicação assíncrona via filas e explorar cenários _serverless_. O foco está em sistemas distribuídos **escaláveis, ágeis e resilientes** — com olhar honesto sobre os _trade-offs_ envolvidos.

## Docentes

- **Vinícius Soares** — Head de Tecnologia, entusiasta de Computação Distribuída; experiência em Java, arquitetura de sistemas e nuvem; liderou projetos SOA/Microsserviços em comunidades open-source; palestrante em Devoxx, TDC e Campus Party; empreendedor envolvido com formação de +1000 pessoas em TI.
- **Luis Fernando Planella Gonzalez** — doutor em Ciência da Computação pela PUCRS, desenvolvedor/arquiteto Java desde 1999, certificado Sun, entusiasta de software livre.

## Do SOA aos microsserviços

> **SOA** — abordagem arquitetural corporativa que permite criar serviços de negócio **interoperáveis**, reutilizados e compartilhados entre aplicações e empresas.

Benefícios frequentemente associados:

- Desacoplamento entre consumidores e provedores.
- Reúso de funcionalidades.
- Infraestrutura de plataforma padronizada.

Microsserviços herdam parte dessa filosofia, porém com granularidade mais fina e forte ênfase em autonomia de times e de deploy.

## Frases que norteiam a disciplina

Alguns "mantras" repetidos para fixar princípios culturais:

- **Two-pizzas team** — _“Se um time não pode ser alimentado por duas pizzas, ele é grande demais para discutir ideias.”_ (Jeff Bezos)
- _“Everything fails all the time.”_ (Werner Vogels) — reconhecer que falhas são inevitáveis e projetar para isso.
- **Lock-in** — cenário em que se adquire uma tecnologia e fica difícil trocá-la; decisões arquiteturais devem ponderar esse risco.
- **Onboarding** — processo de ambientação de novos integrantes; um microsserviço bem projetado reduz atrito nessa fase.

## Boas práticas de modelagem

- Modelar serviços em torno de **domínios de negócio** (DDD, _bounded contexts_).
- **Descentralizar** tanto a decisão técnica quanto as equipes.
- Evitar compartilhamento de código ou banco de dados entre serviços.
- Projetar **APIs bem definidas** e estáveis.
- Perseguir _loose coupling_ com _high cohesion_.
- Linguagem ubíqua e **Event Storming** para mapear comandos, agregações e fronteiras.

## Escala e autonomia

A escalabilidade em microsserviços pode ser **horizontal** (mais réplicas) ou **vertical** (mais capacidade por instância). Em paralelo, equipes pequenas e autônomas entregam mais rápido, com ciclos independentes de deploy.

## Comunicação assíncrona

Em vez de acoplar serviços via chamadas síncronas, a disciplina reforça o uso de **filas** e **eventos**.

### Produtor-Consumidor

- **Pub/Sub (Publisher/Subscriber)** — serviço de mensagens em tempo real gerenciado que permite o envio e o recebimento entre aplicações independentes.
- **Message Broker** — sistema especializado em recepção e envio de mensagens que:
  - desconhece detalhes dos _publishers/subscribers_;
  - persiste mensagens;
  - reentrega em caso de falha do consumidor.

Exemplos comuns: **Kafka, ActiveMQ, RabbitMQ, Amazon MQ, Google Pub/Sub, Azure Service Bus**.

### Garantias de entrega

Três semânticas clássicas aparecem na discussão:

- **At most once** — entrega no máximo uma vez (aceita perdas).
- **At least once** — entrega pelo menos uma vez (aceita duplicatas).
- **Exactly once** — uma e exatamente uma vez (mais difícil e mais caro).

### Protocolo AMQP

> **AMQP (Advanced Message Queuing Protocol)** é um padrão aberto para mensageria entre aplicações. Define como as mensagens devem ser enviadas, recebidas e roteadas em uma rede, com confiabilidade e segurança. É a base de brokers como RabbitMQ e Azure Service Bus.

## Orquestração × Coreografia

- **Orquestração** — um coordenador central dita os passos.
- **Coreografia** — cada serviço reage a eventos, sem um maestro único.

Em transações distribuídas, o padrão **Saga** é recorrente para manter consistência sem bloqueios globais.

## Trade-offs sinceros

Microsserviços resolvem problemas, mas introduzem outros:

- Complexidade operacional muito maior do que um monolito.
- Consistência **eventual** (teorema CAP).
- Necessidade de resiliência explícita — **circuit breakers**, _retries_, _timeouts_.

## Serverless e FaaS

Aplicações serverless:

- Ainda precisam de um servidor para rodar — só que o desenvolvedor **não o conhece**.
- Costumam estar associadas ao modelo **FaaS (Function as a Service)**.

## Exercícios

Atividades conduzidas em aula para materializar os conceitos:

- **exemplo-knative** — uso do Knative para construir aplicações orientadas a eventos em Kubernetes.
- **exemplo-microsservicos** — esqueleto de uma arquitetura multi-serviço.
- **produtor-consumidor** — dois cenários práticos:
  - **fila** — _message queue_ com produtor e consumidor.
  - **tópico** — pub/sub com múltiplos assinantes.

## Ferramental complementar

- **Flyway** — versionamento e gerenciamento de schemas de banco.
- **RabbitMQ** — broker para prática de filas e tópicos.
- **DotEnv** — gerenciamento de variáveis de ambiente em projetos TypeScript.
- **Knative** — solução open-source para apps serverless e orientados a eventos sobre Kubernetes.
- **Docker**, **Kubernetes**, **Spring Boot / Node.js** e **AWS Lambda** compõem o ferramental citado.

## Leitura de apoio

- *Domain-Driven Design* — Eric Evans, referência central para o raciocínio de fronteiras e linguagem ubíqua.
