# Programação Orientada a Objetos (POO)

## Sobre a disciplina

Disciplina dedicada a enxergar a construção de software sob a ótica de **objetos**. Usando JavaScript (ES6+) como laboratório, o aluno se apropria do raciocínio orientado a objetos — pensar em termos de entidades, responsabilidades e colaborações — e aprende a traduzir isso para código idiomático.

> Um **paradigma** é, em essência, “uma forma de fazer algo”. Enquanto a programação funcional coloca o foco nas funções, o paradigma OO organiza o código em torno de objetos que modelam o mundo real.

## Docentes

- **Alessandro Valério Dias** — mestre em Administração e Negócios (PUCRS), especialista em Gerenciamento de Projetos de TI e Informática na Educação. Bacharel em Ciência da Computação e em Psicologia. Analista de sistemas na PUCRS e professor em cursos de Análise/Desenvolvimento de Sistemas e Ciência da Computação no UniRitter.
- **Edson Ifarraguirre Moreno** — doutor em Ciência da Computação, coordena laboratórios na PUCRS com atuação em hardware.

## Os quatro pilares da POO

A disciplina ancora as discussões nos conceitos clássicos, sempre com exemplos práticos em JavaScript:

- **Abstração** — identificar o que é essencial em um problema e descartar detalhes irrelevantes.
- **Encapsulamento** — agrupar atributos e métodos atrás de uma interface bem definida. O consumidor precisa saber o _que_ o objeto faz, não _como_.
- **Herança** — reaproveitar comportamentos generalizados/especializados através de relações do tipo “é-um”.
- **Polimorfismo** — permitir que um mesmo método se comporte de forma diferente conforme o objeto que o invoca (sobrescrita).

Além desses, emerge um quinto conceito específico do ecossistema JS:

- **Protótipo** — mecanismo nativo de herança entre objetos, fornecendo atributos e métodos sem depender (necessariamente) de classes.

## Evolução dos paradigmas

A disciplina também contextualiza a POO como parte de uma linha evolutiva: **estruturada → procedural → orientada a objetos**, mostrando por que cada etapa surgiu e quais problemas tentou resolver.

## Recursos modernos do JavaScript explorados

- Sintaxe de classes (ES6), construtores, `this` e `new`.
- Níveis de visibilidade usando o prefixo `#` para atributos/métodos privados.
- Arrow functions e funções de alta ordem (`map`, `filter`, `reduce`, `forEach`).
- `async/await`, `Promise` e o sistema de módulos (`import/export`).
- Trabalho com JSON, tratamento de exceções (`try/catch`) e desestruturação.

### Visibilidade com `#`

Um dos pontos reforçados em aula é como obter atributos verdadeiramente privados em classes JS:

```javascript
class Pessoa {
  #id;

  constructor(nome, idade, cpf) {
    this.nome = nome;
    this.idade = idade;
    this.#id = cpf;
  }

  getCpf = () => this.#id.toString();
}
```

### Diferença entre `for-in` e `for-of`

Um detalhe que costuma gerar confusão é como cada estrutura itera sobre arrays:

```javascript
var a = [];
a[0] = 'a';
a[1] = 'b';
a[9] = 'c';

console.log(a.length); // 10

for (let val in a) {
  console.log(' --> ' + val); // imprime os índices inicializados: 0, 1 e 9
}

for (let val of a) {
  console.log(' --> ' + val); // imprime os valores, incluindo undefined nas posições vazias
}
```

Em resumo: `for-in` percorre **chaves enumeráveis**, `for-of` percorre **valores iteráveis**.

## Exercícios

Atividades realizadas em aula para sedimentar os conceitos:

- **classes** — criação de classes e demonstração de polimorfismo em JavaScript.
- **funcoesConstrutoras** — uso do padrão clássico de funções construtoras, anterior à sintaxe `class`.
- **metodo_estatico** — declaração e utilização de métodos estáticos.
- **visibilidade_let** — exploração do escopo de bloco do `let` e sua relação com visibilidade.

## Leituras de apoio

Três referências clássicas citadas em aula:

- *Concepts of Programming Languages* — Robert W. Sebesta.
- *Clean Code* — Robert Cecil Martin.
- *Refactoring* — Martin Fowler.
