---
title: Como desativar a expiração de senha do Microsoft Windows (conta local)
author: "Renato Monteiro Batista"
date: 2026-04-15 15:33:08 -0300
category: [sistemas-operacionais, microsoft-windows]
layout: post
description: Como desativar a expiração de senha de contas locais no Microsoft Windows e impedir a solicitação periódica de troca de senha.
keywords: windows, conta local, senha, expiração de senha, desativar expiração de senha, contas de usuário, microsoft windows, política de senha, gerenciamento de contas
revisao: 2026-07-04
---

# Desativar expiração de senha no Windows (conta local)

Este artigo apresenta o procedimento passo‑a‑passo para desativar a expiração de senha no Windows para contas locais.  
O objetivo é impedir que o sistema exija troca periódica de senha.

## 1. Verificar se a conta é local

1. Abra o **Menu Iniciar**.  
2. Clique em **Configurações**.  
3. Acesse **Contas**.  
4. Verifique se aparece “**Conta local**”.  
   - Se estiver usando conta Microsoft, a expiração normalmente não é aplicada.

## 2. Desativar expiração de senha via Prompt de Comando

Este método funciona em **todas as edições do Windows**, incluindo Home.

1. Abra o **Prompt de Comando como Administrador**.  
2. Execute o comando:

```
net accounts /maxpwage:unlimited
```

Esse comando define a validade da senha como **ilimitada**, impedindo expiração.

## 3. Desativar expiração para um usuário específico

Se quiser aplicar apenas a um usuário:

1. Abra o **Prompt de Comando como Administrador**.  
2. Execute:

```
wmic useraccount where name="NOME_DO_USUARIO" set PasswordExpires=False
```


Substitua **NOME_DO_USUARIO** pelo nome da conta local.

Para confirmar:

```
wmic useraccount get name,PasswordExpires
```

## 4. Desativar expiração via Política de Segurança Local (Windows Pro/Enterprise)

Este método não está disponível no Windows Home.

1. Pressione **Win + R**.  
2. Digite:

```
secpol.msc
```

3. Acesse:  
   **Políticas de Conta → Política de Senha**  
4. Abra **Idade máxima da senha**.  
5. Defina como **0** (zero).  
6. Salve.

> **ATENÇÃO**  
> Definir como “0” significa que a senha **nunca expira**.

## 5. Confirmar se a expiração foi desativada

Execute no Prompt de Comando:

```
net accounts
```

Verifique a linha:

```text
Duração máxima da senha (dias): Ilimitado
```

Se estiver assim, a expiração está desativada.