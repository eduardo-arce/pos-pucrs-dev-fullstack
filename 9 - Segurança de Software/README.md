# Segurança no Desenvolvimento de Software

## Sobre a disciplina

A cadeira apresenta os fundamentos da **segurança de software** com foco na realidade do desenvolvedor: criptografia aplicada, protocolos seguros, análise de riscos, modelagem de ameaças, autenticação/autorização e as vulnerabilidades mais recorrentes em aplicações web. O objetivo é formar um profissional que pensa em segurança desde o design, e não como verniz aplicado no final.

## Docentes

- **Moisés Brandalise** — professor convidado, especialista em Segurança da Informação em instituição financeira, com 25 anos de experiência em infraestrutura, desenvolvimento, segurança na indústria de mídia e proteção de dados pessoais.
- **Avelino Francisco Zorzo** — doutor pela University of Newcastle Upon Tyne, com pós-doutorado em segurança pela mesma instituição; professor titular da Escola Politécnica da PUCRS e Coordenador de Programas Profissionais da área de Computação da CAPES/MEC.

## Organizações que definem os padrões de segurança

A disciplina começa mapeando quem escreve as "regras do jogo":

- **ISO** — Organização Internacional de Normalização.
- **W3C** — World Wide Web Consortium.
- **OWASP** — Open Web Application Security Project.
- **NIST** — National Institute of Standards and Technology.
- **IETF** — Internet Engineering Task Force.
- **PCI SSC** — Payment Card Industry Security Standards Council.

## Risco: o acrônimo CIO

Para que exista um risco concreto, três elementos precisam coexistir — o **CIO** da segurança:

1. **Capacidade** — o atacante tem habilidade técnica para explorar?
2. **Iniciativa** — há motivação para agir?
3. **Oportunidade** — o ambiente permite a ação?

Remover qualquer um dos três reduz o risco efetivo.

## Métodos de criptografia

### Simétrica

Usa **a mesma chave** para cifrar e decifrar. É rápida e eficiente — ideal quando a confidencialidade é a prioridade e a chave pode ser protegida. Sua grande limitação é o gerenciamento do segredo: se a chave vaza, a segurança ruiu.

Cenários típicos: transações financeiras, comunicações militares e segurança de rede.

#### AES-256

Variante do **AES** que usa chave de 256 bits, considerado padrão robusto para proteção de dados sensíveis.

### Assimétrica

Também chamada de **criptografia de chave pública**. Opera com um par:

- **Chave pública** — amplamente distribuída; usada para **cifrar** o que será enviado ao dono da chave.
- **Chave privada** — segredo exclusivo do dono; usada para **decifrar** o conteúdo recebido.

Resolve o problema da distribuição de chaves da criptografia simétrica, ao custo de ser computacionalmente mais cara.

### Funções hash

Transformam um conteúdo de tamanho variável em uma sequência de tamanho fixo. São **de mão única** — a ideia é garantir integridade, não recuperar o dado original.

## Modelo OSI

A segurança precisa ser entendida nas diferentes camadas da rede. A disciplina revisita o modelo clássico:

| Camada | Nome | Exemplo |
|---|---|---|
| 7 | Aplicação | Interface com aplicativos |
| 6 | Apresentação | Formatos / criptografia |
| 5 | Sessão | Controle de sessões entre aplicativos |
| 4 | Transporte | Conexão entre hosts / portas |
| 3 | Rede | Endereço lógico / roteadores |
| 2 | Enlace | Endereço físico / switches e hubs |
| 1 | Física | Hardware |

A unidade viajada também muda conforme a camada: dados nas camadas 5-7, segmentos na 4, pacotes na 3, frames na 2 e bits na 1.

## Protocolos e portas relevantes

- **HTTPS / SSL / TLS** — comunicação segura em navegadores.
- **LibSignal** — biblioteca de criptografia ponta-a-ponta usada em apps de mensageria.
- **SMTPS** — e-mail seguro, tipicamente nas portas **465** e **587**.

## Análise de risco, passo a passo

A disciplina propõe um roteiro prático:

1. Analisar ameaças.
2. Identificar ativos.
3. Avaliar vulnerabilidades.
4. Estimar impacto.
5. Classificar os riscos.
6. Construir um plano de mitigação.
7. Monitorar continuamente.

## Modelagem de ameaças com STRIDE

STRIDE é um acrônimo que cobre seis famílias clássicas de ameaças:

| Letra | Ameaça | Descrição |
|---|---|---|
| **S** | Spoofing | Falsificação de identidade. |
| **T** | Tampering | Violação/adulteração de dados. |
| **R** | Repudiation | Negação de ter realizado uma ação. |
| **I** | Information Disclosure | Vazamento de informações. |
| **D** | Denial of Service | Negação de serviço. |
| **E** | Elevation of Privilege | Escalonamento de privilégios. |

## Autenticação, autorização e o OWASP Top 10

A disciplina trata **autenticação** como o ato de verificar identidade, distinto da **autorização** (o que o usuário pode fazer). Conecta-se ao **OWASP Top 10** — injeção, autenticação quebrada, exposição de dados sensíveis etc. — e reforça a conformidade com a **LGPD** no tratamento de dados pessoais.

## Boas práticas aplicadas

- Análise estática e dinâmica do código.
- Testes de invasão (pentest).
- Gerenciamento cuidadoso de chaves e segredos.
- Uso de ferramentas da OWASP e análise contínua de qualidade com **Sonar**.
