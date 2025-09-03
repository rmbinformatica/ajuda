---
title: Instalando o plugin dns do cloudflare no ACME do Proxmox VE
author: "Renato Monteiro Batista"
date: 2025-09-03 19:12:00 -0300
category: [sistemas-operacionais, linux]
layout: post
revisao: 2025-09-03
keywords: proxmox, rede, configuração, CLI, shell, bash
description: Guia para instalar o plugin do Cloudflare no ACME do Proxmox VE.
---

Instalar o plugin do Cloudflare no ACME do Proxmox VE é uma excelente forma de automatizar a emissão e renovação de certificados SSL via Let's Encrypt, usando o DNS Challenge. Abaixo estão os passos detalhados para realizar essa instalação e configuração via linha de comando (CLI) no shell bash.

## Pré-requisitos

* Proxmox VE 7.x ou 8.x com acesso root
* Domínio gerenciado pela Cloudflare
* Um API Token com permissões:
  * Zone:DNS:Edit
  * Zone:Zone:Read
* Um registro DNS A válido (ex: pve.seudominio.com)

## 1. Criar o API Token no Cloudflare

1. Acesse Cloudflare → API Tokens
2. Clique em Create Token
3. Use o template Edit zone DNS
4. Restrinja ao seu domínio específico
5. Salve o token gerado com segurança

## 2. Criar o arquivo de token no Proxmox

No Proxmox, crie um arquivo para armazenar o token:

```bash
echo 'CF_Token="seu_token_aqui"' > /root/cf-token.txt
chmod 600 /root/cf-token.txt
```

## 3. Adicionar o plugin ACME do Cloudflare

Instale o plugin do Cloudflare para o ACME:

```bash
pvenode acme plugin add dns cftoken --api cf --data /root/cf-token.txt
```

## 4. Verificar se o plugin foi adicionado

```bash
pvenode acme plugin list
```

## 5. Configruar o ACME

No Web GUI do Proxmox, vá para Node - System - Certificates - ACME e crie uma nova conta ACME, selecionando o plugin `cftoken`.

Você também pode fazer isso via CLI:

```bash
pvenode acme account register default seuemail@dominio.com
```

## 6. Criar um novo certificado

Ainda no Web GUI do Proxmox, crie um novo certificado ACME, selecionando o domínio desejado e o método DNS usando o plugin `cftoken`.

Ou via CLI:

```bash
pvenode acme cert create seu_dominio.com --plugin cftoken --dns seu_dominio.com
pvenode config set -acmedomain0 pve.seudominio.com,plugin=cftoken
```

## 7. Testar a renovação do certificado

```bash
pvenode acme cert renew -force
```