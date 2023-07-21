---
description: >-
  Estruturas de sintaxe básicas do Python.
---
## Estruturas de sintaxe básicas do Python

### Comentários em Python

Comentários são blocos de texto que não são interpretados pela linguagem de programação. Eles são utilizados para documentar o código, explicar o que está sendo feito, ou para desabilitar uma parte do código.

```python
# Isto é um comentário de uma linha

"""
Isto é um comentário
de múltiplas linhas
"""

'''
Isto também é um comentário
de múltiplas linhas
'''
```

### Declaração de variáveis em Python

```python
# Variável
var = "Python"
```

### Declaração de arrays em Python

```python
# Lista
lista = [1, "Python", True, [2, 3, 4]]
```

### Ler input do usuário, atribuir a uma variável e depois imprimir na tela em Python

```python
# Ler um input do usuário e guardar na variável nome
nome = input("Qual é o seu nome? ")

# Imprimir a variável nome
print(f"Olá, {nome}!")
```

## Estruturas de seleção em Python

### if em Python

```python
# Testar uma expressão usando if
if EXPRESSÃO:
  # Executar este bloco se a expressão for verdadeira

# Testar uma expressão usando if e else
if EXPRESSÃO:
  # Executar este bloco se a expressão for verdadeira
else:
  # Executar este bloco se a expressão for falsa

# Testar uma expressão usando if, elif e else
if EXPRESSÃO1:
  # Executar este bloco se a expressão1 for verdadeira
elif EXPRESSÃO2:
  # Executar este bloco se a expressão2 for verdadeira e a expressão1 for falsa
else:
  # Executar este bloco se nenhuma das expressões anteriores for verdadeira
```

### switch em Python

```python
# Criar um dicionário com os valores e as funções correspondentes
switch = {
  VALOR1: função1,
  VALOR2: função2,
}

# Testar o valor de uma variável usando o dicionário como switch
# Usar o método get para obter a função correspondente ao valor da variável ou uma função padrão caso não exista
# Usar parênteses para chamar a função obtida
switch.get(VARIÁVEL, função_default)()
```

## Estruturas de repetição em Python

### for em Python

```python
# Iterar sobre uma lista
for item in lista:
  # Executar este bloco para cada item da lista

# Iterar sobre uma lista usando o índice
for i in range(len(lista)):
  # Executar este bloco para cada índice da lista

# Iterar sobre uma lista usando o índice e o item
for i, item in enumerate(lista):
  # Executar este bloco para cada índice e item da lista

# Iterar sobre um dicionário
for chave, valor in dicionario.items():
  # Executar este bloco para cada chave e valor do dicionário

# Iterar sobre um dicionário usando a chave
for chave in dicionario:
  # Executar este bloco para cada chave do dicionário

# Iterar sobre um dicionário usando o valor
for valor in dicionario.values():
  # Executar este bloco para cada valor do dicionário

# Iterar sobre um dicionário usando o índice e o item
for i, item in enumerate(dicionario.items()):
  # Executar este bloco para cada índice e item do dicionário

# Iterar sobre um dicionário usando o índice e a chave
for i, chave in enumerate(dicionario):
  # Executar este bloco para cada índice e chave do dicionário

# Iterar sobre um dicionário usando o índice e o valor
for i, valor in enumerate(dicionario.values()):
  # Executar este bloco para cada índice e valor do dicionário

# Iterar sobre um dicionário usando o índice
for i in range(len(dicionario)):
  # Executar este bloco para cada índice do dicionário

# Iterar sobre um dicionário usando o item
for item in dicionario.items():
  # Executar este bloco para cada item do dicionário

# Iterar sobre um dicionário usando a chave
for chave in dicionario.keys():
  # Executar este bloco para cada chave do dicionário

# Iterar sobre um dicionário usando o valor
for valor in dicionario.values():
  # Executar este bloco para cada valor do dicionário

# Iterar sobre um dicionário usando o índice e o item
for i, item in enumerate(dicionario.items()):
  # Executar este bloco para cada índice e item do dicionário

# Iterar sobre um dicionário usando o índice e a chave
for i, chave in enumerate(dicionario.keys()):
  # Executar este bloco para cada índice e chave do dicionário

# Iterar sobre um dicionário usando o índice e o valor
for i, valor in enumerate(dicionario.values()):
  # Executar este bloco para cada índice e valor do dicionário

# Iterar sobre um range
for i in range(10):
  # Executar este bloco para cada número de 0 a 9

# Iterar sobre um range com início, fim e passo
for i in range(0, 10, 2):
  # Executar este bloco para cada número de 0 a 9 com passo de 2

# Iterar sobre um range com início, fim e passo negativo
for i in range(10, 0, -2):
  # Executar este bloco para cada número de 10 a 1 com passo de -2
```

### while em Python

```python
# Executar um bloco de código enquanto uma expressão for verdadeira usando while
while EXPRESSÃO:
  # Executar este bloco enquanto a expressão for verdadeira
```

### do while em Python

Em Python, não há uma estrutura do-while nativa, mas você pode simular um comportamento semelhante usando um laço while com uma variável de controle. A sintaxe para usar um laço while com uma variável de controle é a seguinte:

```python
# Executar um bloco de código pelo menos uma vez e enquanto uma expressão for verdadeira usando while e uma variável de controle
primeira_vez = True
while primeira_vez or EXPRESSÃO:
  # Executar este bloco pelo menos uma vez
  primeira_vez = False
```

### foreach em Python

```python
# Iterar sobre uma lista
lista = [1, 2, 3, 17]
for valor in lista:
  print(f"O valor atual é {valor}")

# Iterar sobre um dicionário
dicionario = {
  "um": 1,
  "dois": 2,
  "três": 3,
  "dezessete": 17
}
for chave, valor in dicionario.items():
  print(f"{chave} => {valor}")
```

Mais detalhes e exemplos em [Python For Loops - w3schools.com](https://www.w3schools.com/python/python_for_loops.asp).

## Funções em Python

```python
# Declarar uma função chamada soma que recebe dois parâmetros
def soma(a, b):
  return a + b # Retorna a soma de a e b

# Declarar uma função chamada multiplica que recebe dois parâmetros
def multiplica(a, b):
  return a * b # Retorna o produto de a e b

# Chamar as funções e imprimir seus valores de retorno
print("O resultado da soma é", soma(3, 4)) # Imprime "O resultado da soma é 7"
print("O resultado da multiplicação é", multiplica(3, 4)) # Imprime "O resultado da multiplicação é 12"
```

Mais detalhes e exemplos em [Python Functions - w3schools.com](https://www.w3schools.com/python/python_functions.asp).

## Fazer requisições HTTP no Python

```python
# Requisição GET usando requests
import requests
url = "https://example.com"
response = requests.get(url)
print(response.text)

# Requisição POST usando requests
import requests
url = "https://example.com"
data = {"param1": "value1", "param2": "value2"}
response = requests.post(url, data=data)
print(response.text)

# Requisição GET usando urllib
import urllib.request
url = "https://example.com"
response = urllib.request.urlopen(url)
print(response.read())

# Requisição POST usando urllib
import urllib.request
import urllib.parse
url = "https://example.com"
data = {"param1": "value1", "param2": "value2"}
data = urllib.parse.urlencode(data).encode()
request = urllib.request.Request(url, data=data)
response = urllib.request.urlopen(request)
print(response.read())
```

## Links úteis

- [Python Doc](https://www.python.org/doc/)
- [Python Tutorial](https://docs.python.org/3/tutorial/)
- [Python | W3Schools](https://www.w3schools.com/python/)

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}
