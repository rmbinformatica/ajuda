---
description: >-
  Este artigo descreve um conjunto de comandos úteis para utilização no terminal
  do mac. Alguns comandos descritos podem servir também para sistemas linux.
---

# Comandos úteis no terminal

## Mostrar a tabela de rotas do Mac OS

No linux seria equivalente ao resultado do comando `route -n`

```bash
netstat -rn
```

## Adicionando uma rota manualmente no Mac OS

```bash
sudo route -n add -net [rede_destino/CIDR] [gateway]
```

## Alterar o hostname da máquina

```bash
sudo scutil --set HostName [novo_nome]
```

## Verificar o hash MD5 ou SHA de um arquivo

```bash
md5 [nome_arquivo]
shasum [nome_arquivo]
```
