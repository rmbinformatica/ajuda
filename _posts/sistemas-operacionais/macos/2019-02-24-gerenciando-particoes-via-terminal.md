---
title: Gerenciando partições do MacOS via terminal
author: "Renato Monteiro Batista"
date: 2019-02-24
category: [sistemas-operacionais, macos]
layout: post
revisao: 2023-11-20
keywords: macos, terminal, partição, diskutil, gpt, gerenciar, apagar, alterar, particionamento, particionar, mac, mac os, 
description: Como alterar o mapa de partições a partir do terminal
---

## Listar partições existentes

```bash
diskutil list
```

Em todos os comandos a seguir considere o _N_ de _diskN_ como o identificador do disco, conforme mostrado na listagem do comando acima.

## Desmontando uma unidade de disco

```bash
diskutil umountDisk /dev/diskN
```

## Removendo uma partição GPT

```bash
gpt remove -i 2 /dev/diskN
```

Nesse caso seria removido a partição relativa à entrada # 2 da listagem.

## Removendo todas as partições GPT

```bash
gpt destroy /dev/diskN
```

## Apagando todo o conteúdo de um disco e deixando sem partições

```bash
diskutil zeroDisk /dev/diskN
```
