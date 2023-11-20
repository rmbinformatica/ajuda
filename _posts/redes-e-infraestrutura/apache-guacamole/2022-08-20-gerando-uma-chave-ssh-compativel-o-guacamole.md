---
title: Gerando uma chave SSH compatível o Guacamole
author: "Renato Monteiro Batista"
date: 2022-08-20
category: [redes-e-infraestrutura, apache-guacamole]
layout: post
revisao: 2023-11-19
keywords: apache, guacamole, ssh, conexão, erro, auth key import failed
description: Este artigo descreve como gerar uma chave SSH para uso com o guacamole
---

## Descrição do problema

Ao tentar conectar via SSH utilizando o Apache Guacamole a conexão não é estabelecida gerando uma entrada de log:

`guacd[pid] DEBUG: Auth key import failed: (null)`

Verifique se a chave privada gerada possui o cabeçalho (primeira linha):

`-----BEGIN OPENSSH PRIVATE KEY-----`

Sendo esse o caso a chave gerada é do novo padrão e não é suportada pela versão atual do guacamole, sendo necessário gerar uma chave cujo cabeçalho seja:

`-----BEGIN RSA PRIVATE KEY-----`

## Resolução

Para resolver esse problema gere uma nova chave ssh com o comando a seguir:

```bash
ssh-keygen -m PEM
```

Utilize a nova chave privada gerada.
