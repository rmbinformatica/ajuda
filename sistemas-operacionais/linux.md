---
description: Dicas do sistema operacional linux
---

# Linux

## Contando arquivos no diretório atual

```text
ls -1 | wc -l
```

## Retornando as linhas contendo um texto buscado usando grep

```text
grep -in [texto] [arquivo]
```

## Dividindo um arquivo em vários pelo numero de linhas

```text
split -l [linhas] [arquivo]
```

## Apagando linhas específicas de um arquivo usando o sed

No exemplo abaixo vamos apagar as linhas de 7 a 14, e a linha 28

```text
sed -e '7,14d;28d' [arquivo]
```

## Executando um comando para cada arquivo no diretório atual usando bash script

Substitua a linha do echo pelo comando desejado

```text
for i in * 
do
    if -f "$i" 
    then
       echo "Encontrei arquivo $i"
    fi
done

```

## Buscando todos os arquivos em um determinado caminho contendo um texto específico

```text
grep -rnw '/caminho/a/pesquisar/' -e 'texto'
```

