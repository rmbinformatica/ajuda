---
description: >-
  Estruturas de sintaxe básicas do C# (C Sharp).
---
## Estruturas de sintaxe básicas do C# (C Sharp)

### Comentários em C#

Comentários são blocos de texto que não são interpretados pela linguagem de programação. Eles são utilizados para documentar o código, explicar o que está sendo feito, ou para desabilitar uma parte do código.

```csharp
// Isto é um comentário de uma linha

/*
Isto é um comentário
de múltiplas linhas
*/
```

### Declaração de variáveis em C#

```csharp
// Variável
string var = "C#";
```

### Declaração de arrays em C#

```csharp
// Array
int[] array = new int[5]; // cria um array de 5 inteiros

// Array (atribuindo valores)
int[] array = new int[5] { 1, 2, 3, 4, 5 };

// Array (sintaxe simplificada)
int[] array = { 1, 2, 3, 4, 5 };
```

### Ler input do usuário, atribuir a uma variável e depois imprimir na tela em C#

```csharp
// Ler um input do usuário e guardar na variável nome
Console.Write("Qual é o seu nome? ");
string nome = Console.ReadLine();

// Imprimir a variável nome
Console.WriteLine("Olá, " + nome + "!");
```

## Estruturas de seleção em C#

### if em C#

```csharp
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

### switch em C#

```csharp
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

## Estruturas de repetição em C#

### for em C#

```csharp
// Repetir um bloco de código usando for
for (int i = 1; i <= 10; i += PASSO) {
  // Executar este bloco para cada valor de i
}
```

Mais detalhes e exemplos em [A instrução for - Guia do C#](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/statements/iteration-statements#the-for-statement).

### while em C#

```csharp
// Executar um bloco de código enquanto uma expressão for verdadeira usando while
while (EXPRESSÃO) {
  // Executar este bloco enquanto a expressão for verdadeira
}
```

Mais detalhes e exemplos em [A instrução while - Guia do C#](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/statements/iteration-statements#the-while-statement).

### do while em C#

```csharp
// Executar um bloco de código pelo menos uma vez e enquanto uma expressão for verdadeira usando do-while
do {
  // Executar este bloco pelo menos uma vez
} while (EXPRESSÃO);
```

Mais detalhes e exemplos em [A instrução do - Guia do C#](https://learn.microsoft.com/pt-br/dotnet/csharp/language-reference/statements/iteration-statements#the-do-statement).

### foreach em C#

```csharp
// Iterar sobre um array
int[] numeros = {1, 2, 3, 17};
foreach (int valor in numeros)
{
    Console.WriteLine("O valor atual é " + valor);
}

// Iterar sobre um dicionário
Dictionary<string, int> mapa = new Dictionary<string, int>();
mapa.Add("um", 1);
mapa.Add("dois", 2);
mapa.Add("três", 3);
mapa.Add("dezessete", 17);
foreach (KeyValuePair<string, int> par in mapa)
{
    Console.WriteLine(par.Key + " => " + par.Value);
}
```

Mais detalhes e exemplos em [foreach - C# Reference | Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/keywords/foreach-in).

## Funções em C#

```csharp
// Declarar uma função chamada soma que recebe dois parâmetros do tipo int e retorna um valor do tipo int
int soma(int a, int b) {
  return a + b; // Retorna a soma de a e b
}

// Declarar uma função chamada multiplica que recebe dois parâmetros do tipo int e retorna um valor do tipo int
int multiplica(int a, int b) {
  return a * b; // Retorna o produto de a e b
}

// Chamar as funções e imprimir seus valores de retorno
Console.WriteLine("O resultado da soma é " + soma(3, 4)); // Imprime "O resultado da soma é 7"
Console.WriteLine("O resultado da multiplicação é " + multiplica(3, 4)); // Imprime "O resultado da multiplicação é 12"
```

Mais detalhes e exemplos em [Methods - C# Programming Guide | Microsoft Docs](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/classes-and-structs/methods).

## Links úteis

- [Guia do C# Microsoft Learn](https://learn.microsoft.com/pt-br/dotnet/csharp/)