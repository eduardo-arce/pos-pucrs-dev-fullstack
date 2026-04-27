# Bancos de Dados Não Relacionais (NoSQL)

## Sobre a disciplina

A cadeira abre espaço para os bancos **NoSQL**, partindo de uma revisão do contexto de **Big Data** — volume, velocidade, variedade, validade, volatilidade e valência — e avançando para os modelos de armazenamento que fogem ao paradigma relacional. O aluno entra em contato com clusters, agregados, distribuição, tolerância a falhas, _sharding_ e passa por exercícios práticos nos quatro grandes formatos NoSQL.

## Docentes

- **Vinícius Frantz Kroth** — professor convidado, especialista em SOA, Microservices, MongoDB, Redis, Elasticsearch e AWS.
- **Eduardo Henrique Pereira de Arruda** — professor da PUCRS, fundador da Doc.Space, com atuação em modelagem e sistemas.

## Do relacional ao NoSQL: revisão rápida

Antes de mergulhar nas novas tecnologias, a disciplina rememora as **formas normais** para deixar claro o que se está deixando para trás (ou flexibilizando):

| Forma Normal | Regra central |
|---|---|
| 1FN | Cada coluna contém um único valor atômico (sem listas dentro de uma célula). |
| 2FN | Após a 1FN, atributos não-chave devem depender totalmente da chave primária (sem dependências parciais). |
| 3FN | Eliminar dependências transitivas — atributos não-chave dependem _só_ da PK. |

## Teorema CAP

Em sistemas distribuídos é impossível garantir simultaneamente as três propriedades abaixo; sempre há uma troca:

- **Consistency** — todos os clientes enxergam os mesmos dados ao mesmo tempo, independentemente do nó consultado. Exige replicação antes de confirmar a escrita.
- **Availability** — toda requisição recebe uma resposta válida, mesmo que algum nó esteja fora.
- **Partition Tolerance** — o cluster segue operando mesmo com falhas de comunicação entre nós.

## ACID × BASE

Enquanto os relacionais priorizam ACID, muitos NoSQL se orientam pelo modelo **BASE** — relaxam a consistência imediata para ganhar disponibilidade e escalabilidade.

**ACID** (clássico):

- **Atomicidade** — a transação ou acontece por inteiro ou é desfeita.
- **Consistência** — a integridade estrutural nunca é comprometida.
- **Isolamento** — transações concorrentes não interferem entre si.
- **Durabilidade** — uma vez confirmada, a transação persiste mesmo após falhas.

**BASE** (NoSQL):

- **Basically Available** — disponibilidade dos dados espalhando/replicando pelos nós do cluster.
- **Soft state** — os valores podem mudar com o tempo; o sistema não impõe consistência imediata.
- **Eventually consistent** — a consistência é alcançada _eventualmente_; enquanto isso, leituras podem não refletir a realidade mais recente.

### Conceitos adicionais

- **Sharding** — divisão horizontal dos dados entre servidores para distribuir leitura e escrita.
- **SPOF (Single Point of Failure)** — componente crítico cuja falha derruba o sistema inteiro. NoSQL costuma evitar SPOFs via arquitetura peer-to-peer.

## Os quatro modelos (e um primo distante)

### Document — MongoDB

Armazena documentos em formato **BSON** (JSON binário) agrupados em _collections_. Destaques:

- Esquema flexível, ideal para modelos que evoluem.
- Indexação avançada (composta, geoespacial, textual).
- Escalabilidade horizontal via sharding automático.
- **Aggregation Framework** para pipelines de transformação.
- **Replica sets** para alta disponibilidade.
- **Organização**: _databases_ → _collections_ → _documents_ (analogia a bases → tabelas → linhas).

Casos de uso comuns: perfis de usuário, CMS, analytics em tempo real. Empresas como eBay, Adobe e Forbes são citadas.

### Key-Value — Redis

In-memory, armazena pares chave-valor com estruturas de dados ricas.

- Latência sub-milissegundo (dados na RAM).
- Suporta strings, listas, sets, sorted sets, hashes, streams e módulos (JSON, grafos).
- Persistência opcional via RDB (snapshot) ou AOF (append-only).
- Pub/Sub, transações, scripting Lua e clustering.
- Single-threaded no caminho principal — simples e otimizado para throughput.

Casos de uso: cache de sessão, leaderboards, filas de tarefas. Usado por Twitter, GitHub e StackOverflow.

### Columnar — Apache Cassandra

Wide-column store distribuído e altamente escalável.

- Arquitetura **peer-to-peer** descentralizada, sem SPOF.
- Escala horizontalmente para petabytes.
- Replicação automática entre nós e datacenters.
- **Consistência tunável** via PACELC.
- Otimizado para cargas intensivas em escrita (IoT, logs).
- Linguagem **CQL** parecida com SQL, mas sem `JOIN`.

Vocabulário específico do Cassandra:

- **Keyspace** — equivalente ao "database" relacional.
- **Table** — o objeto físico que guarda os dados.
- **Primary Key** — identificador único, podendo ser composto.
- **Partition Key** — parte da PK que define em qual partição o dado vai morar.
- **Clustering Key** — parte da PK que define a ordenação dentro da partição.

Adotado por Netflix, Apple e Uber.

### Graph — Neo4j

Banco nativo de grafos, focado em _relacionamentos_ entre entidades.

- Armazena nós, relacionamentos e propriedades.
- **Cypher** — linguagem declarativa para consultas como caminhos mais curtos.
- **ACID-compliant**, com consistência forte.
- Biblioteca de algoritmos de grafos (PageRank, centralidade, detecção de comunidades).
- Integração com frameworks de IA (Graph Data Science Library).

Casos de uso: recomendações em redes sociais, detecção de fraudes, análise de redes de telecom. Adotado pela NASA, Airbnb e Walmart.

### Bônus — ScyllaDB

Alternativa ao Cassandra escrita em C++ com arquitetura **shard-per-core** sobre o framework **Seastar**:

- Mantém compatibilidade com CQL, drivers e formato SSTable.
- Latências sub-milissegundo e alta vazão com menos hardware.
- Auto-otimização (balanceamento, compaction incremental).
- Ótimo para time-series e telemetria em alta ingestão.

Empresas como Discord, Comcast e Bloomberg utilizam.

## Exercícios

Coleção de roteiros usados nas práticas em aula:

- **Cassandra** — roteiro com scripts CQL.
- **MongoDB** — exemplos de CRUD e agregações.
- **Neo4j** — consultas em Cypher.
- **Redis** — operações com as estruturas nativas.

## Ferramentas complementares

- **Astah** — modelagem UML usada em algumas atividades.
- **BRModelo** — para traçar modelos complementares quando necessário.
