# DevOps Avançado e Pipelines

## Sobre a disciplina

Complemento natural da disciplina introdutória: aqui o foco se desloca da construção de imagens Docker para a **automação ponta-a-ponta** do ciclo de entrega. Entram em cena entrega contínua (CD), orquestração de containers, infraestrutura como código (IaC) e observabilidade. A meta é deixar o software pronto para chegar ao usuário rapidamente, com previsibilidade e segurança.

## Docentes

- **Cássio A. W. Trindade** — arquiteto de software na PUCRS, com mais de 30 anos de experiência em desenvolvimento e DevOps.
- **Marcelo Veiga Neves** — doutor em Ciência da Computação, especialista em redes, alto desempenho e sistemas embarcados.

## DevOps como cultura

Os professores reforçam um ponto importante: DevOps **não é ferramenta, cargo ou sinônimo de CI/CD**.

> DevOps é uma **cultura** de entrega contínua de produtos digitais com valor, que combina as áreas de _development_ e _operations_ e se apoia nas melhores metodologias, práticas e ferramentas da TI.

## Integração e Entrega Contínuas (CI/CD)

> **Integração contínua** é a prática de automatizar o build, os testes e o deploy de todos os componentes, de forma contínua.

CI/CD nasce da combinação de várias técnicas, entre elas:

### Versionamento de código

Git (padrão atual), SVN e CVS (legados) como registradores de histórico de mudanças.

### Automação de build/compilação

| Ecossistema | Ferramenta típica |
|---|---|
| JavaScript/Node | npm, yarn |
| C/C++ | Autotools, Make |
| Java | Ant, Maven, Gradle |
| .NET | NAnt, MSBuild |

### Automação de testes

| Categoria | Exemplos |
|---|---|
| Unitários | Mocha, Chai (JS), JUnit (Java) |
| Funcionais/E2E | Cypress (JS), Selenium (Java) |
| Desempenho/estresse | JMeter |

## Tópicos avançados trabalhados

- **Orquestração de containers** — Kubernetes, ECS e EKS para subir e coordenar múltiplos serviços.
- **Infraestrutura como Código (IaC)** — Terraform para provisionar recursos e Ansible para configuração.
- **Serverless e Fargate** — rodar código sem gerenciar servidores.
- **Observabilidade nos três pilares** — métricas, logs e _tracing_, compondo a visão completa do comportamento do sistema.
- **Feedback contínuo** e práticas estruturadas de _troubleshooting_.
- **Pipelines** em GitHub Actions, Jenkins e AWS CodePipeline.

## Exercícios

- **app-status-ip** — aplicação usada em aula para exercitar o fluxo completo: containerização, deploy e inspeção de status/IP em ambientes orquestrados.

## Ferramentas utilizadas ao longo das aulas

GitHub Actions, Docker Compose, Kubernetes, Terraform, Ansible, Jenkins e uma coleção de serviços da AWS — ECS, EKS, Fargate, CloudWatch e Elastic Beanstalk — formam a caixa de ferramentas do aluno ao final do módulo.
