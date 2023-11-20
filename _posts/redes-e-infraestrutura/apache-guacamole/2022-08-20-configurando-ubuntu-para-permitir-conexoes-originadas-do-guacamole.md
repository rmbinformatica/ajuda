---
title: Configurando ubuntu para permitir conexões originadas do guacamole
author: "Renato Monteiro Batista"
date: 2022-08-20
category: [redes-e-infraestrutura, apache-guacamole]
layout: post
revisao: 2023-11-19
keywords: apache, guacamole, ubuntu, ssh, conexão, erro, handshake
description: >-
  Este artigo descreve uma solução para conseguir conectar em servidores linux
  ubuntu 22.04 utilizando o apache guacamole
---

## Detalhamento do problema

Devido às bibliotecas de ssh utilizadas pelo apache guacamole, não é possível estabelecer uma conexão ssh com servidores ubuntu. Apresentando a mensagem de erro no log:

`guacd[pid] ERROR: SSH handshake failed.`

## Resolução

> ##### RECOMENDAÇÕES DE SEGURANÇA
>
> A solução abaixo deve ser utilizada somente em redes internas, uma vez que os protocolos apresentados podem apresentar risco de segurança por estarem defasados.
{: .block-danger }

Edite o arquivo de configuração do sshd:

```bash
sudo nano /etc/ssh/sshd_config
```

Inclua as linhas à seguir:

```
PubkeyAcceptedKeyTypes +ssh-rsa
KexAlgorithms +diffie-hellman-group14-sha1
HostKeyAlgorithms +ssh-rsa
```

Reinicie o serviço SSHD:

```bash
sudo systemctl restart ssh
```