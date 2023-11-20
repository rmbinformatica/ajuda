---
title: Como se conectar a um servidor SSH utilizando o algoritmo ssh-dss
author: "Renato Monteiro Batista"
date: 2022-07-07
category: [sistemas-operacionais, linux]
layout: post
revisao: 2023-11-20
keywords: linux, ssh, ssh-dss, ssh-keygen, ssh-keyscan, ssh-copy-id, ssh-add, ssh-agent, ssh-keygen, ssh-keyscan, ssh-copy-id, ssh-add, ssh-agent
description: >-
  Esse artigo descreve a solução para o problema de compatibilidade de conexão
  SSH com servidores que só suportam o algoritmo ssh-dss.
---

## Descrição do problema

Em alguns servidores e storages antigos ao tentar se conectar com o servidor ssh é apresentada a mensagem de erro:

**`Unable to negotiate with xxx.xxx.xxx.xxx port 22: no matching host key type found. Their offer: ssh-dss`**

Isso é causado pois o cliente de ssh está utilizando um algoritmo que não é compatível com o oferecido pelo servidor

## Solução

Para resolver esse problema é necessário configurar o cliente ssh para se conectar utilizando o algoritmo ssh-dss, para fazer isso basta utilizar o comando a seguir:

```bash
ssh -oHostKeyAlgorithms=+ssh-dss [usuario]@[servidor]
```

Substituindo _\[usuario]_ pelo respectivo login e _\[servidor]_ pelo endereço do host do servidor.