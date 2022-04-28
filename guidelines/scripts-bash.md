---
description: Orientações sobre como elaborar scripts em bash
---

# Scripts Bash

## Como fazer uma pergunta ao usuário em bash e guardar o resultado numa variável?

```bash
read -p "Qual sua pergunta?" variavel
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

