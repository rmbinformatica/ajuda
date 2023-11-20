---
title: Substituindo as chaves SSH de servidor do linux
author: "Renato Monteiro Batista"
date: 2019-08-09
category: [sistemas-operacionais, linux]
layout: post
revisao: 2023-11-20
keywords: linux, ssh, chaves, servidor, substituir, gerar, ssh-keygen, sshd, ssh-keyscan, ssh-copy-id, ssh-add, ssh-agent, ssh-keygen, ssh-keyscan, ssh-copy-id, ssh-add, ssh-agent
description: >-
  Este artigo descreve o processo de substituição das chaves SSH de servidor de
  um linux.
---

## Realize um backup das chaves anteriores

Antes de proceder a substituição das chaves recomendamos o backup das chaves anterior para caso de necessidade futura.

```bash
tar -cf antigo.tar /etc/ssh/*key*
```

## Removendo as chaves antigas

```bash
rm -fv /etc/ssh/*key*
```

## Reiniciando o serviço SSHD

Ao reiniciar o serviço sshd as novas chaves serão geradas automaticamente.

```bash
service sshd restart
```
