---
title: Folha de dicas para análise de logs
author: "Renato Monteiro Batista"
date: 2022-11-13
category: [sistemas-operacionais, linux]
layout: post
revisao: 2023-11-20
keywords: linux, grep, ngrep, cut, sed, sort, uniq, diff, awk, log, logs, analise, analisar, parsing, parsear, parse, parsing, log, logs, analise, analisar, parsing, parsear, parse
description: Folha de dicas para análise de logs
---

## `grep`

O `grep` permite buscar padrões de experssões regulares em um arquivo. Para busca em arquivos `gzip` utilize o `zgrep`.

### Sintaxe de uso do `grep`

```bash
grep <padrao> <arquivo.log>
```

### Opções do comando `grep`

* `-E` Regex extendida
* `-i` Case insentitive
* `-c` Contagem de resultados
* `-l` Busca nos nomes dos arquivos
* `-n` Mostrar o número das linhas onde o padrão foi encontrado.
* `-v` Inverter o sentido da busca e mostrar as linhas que não possuem o padrão.
* `-R` Varrer recursivamente os arquivos do diretório atual e todas as subpastas.

## `ngrep`

O `ngrep` é usado para analisar pacotes de rede.

### Sintaxe de uso do `ngrep`

```bash
ngrep -I <arquivo.pcap>
```

### Opções do comando `ngrep`

* `-i` Case insenitive
* `-t` Exibir timestamp
* `-I` Ler arquivo pcap
* `-x` Exibir hexdump alternativo
* `-d` Especificar interface de rede

## `cut`

O `cut` é usado para analisar campos em arquivos de log delimitados.

### Sintaxe de uso do `cut`

```bash
cut -d ":" -f 2 <arquivo.log>
```

### Opções do comando `cut`

* `-f` Número de campos
* `-d` Especificar o delimitador
* `-c` Especificar contagem de caracteres

## `sed`

O `sed` (Stream Editor) é utilizado para substituir strings em um arquivo

### Sintaxe de uso do `sed`

```bash
sed s/busca/substituto/g
```

### Opções do comando `sed`

* `s` Busca
* `d` Remover
* `g` Substituto
* `w` Acrescentar ao arquivo
* `-n` Suprimir saída
* `-e` Executar comando

## `sort`

O `sort` é usado para ordenar um arquivo.

### Sintaxe de uso do `sort`

```bash
sort <arquivo.txt>
```

### Opções do comando `sort`

* `-r` Ordem reversa
* `-h` Formato humano
* `-u` Ordenar e remover
* `-n` Ordenação numérica
* `-k` Ordenar por coluna
* `-c` Verificar se ordenado
* `-o` Direcionar saída para um arquivo
* `-f` Ignorar case (maiúscula/minúscula)

## `uniq`

O `uniq` é usado para extrair ocorrências únicas de um arquivo.

### Sintaxe de uso do `uniq`

```bash
uniq <arquivo.txt>
```

### Opções do comando `uniq`

* `-i` Case insensitive
* `-d` Imprimir duplicidades
* `-c` Contar a quantidade de duplicidades

## `diff`

O `diff` é usado para mostrar a diferença entre dois arquivos comparando-os linha por linha.

### Sintaxe de uso do `diff`

```bash
diff <arquivo_a.txt> <arquivo_b.txt>
```

### Como interpretar o resultado do `diff`?

* `a` Adição
* `d` Remoção
* `c` Modificação
* `<` Arquivo A
* `>` Arquivo B
* `#` Número da linha

## `awk`

O `awk` é uma linguagem de programação usada para manipular dados.

### Sintaxe de uso do `awk`

```bash
awk {print $2} <arquivo.txt>
```

### Exemplos de uso do comando `awk`

#### Imprimir a primeira coluna de um arquivo cujo separador é `:`

```bash
awk -F: '{print $1}' /etc/passwd
```

#### Extrair os valores únicos de dois arquivos:

```bash
awk 'FNR==NR {a[$0]++; next} !($0 in a)' <arquivo1.txt> <arquivo2.txt>
```
