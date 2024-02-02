---
title: Sintaxe JavaScript
author: "Renato Monteiro Batista"
date: 2023-07-17
category: [guidelines, sintaxe-programacao]
layout: post
keywords: javascript, sintaxe javascript, comentários em javascript, variáveis em javascript, arrays em javascript, ler input do usuário em javascript, if em javascript, switch em javascript, while em javascript, do while em javascript, for em javascript, foreach em javascript, funções em javascript, requisições http em javascript
description: >-
  Estruturas de sintaxe básicas do JavaScript.
revisao: 2023-11-19
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

## Fazendo uma requisição HTTP no JavaScript

### Usando XMLHttpRequest

```javascript
// Criar uma instância de XMLHttpRequest
var xhr = new XMLHttpRequest();

// Configurar o método, a URL e o tipo de resposta
xhr.open('GET', 'http://example.com/recepticle.aspx');
xhr.responseType = 'text';

// Definir uma função para lidar com o carregamento da resposta
xhr.onload = function() {
  if (xhr.status === 200) {
    // A requisição foi bem sucedida e a resposta está disponível em xhr.response
    console.log(xhr.response);
  }
  else {
    // A requisição falhou e o status está disponível em xhr.status
    console.error('Request failed: ' + xhr.status);
  }
};

// Enviar a requisição
xhr.send();
```

### Usando fetch

```javascript
// Fazer uma requisição GET usando a API Fetch
fetch('http://example.com/recepticle.aspx')
  .then(function(response) {
    // Verificar se a resposta foi bem sucedida
    if (response.ok) {
      // Retornar a resposta como texto
      return response.text();
    }
    else {
      // Lançar um erro com o status da resposta
      throw new Error('Request failed: ' + response.status);
    }
  })
  .then(function(data) {
    // A resposta como texto está disponível em data
    console.log(data);
  })
  .catch(function(error) {
    // Lidar com o erro lançado
    console.error(error);
  });

// Fazer uma requisição POST usando a API Fetch
fetch('http://example.com/recepticle.aspx', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/x-www-form-urlencoded'
  },
  body: 'thing1=hello&thing2=world'
})
  .then(function(response) {
    // Verificar se a resposta foi bem sucedida
    if (response.ok) {
      // Retornar a resposta como texto
      return response.text();
    }
    else {
      // Lançar um erro com o status da resposta
      throw new Error('Request failed: ' + response.status);
    }
  })
  .then(function(data) {
    // A resposta como texto está disponível em data
    console.log(data);
  })
  .catch(function(error) {
    // Lidar com o erro lançado
    console.error(error);
  });
```

## Outros códigos de exemplo

### Redirecionar o usuário se a url contiver uma palavra especifica

```javascript
// Obter o url acessado
var url = window.location.href;

// Verificar se o url contém /ajuda/
if (url.includes("/ajuda/")) {
  // Remover o /ajuda/ do url
  var novoUrl = url.replace("/ajuda/", "/");

  // Direcionar o usuário para o novo url
  window.location.replace(novoUrl);
}
```


## Links úteis

- [JavaScript | MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
- [JavaScript | W3Schools](https://www.w3schools.com/js/)
- [JavaScript | DevDocs](https://devdocs.io/javascript/)
