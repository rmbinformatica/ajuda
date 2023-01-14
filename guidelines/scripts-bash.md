---
description: Orientações sobre como elaborar scripts em bash
---

# Scripts Bash

## Como usar variáveis em scripts bash

```bash
#!/bin/bash
# Variáveis
NOME="Fulano"
echo "Olá $NOME"
```

### Variáveis de parâmetros da linha de comando do bash

```bash
#!/bin/bash
# Variáveis de parâmetros
echo "Parâmetro 1: $1"
echo "Parâmetro 2: $2"
```

### Como atribuir a uma variável o resultado de um comando

```bash
NOME=$(whoami)
```

### Como fazer uma pergunta ao usuário em bash e guardar o resultado numa variável?

```bash
read -p "Qual sua pergunta?" variavel
```

## Funções em bash scripts

```bash
#!/bin/bash
# Funções
function nome_funcao {
    echo "Olá $1"
}
nome_funcao Fulano
```

## Como usar o comando if em scripts bash

```bash
#!/bin/bash
# Condicional
if [ $1 -eq 1 ]
then
    echo "O parâmetro é igual a 1"
else
    echo "O parâmetro é diferente de 1"
fi
```

### Como usar o comando if com múltiplas condições

```bash
#!/bin/bash
# Condicional
if [ $1 -eq 1 ]
then
    echo "O parâmetro é igual a 1"
elif [ $1 -eq 2 ]
then
    echo "O parâmetro é igual a 2"
else
    echo "O parâmetro é diferente de 1 e 2"
fi
```

### Como usar o comando if com múltiplas condições e operadores lógicos

```bash
#!/bin/bash
# Condicional
if [ $1 -eq 1 ] && [ $2 -eq 2 ]
then
    echo "O parâmetro 1 é igual a 1 e o parâmetro 2 é igual a 2"
elif [ $1 -eq 2 ] || [ $2 -eq 2 ]
then
    echo "O parâmetro 1 é igual a 2 ou o parâmetro 2 é igual a 2"
else
    echo "O parâmetro 1 é diferente de 1 e o parâmetro 2 é diferente de 2"
fi
```

## Como usar o comando case em scripts bash

```bash
#!/bin/bash
# Condicional
case $1 in
    1)
        echo "O parâmetro é igual a 1"
        ;;
    2)
        echo "O parâmetro é igual a 2"
        ;;
    *)
        echo "O parâmetro é diferente de 1 e 2"
        ;;
esac
```

## Como usar o loop while em scripts bash

```bash
#!/bin/bash
# Loop
i=0
while [ $i -lt 10 ]
do
    echo "Número: $i"
    i=$((i+1))
done
```

## Como usar o loop for em scripts bash

```bash
#!/bin/bash
# Loop
for i in $(seq 1 10)
do
    echo "Número: $i"
done
```

### Como usar o loop for em scripts bash para percorrer um array

```bash
#!/bin/bash
# Loop
array=(1 2 3 4 5 6 7 8 9 10)
for i in "${array[@]}"
do
    echo "Número: $i"
done
```

### Como usar o loop for em scripts bash para percorrer um array de strings

```bash
#!/bin/bash
# Loop
array=("Fulano" "Beltrano" "Ciclano")
for i in "${array[@]}"
do
    echo "Nome: $i"
done
```

### Como usar o loop for em scripts bash para percorrer um array de strings e exibir o índice e o valor de cada elemento

```bash
#!/bin/bash
# Loop
array=("Fulano" "Beltrano" "Ciclano")
for i in "${!array[@]}"
do
    echo "Índice: $i - Nome: ${array[$i]}"
done
```

### Como usar o comando break em scripts bash

```bash
#!/bin/bash
# Loop
i=0
while [ $i -lt 10 ]
do
    echo "Número: $i"
    i=$((i+1))
    if [ $i -eq 5 ]
    then
        break
    fi
done
```

### Como usar o comando continue em scripts bash

```bash
#!/bin/bash
# Loop
i=0
while [ $i -lt 10 ]
do
    i=$((i+1))
    if [ $i -eq 5 ]
    then
        continue
    fi
    echo "Número: $i"
done
```

### Como usar o comando exit em scripts bash

```bash
#!/bin/bash
# Loop
i=0
while [ $i -lt 10 ]
do
    echo "Número: $i"
    i=$((i+1))
    if [ $i -eq 5 ]
    then
        exit
    fi
done
```

## Saída de dados

### Como usar o comando echo em scripts bash

