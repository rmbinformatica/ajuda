---
description: >-
  Estruturas de sintaxe básicas do JavaScript.
---
## Estruturas de sintaxe básicas do JavaScript

### Comentários em JavaScript

Comentários são blocos de texto que não são interpretados pela linguagem de programação. Eles são utilizados para documentar o código, explicar o que está sendo feito, ou para desabilitar uma parte do código.

```javascript
// Isto é um comentário de uma linha

/*
Isto é um comentário
de múltiplas linhas
*/
```

### Declaração de variáveis em JavaScript

```javascript
// Variável
var var = "JavaScript";
```

### Declaração de arrays em JavaScript

```javascript
// Array
var array = [1, "JavaScript", false, [2, 3, 4]];

// Array (usando construtor)
var array = new Array(1, "JavaScript", false, [2, 3, 4]);
```

### Ler input do usuário, atribuir a uma variável e depois imprimir na tela em JavaScript

```javascript
// Ler um input do usuário e guardar na variável nome
var nome = prompt("Qual é o seu nome?");

// Imprimir a variável nome
alert("Olá, " + nome + "!");
```

## Estruturas de seleção em JavaScript

### if em JavaScript

```javascript
// Testar uma expressão usando if
if (EXPRESSÃO) {
  // Executar este bloco se a expressão for verdadeira
}

// Testar uma expressão usando if e else
if (EXPRESSÃO) {
  // Executar este bloco se a expressão for verdadeira
} else {
  // Executar este bloco se a expressão for falsa
}

// Testar uma expressão usando if, else if e else
if (EXPRESSÃO1) {
  // Executar este bloco se a expressão1 for verdadeira
} else if (EXPRESSÃO2) {
  // Executar este bloco se a expressão2 for verdadeira e a expressão1 for falsa
} else {
  // Executar este bloco se nenhuma das expressões anteriores for verdadeira
}
```

### switch em JavaScript

```javascript
// Testar o valor de uma expressão usando switch
switch (EXPRESSÃO) {
  case VALOR1:
    // Executar este bloco se a expressão for igual a VALOR1
    break;
  case VALOR2:
    // Executar este bloco se a expressão for igual a VALOR2
    break;
  default:
    // Executar este bloco se a expressão não for igual a nenhum dos valores anteriores
    // Este é o caso default
    break;
}
```

## Estruturas de repetição em JavaScript

### for em JavaScript

```javascript
// Iterar sobre um intervalo de valores com um passo usando for
for (let i = 1; i <= 10; i += PASSO) {
  // Executar este bloco para cada valor de i
}
```

### while em JavaScript

```javascript
// Executar um bloco de código enquanto uma expressão for verdadeira usando while
while (EXPRESSÃO) {
  // Executar este bloco enquanto a expressão for verdadeira
}
```

### do while em JavaScript

```javascript
// Executar um bloco de código pelo menos uma vez e enquanto uma expressão for verdadeira usando do-while
do {
  // Executar este bloco pelo menos uma vez
} while (EXPRESSÃO);
```

### foreach em JavaScript

```javascript
// Iterar sobre um array
let numeros = [1, 2, 3, 17];
numeros.forEach(function (valor) {
  console.log("O valor atual é " + valor);
});

// Iterar sobre um objeto iterável
let mapa = new Map([
  ["um", 1],
  ["dois", 2],
  ["três", 3],
  ["dezessete", 17]
]);
mapa.forEach(function (valor, chave) {
  console.log(chave + " => " + valor);
});
```

Mais detalhes e exemplos em [Array.prototype.forEach() - JavaScript | MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).

## Funções em JavaScript

```javascript
// Declarar uma função chamada soma que recebe dois parâmetros
function soma(a, b) {
  return a + b; // Retorna a soma de a e b
}

// Declarar uma função chamada multiplica que recebe dois parâmetros
function multiplica(a, b) {
  return a * b; // Retorna o produto de a e b
}

// Chamar as funções e imprimir seus valores de retorno
console.log("O resultado da soma é " + soma(3, 4)); // Imprime "O resultado da soma é 7"
console.log("O resultado da multiplicação é " + multiplica(3, 4)); // Imprime "O resultado da multiplicação é 12"
```

Mais detalhes e exemplos em [Understand parameters and return values - OpenClassrooms](https://openclassrooms.com/en/courses/5664271-learn-programming-with-javascript/6056621-understand-parameters-and-return-values)

## Links úteis

- [JavaScript | MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
- [JavaScript | W3Schools](https://www.w3schools.com/js/)
- [JavaScript | DevDocs](https://devdocs.io/javascript/)

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}
