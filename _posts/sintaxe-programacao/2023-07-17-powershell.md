---
title: Sintaxe PowerShell
author: "Renato Monteiro Batista"
date: 2023-07-17
category: [guidelines, sintaxe-programacao]
layout: post
keywords: powershell, sintaxe powershell, comentários em powershell, variáveis em powershell, arrays em powershell, ler input do usuário em powershell, if em powershell, switch em powershell, while em powershell, do while em powershell, for em powershell, foreach em powershell, funções em powershell, requisições http em powershell
description: >-
  Estruturas de sintaxe básicas do PowerShell.
revisao: 2023-11-19
---
## Estruturas de sintaxe básicas do PowerShell

### Comentários em PowerShell

Comentários são blocos de texto que não são interpretados pela linguagem de programação. Eles são utilizados para documentar o código, explicar o que está sendo feito, ou para desabilitar uma parte do código.

```powershell
# Isto é um comentário de uma linha

<#
Isto é um comentário
de múltiplas linhas
#>
```

### Declaração de variáveis em PowerShell

```powershell
# Variável
$var = "PowerShell"
```

### Declaração de arrays em PowerShell

```powershell
# Array (usando operador @())
$array = @("PowerShell", 1, $true)

# Array (usando vírgulas)
$array = "PowerShell", 1, $true
```

### Ler input do usuário, atribuir a uma variável e depois imprimir na tela em PowerShell

```powershell
# Ler um input do usuário e guardar na variável nome
$nome = Read-Host -Prompt "Qual é o seu nome?"

# Imprimir a variável nome
Write-Host "Olá, $nome!"
```

## Estruturas de seleção em PowerShell

### if em PowerShell

```powershell
# Testar uma condição usando if
if (CONDIÇÃO) {
  # Executar este bloco se a condição for verdadeira
}

# Testar uma condição usando if e else
if (CONDIÇÃO) {
  # Executar este bloco se a condição for verdadeira
} else {
  # Executar este bloco se a condição for falsa
}

# Testar uma condição usando if, elseif e else
if (CONDIÇÃO1) {
  # Executar este bloco se a condição1 for verdadeira
} elseif (CONDIÇÃO2) {
  # Executar este bloco se a condição2 for verdadeira e a condição1 for falsa
} else {
  # Executar este bloco se nenhuma das condições anteriores for verdadeira
}
```

### switch em PowerShell

```powershell
# Testar o valor de uma variável ou expressão usando Switch
Switch (VARIÁVEL ou EXPRESSÃO) {
  VALOR1 {
    # Executar este bloco se a variável ou expressão for igual a VALOR1
  }
  VALOR2 {
    # Executar este bloco se a variável ou expressão for igual a VALOR2
  }
  Default {
    # Executar este bloco se a variável ou expressão não for igual a nenhum dos valores anteriores
    # Este é o caso default
  }
}
```

## Estruturas de repetição em PowerShell

### for em PowerShell

```powershell
# Iterar sobre uma lista de valores com um passo usando ForEach-Object
1..10 | ForEach-Object -Begin {$i = 1} -Process {
  # Executar este bloco para cada valor de i
  $i += PASSO
}
```

### while em PowerShell

```powershell
# Executar um bloco de código enquanto uma condição for verdadeira usando while
while (CONDIÇÃO) {
  # Executar este bloco enquanto a condição for verdadeira
}
```

### do while em PowerShell

```powershell
# Executar um bloco de código pelo menos uma vez e enquanto uma condição for verdadeira usando do-while
do {
  # Executar este bloco pelo menos uma vez
} while (CONDIÇÃO)
```

### foreach em PowerShell

```powershell
# Iterar sobre um array
$numeros = 1, 2, 3, 17
foreach ($valor in $numeros) {
    Write-Host "O valor atual é $valor"
}

# Iterar sobre um hashtable
$mapa = @{
    "um" = 1
    "dois" = 2
    "três" = 3
    "dezessete" = 17
}
foreach ($chave in $mapa.Keys) {
    Write-Host "$chave => $($mapa[$chave])"
}
```

Mais detalhes e exemplos em [about Foreach - PowerShell | Microsoft Learn](https://learn.microsoft.com/pt-br/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-7.3).

## Funções em PowerShell

```powershell
# Declarar uma função chamada soma que recebe dois parâmetros através do array $args
function soma {
  $a = $args[0] # O primeiro elemento do array $args é atribuído à variável a
  $b = $args[1] # O segundo elemento do array $args é atribuído à variável b
  return $a + $b # Retorna a soma de a e b
}

# Declarar uma função chamada multiplica que recebe dois parâmetros através de nomes específicos
function multiplica ($a, $b) {
  $a * $b # Retorna o produto de a e b sem usar o comando return
}

# Chamar as funções e imprimir seus valores de retorno
Write-Host "O resultado da soma é $(soma 3 4)" # Imprime "O resultado da soma é 7"
Write-Host "O resultado da multiplicação é $(multiplica 3 4)" # Imprime "O resultado da multiplicação é 12"
```

Mais detalhes e exemplos em [about Functions - PowerShell Microsoft Learn](https://learn.microsoft.com/pt-br/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-7.3) e [about Return - PowerShell  Microsoft Learn](https://learn.microsoft.com/pt-br/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-7.3).

## Fazendo uma requisição HTTP no PowerShell

### Usando System.Net.WebRequest

```powershell
$request = [System.Net.WebRequest]::Create ('http://example.com')
$request.Method = "POST"
$request.ContentType = "application/x-www-form-urlencoded"
$bytes = [System.Text.Encoding]::ASCII.GetBytes ("name=john&number=5")
$request.ContentLength = $bytes.Length
$requestStream = $request.GetRequestStream ()
$requestStream.Write ( $bytes, 0, $bytes.Length )
$requestStream.Close ()
$response = $request.GetResponse ()
```

### Usando System.Net.WebClient

```powershell
$client = new-object system.net.webclient
$client.UploadString ("http://example.com", "POST", "name=john&number=5")
```

### Usando Invoke-WebRequest

```powershell
Invoke-WebRequest -Uri "http://example.com" -Method POST -Body "name=john&number=5"
```

### Usando Invoke-RestMethod

```powershell
Invoke-RestMethod -Uri "http://example.com" -Method POST -Body "name=john&number=5"
```

## Links úteis

- [Documentação do PowerShell - Microsoft Learn](https://learn.microsoft.com/pt-br/powershell/)