---
title: Configurando ubuntu para permitir conexões originadas do guacamole
author: "Renato Monteiro Batista"
date: 2022-08-20
category: [redes-e-infraestrutura, apache-guacamole]
layout: post
revisao: 2026-07-04
keywords: apache, guacamole, ubuntu, ssh, conexão, erro, handshake
description: >-
  Este artigo descreve uma solução para conseguir conectar em servidores linux
  ubuntu 22.04 utilizando o apache guacamole
---

Para que o Apache Guacamole consiga gerenciar o seu servidor Ubuntu remotamente, é necessário configurar corretamente o serviço de SSH ou VNC. Certifique-se de liberar a porta correspondente no firewall (UFW) do Ubuntu. Sempre faça a opção pelo uso de chaves privadas para a conexão SSH em vez de senhas, lembre-se de que o Guacamole exige formatos específicos (como o padrão OpenSSH) para validar a autenticação.

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