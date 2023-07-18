---
description: >-
  Estruturas de sintaxe básicas do PHP.
---
## Estruturas de sintaxe básicas do PHP

### Comentários em PHP

Comentários são blocos de texto que não são interpretados pela linguagem de programação. Eles são utilizados para documentar o código, explicar o que está sendo feito, ou para desabilitar uma parte do código.

```php
// Isto é um comentário de uma linha

# Isto também é um comentário de uma linha

/*
Isto é um comentário
de múltiplas linhas
*/
```

### Declaração de variáveis em PHP

```php
# Variável
$var = "PHP";
```

### Declaração de arrays em PHP

```php
# Lista simples
$lista = [1, "PHP", true, [2, 3, 4]];

# Array
$array = array(
  "chave1" => 1,
  "chave2" => "PHP",
  "chave3" => false
);

# Array (sintaxe curta)
$array = [
  "chave1" => 1,
  "chave2" => "PHP",
  "chave3" => false
];

# Array (usando construtor)
$array = new ArrayObject([
  "chave1" => 1,
  "chave2" => "PHP",
  "chave3" => false
]);
```

### Ler input do usuário, atribuir a uma variável e depois imprimir na tela em PHP (cli)

O exemplo é válido para o php em linha de comando (php cli), para dados recebidos em servidores web as informações já estão guardadas nas variáveis globais `$_GET`, `$_POST`, `$_REQUEST`, `$_COOKIE`, `$_SESSION` e `$_FILES`.

```php
# Ler um input do usuário e guardar na variável nome
$nome = readline("Qual é o seu nome? ");

# Imprimir a variável nome
echo "Olá, $nome!\n";
```

## Estruturas de seleção em PHP

### if em PHP

```php
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

// Testar uma expressão usando if, elseif e else
if (EXPRESSÃO1) {
  // Executar este bloco se a expressão1 for verdadeira
} elseif (EXPRESSÃO2) {
  // Executar este bloco se a expressão2 for verdadeira e a expressão1 for falsa
} else {
  // Executar este bloco se nenhuma das expressões anteriores for verdadeira
}
```

### switch em PHP

```php
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

## Estruturas de repetição em PHP

### for em PHP

```php
// Iterar sobre um intervalo de valores com um passo usando for
for ($i = 1; $i <= 10; $i += PASSO) {
  // Executar este bloco para cada valor de i
}
```

### while em PHP

```php
// Executar um bloco de código enquanto uma expressão for verdadeira usando while
while (EXPRESSÃO) {
  // Executar este bloco enquanto a expressão for verdadeira
}
```

### do while em PHP

```php
// Executar um bloco de código pelo menos uma vez e enquanto uma expressão for verdadeira usando do-while
do {
  // Executar este bloco pelo menos uma vez
} while (EXPRESSÃO);
```

### foreach em PHP

```php
// Iterar sobre um array simples
$a = array(1, 2, 3, 17);
foreach ($a as $v) {
    echo "O valor atual é $v.\n";
}

// Iterar sobre um array associativo
$a = array(
    "um" => 1,
    "dois" => 2,
    "três" => 3,
    "dezessete" => 17
);
foreach ($a as $k => $v) {
    echo "\$a[$k] => $v.\n";
}
```

Mais detalhes e exemplos em [PHP: foreach - Manual](https://www.php.net/manual/pt_BR/control-structures.foreach.php).

## Funções em PHP

```php
// Declarar uma função chamada soma que recebe dois parâmetros
function soma($a, $b) {
  return $a + $b; // Retorna a soma de a e b
}

// Declarar uma função chamada multiplica que recebe dois parâmetros
function multiplica($a, $b) {
  return $a * $b; // Retorna o produto de a e b
}

// Chamar as funções e imprimir seus valores de retorno
echo "O resultado da soma é " . soma(3, 4) . "\n"; // Imprime "O resultado da soma é 7"
echo "O resultado da multiplicação é " . multiplica(3, 4) . "\n"; // Imprime "O resultado da multiplicação é 12"
```

Mais detalhes e exemplos em [PHP: Funções - Manual](https://www.php.net/manual/pt_BR/language.functions.php).

## Links úteis

- [Manual oficial do PHP](https://www.php.net/manual/pt_BR/index.php)
- [PHP | W3Schools](https://www.w3schools.com/php/default.asp)

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}
