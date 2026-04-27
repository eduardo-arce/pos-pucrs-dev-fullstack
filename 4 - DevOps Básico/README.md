# Introdução ao DevOps

## Sobre a disciplina

Porta de entrada para a cultura DevOps dentro do curso. A proposta é unir a perspectiva de **Dev** (desenvolvimento) com a de **Ops** (operações) por meio de práticas que favorecem colaboração, automação e entregas de menor risco. O aluno sai da disciplina capaz de criar imagens Docker, subir containers, entender pipelines e aplicar os princípios de aplicações modernas em nuvem.

## Docentes

- **Fabrício Veronez** — fundador da Formação KubeDev, +13 anos como desenvolvedor e arquiteto, criador de conteúdo sobre containers e DevOps em veronez.dev e YouTube.
- **Marco Aurélio Souza Mangan** — doutor em Engenharia de Sistemas e Computação pela UFRJ, professor da Faculdade de Informática da PUCRS e do Senac, com atuação em engenharia de software, linguagens de programação e CSCW.

## O que é DevOps?

> DevOps é um conjunto de práticas que integra os times de desenvolvimento e operações, buscando maior colaboração, automação e eficiência tanto para o produto quanto para o processo de entrega.

A filosofia é estruturada em três “modos” (os _Three Ways_ de Gene Kim):

1. **Fluxo** — analisar e otimizar processos, apoiar testes automatizados, integração contínua e deploys contínuos, reduzindo o risco das entregas.
2. **Feedback** — coletar métricas, habilitar observabilidade, adotar testes A/B e usar o feedback dos resultados para replanejar.
3. **Aprendizado contínuo e experimentação** — aprender com os erros, promover experimentação controlada, disseminar conhecimento e padronizar o que deu certo.

Dois conceitos aparecem ao longo da discussão:

- **Observabilidade** — na teoria do controle, é a capacidade de inferir o estado interno de um sistema a partir das suas saídas visíveis.
- **Teste A/B** — técnica em que duas variações (A e B) são comparadas aleatoriamente em um experimento controlado, sendo uma o controle e a outra o tratamento.

## Twelve-Factor App

Conjunto de boas práticas criado por engenheiros da Heroku para aplicações **SaaS** modernas, escaláveis e portáveis. A disciplina revisa os 12 fatores:

| # | Fator | Essência |
|---|---|---|
| 1 | Base de código única | Um repositório versionado por aplicação. |
| 2 | Dependências explícitas | Declaradas via Maven, Gradle, npm, pip etc. |
| 3 | Configuração no ambiente | Em variáveis de ambiente, nunca no código-fonte. |
| 4 | Serviços externos como recursos | Consumidos via URLs/conexões desacopladas. |
| 5 | Build, Release, Run | Etapas separadas para garantir previsibilidade. |
| 6 | Processos independentes | Stateless e auto-contidos. |
| 7 | Port binding | A aplicação expõe seus próprios serviços por porta. |
| 8 | Concorrência | Escalar adicionando processos leves, não threads. |
| 9 | Disposability | Inicializar e encerrar rapidamente e de forma graciosa. |
| 10 | Dev/Prod parity | Ambientes parecidos para evitar surpresas. |
| 11 | Logs como fluxo de eventos | Escritos em `stdout`, tratados por sistema externo. |
| 12 | Processos administrativos | Executados isoladamente, sem afetar o runtime principal. |

## Containers na prática

O container é apresentado como unidade de empacotamento padronizada que inclui tudo o que a aplicação precisa para rodar. A disciplina ressalta suas características:

- Isolamento entre processos.
- Controle de ciclo de vida.
- **Idempotência** — operação que leva ao mesmo resultado não importa quantas vezes seja executada.
- Portabilidade entre ambientes.
- Confiabilidade de comportamento.

Duas entidades fundamentais:

- **Imagem** — o elemento-base usado para instanciar containers.
- **Container** — ambiente de execução padronizado construído a partir de uma imagem.

## Pipelines

> Pipeline é uma sequência automatizada que orquestra build, testes e implantação do software, conectando codificação e produção e fomentando a colaboração entre dev e ops.

## Exercícios

- **ubuntu-curl** — descrição de uma imagem Docker que cria um Ubuntu com utilitários (primeiro contato com `Dockerfile`).
- **conversao-temperatura** — projeto Node.js usado para exercitar todo o fluxo: build da imagem, versionamento de tags (`v1`, `v2`), execução local, testes e publicação no Docker Hub.
- **app-status-ip** — laboratório adicional com foco em inspecionar status e IPs dentro de um ambiente conteinerizado.

### Fluxo executado no laboratório `conversao-temperatura`

O exercício principal passa por:

1. `npm install` para preparar o projeto Node.
2. Execução local via `node server.js`.
3. Escrita de um `Dockerfile` enxuto e construção da imagem: `docker build -t usuario/conversao-temperatura:v1 .`.
4. Inspeção do cache de build ao alterar apenas um comentário no `server.js` — evidência da camada de cache do Docker.
5. Execução do container mapeando a porta: `docker container run -d -p 8080:8080 usuario/conversao-temperatura:v1`.
6. Atualização da versão do Node e geração de uma **v2** com imagem mais enxuta.
7. Publicação de ambas as tags no Docker Hub com `docker push`.

## Ferramental mencionado

Ao longo das aulas aparecem ferramentas como Git, GitHub, Maven, Gradle, npm, Yarn, GitHub Actions, Jenkins, Travis e Docker — um ecossistema amplo para que o aluno comece a compor seu repertório DevOps.

## Leitura de apoio

- *The DevOps Adoption Playbook* — Sanjeev Sharma.