```bash
#!/bin/bash
# Saída de dados
echo "Olá $1"
```

### Como usar o comando printf em scripts bash

```bash
#!/bin/bash
# Saída de dados
printf "Olá %s\n" $1
```

### Como usar o comando echo com cores em scripts bash

```bash
#!/bin/bash
# Saída de dados
echo -e "\033[0;31mOlá $1\033[0m"
```

### Como usar o comando echo com cores e negrito em scripts bash

```bash
#!/bin/bash
# Saída de dados
echo -e "\033[1;31mOlá $1\033[0m"
```

## Como ler dados do usuário em scripts bash

### Como usar o comando read em scripts bash

```bash
#!/bin/bash
# Leitura de dados
echo "Digite seu nome: "
read nome
echo "Olá $nome"
```

### Como usar o comando read com parâmetros em scripts bash

```bash
#!/bin/bash
# Leitura de dados
read -p "Digite seu nome: " nome
echo "Olá $nome"
```

### Como usar o comando read com parâmetros e senha em scripts bash

```bash
#!/bin/bash
# Leitura de dados
read -sp "Digite sua senha: " senha
echo
echo "Senha digitada: $senha"
```

### Como usar o comando read com parâmetros e timeout em scripts bash

```bash
#!/bin/bash
# Leitura de dados
read -t 5 -p "Digite seu nome: " nome
echo
echo "Nome digitado: $nome"
```

### Como usar o comando read com parâmetros e array em scripts bash

```bash
#!/bin/bash
# Leitura de dados
read -a nomes -p "Digite seus nomes: "
echo
echo "Nomes digitados: ${nomes[@]}"
```

### Como usar o comando read com parâmetros e array de strings em scripts bash

```bash
#!/bin/bash
# Leitura de dados
read -a nomes -p "Digite seus nomes: "
echo
echo "Nomes digitados:"
for i in "${!nomes[@]}"
do
    echo "Índice: $i - Nome: ${nomes[$i]}"
done
```

## Como executar um comando usando como parâmetro o conteúdo de um arquivo linha por linha

### Como executar um comando usando como parâmetro o conteúdo de um arquivo linha por linha usando o while

```bash
#!/bin/bash
# Executar comando usando como parâmetro o conteúdo de um arquivo linha por linha
while read linha
do
    echo "Linha: $linha"
done < $1
```

### Como executar um comando usando como parâmetro o conteúdo de um arquivo linha por linha usando o for

```bash
#!/bin/bash
# Executar comando usando como parâmetro o conteúdo de um arquivo linha por linha
for linha in $(cat $1)
do
    echo "Linha: $linha"
done
```

### Como executar um comando usando como parâmetro o conteúdo de um arquivo linha por linha usando o for e IFS

```bash
#!/bin/bash
# Executar comando usando como parâmetro o conteúdo de um arquivo linha por linha
IFS=$'\n'
for linha in $(cat $1)
do
    echo "Linha: $linha"
done
```

## Trabalhando com arquivos texto pelo número da linha

### Como pesquisar quais linhas contém determinado texto usando grep no linux e mostrando o número da linha

```bash
grep -in "[buscar]" [nome_arquivo]
```

### Contagem de linhas de um arquivo no linux

```bash
wc -l [nome_arquivo]
```

### Exibir as primeiras N linhas de um arquivo no linux usando o head

```bash
head -n [num_linhas] [nome_arquivo]
```

### Exibir as últimas N linhas de um arquivo no linux usando o tail

```bash
tail -n [num_linhas] [nome_arquivo]
```

### Dividir um arquivo no linux pelo número da linha usando o split

```bash
split -l [num_linha] [nome_arquivo]
```

### Excluindo linhas específicas de um arquivo texto no linux pelo número da linha usando o sed

No exemplo abaixo vamos realizar um backup do arquivo original com o mesmo nome do arquivo e acrescido da extensão `.old` no final, também informamos que desejamos excluir a linha específica 20 com o `20d` além de excluir a sequência de linhas de 3 até 10 com o `3,10d`, como separador dos grupos de linhas é usado o `;`

```bash
sed -i.old -e '3,10d;20d' [nome_arquivo]
```

## Executando uma operação para todos os arquivos no diretório atual

Substitua o trecho entre o `then` e o `fi` pelo código necessário. A linha `if test -f` verifica se é um arquivo ou diretório.

```bash
for i in *
do
if test -f "$i"
then
echo "Fazer alguma coisa com o arquivo $i"
fi
done    
```

