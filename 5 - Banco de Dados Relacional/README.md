# Bancos de Dados Relacionais

## Sobre a disciplina

Primeiro contato estruturado com **bancos de dados relacionais** dentro do curso. A disciplina passa pela modelagem conceitual (ER), pela derivação do modelo lógico, pela escrita de SQL (DDL + DML) e pelo mapeamento objeto-relacional (ORM) usando Python — do diagrama no papel até a aplicação conversando com o banco.

## Docentes

- **Claudio Bonel** — professor convidado, especialista em Engenharia e Análise de Dados.
- **Azriel Majdenbaum** — professor da PUCRS com atuação no tema.

## Glossário fundamental

Antes de escrever qualquer SQL, a disciplina fixa alguns termos que são referenciados durante todo o curso:

- **Banco de dados** — coleção de informações coerentes e inter-relacionadas, armazenadas em um sistema computacional.
- **SGBD (Sistema de Gerenciamento de Banco de Dados)** — sistema que permite criar e administrar um banco de dados.
- **Metadados** — “dados sobre os dados”; descrevem a estrutura e as características do próprio banco.
- **Minimundo** — o recorte do mundo real que a base vai representar.
- **Modelo de dados** — peça central; garante correlação, coerência e abstração.
- **Cardinalidade** — grau da relação entre entidades. Pode ser _um-para-um_, _um-para-muitos_ ou _muitos-para-muitos_.

## Modelagem: do conceito ao físico

A modelagem é trabalhada em três camadas complementares:

1. **Modelo Entidade-Relacionamento (MER)** — descrição textual dos objetos do negócio, seus atributos e relações.
2. **Diagrama Entidade-Relacionamento (DER)** — representação gráfica do MER.
3. **Modelo Lógico e Físico** — tradução da modelagem conceitual para tabelas, colunas, tipos e índices em um SGBD específico.

No DER, as convenções clássicas se mantêm:

- **Entidade** — representada por retângulo; agrupa informações sobre um conceito.
- **Atributo** — representado por elipse; descreve características da entidade.
- **Relacionamento** — representado por losango; associa entidades.

## Restrições de integridade (constraints)

Regras que limitam os dados aceitos em uma tabela, garantindo consistência:

| Constraint | Papel |
|---|---|
| `PRIMARY KEY` | Identifica unicamente cada linha da tabela. |
| `FOREIGN KEY` | Estabelece relacionamento entre tabelas. |
| `UNIQUE` | Garante que o valor seja único na coluna. |
| `NOT NULL` | Impede valores ausentes. |
| `CHECK` | Valida expressões sobre os valores inseridos. |

Um conceito interessante é o de **surrogate key** (chave substituta/sintética) — identificador artificial sem significado no domínio, criado exclusivamente para identificar a linha. Exemplos comuns: UUIDs, seriais autoincrementais.

## SQL na prática

A disciplina cobre os dois subconjuntos clássicos da linguagem:

- **DDL (Data Definition Language)** — `CREATE`, `ALTER`, `DROP` para estruturar objetos.
- **DML (Data Manipulation Language)** — `SELECT`, `INSERT`, `UPDATE`, `DELETE` para operar sobre os dados.

Tópicos mais avançados também são trabalhados:

- **JOINs** (`INNER`, `OUTER`, `CROSS`) para combinar tabelas.
- **`GROUP BY` + `HAVING`** e subconsultas.
- **Funções agregadas** — `COUNT`, `SUM`, `AVG`, `MAX`, `MIN`.
- **Índices** e **sequências** para performance e chaves auto-incrementais.
- **Integridade referencial** mantida via FKs.

## ORM com Python

O módulo de ORM introduz o **SQLAlchemy**, permitindo mapear classes Python a tabelas do banco. Com isso, CRUD, relacionamentos e queries passam a ser expressos em código orientado a objetos, sem abrir mão do SQL quando ele se faz necessário.

## Ferramentas

- **SQLAlchemy** (ORM em Python).
- **BRModelo** para modelagem conceitual e lógica.
- **Oracle Live SQL** e **SQLite** para prática sem setup local.
- **Draw.io** para diagramação.

## Leituras de apoio

- BONEL, Claudio. *Metodologia e Engenharia de Requisitos para Projetos de Business Intelligence*. Clube de Autores, 2021.
- COPELAND, Rick. *Essential SQLAlchemy*. 2ª ed. O'Reilly Media, 2016.
- ELMASRI, Ramez; NAVATHE, Shamkant B. *Sistemas de Banco de Dados*. 7ª ed. Pearson, 2018.
