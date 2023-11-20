---
title: Como redefinir a senha de um e-mail no painel de controle cPanel
author: "Renato Monteiro Batista"
date: 2021-04-01
category: [hospedagem-cpanel, alteracao-da-senha-de-e-mail]
layout: post
keywords: cpanel, email, senha, alterar senha, alterar senha cpanel, mudar senha email, mudar senha email cpanel
description: >-
  Este artigo descreve como redefinir a senha de uma conta de e-mail sem a
  necessidade de lembrar a senha anterior.
revisao: 2023-11-19
---

## Acesse o painel de controle cPanel

Primeiramente acesse o painel de controle cPanel com a senha de administrador da conta. O endereço de acesso é normalmente `cpanel.[dominio.com.br]`, exemplo: se seu dominio é `rmbinformatica.com.br` o endereço de acesso ao seu domínio será `cpanel.rmbinformatica.com.br`.

Ao acessar o endereço do painel de controle cPanel será exibida a tela de login conforme a imagem abaixo. Informe o login de administrador, a senha e clique no botão **Login** ou **Entrar**.

![Tela de login do cPanel]({{site.img}}tela_login_cpanel.png)

_ATENÇÃO: Caso não saiba a senha de administrador da conta entre em contato com o suporte da sua hospedagem._

Ao fazer o login será exibida a tela inicial do painel de controle cPanel conforme ilustrado na figura abaixo:

![Tela inicial do painel de controle cPanel]({{site.img}}tela_inicial_cpanel.png)

## Acessando a área de administração dos e-mails

Clique na opção Contas de e-mail, conforme ícone a seguir.

![Ícone para acesso à area de administração de e-mails]({{site.img}}cpanel_contas_de_email.png)

Será exibido a lista de endereços de e-mail do seu domínio, clique no botão Gerenciar na mesma linha do e-mail que você deseja alterar a senha. Só é possível alterar uma senha por vez.

![Listagem de e-mails do domínio]({{site.img}}cpanel_opcao_gerenciar_email.png)

### Gerenciando uma conta de e-mail

Ao clicar no botão gerenciar, será exibida a tela de gerenciamento da conta de e-mail, conforme mostrado na imagem abaixo.

![Tela de gerenciamento de conta de e-mail]({{site.img}}gerador_senhas_email_cpanel.png)

Caso deseje que o sistema gere uma nova senha aleatória automaticamente, basta clicar no botão **Generate**. Para visualizar a senha que está sendo digitada basta clicar no ícone do olho, conforme destacado com uma seta vermelha na imagem abaixo.

![Visualizar senha gerada]({{site.img}}cpanel_visualizar_senha_gerada.png)

### Nível de segurança da senha

A medida que a nova senha for sendo digitada o sistema irá exibir uma barra mostrando o nível de segurança da senha, os níveis são:

#### Senha forte

![Indicador de senha forte cpanel]({{site.img}}cpanel_senha_forte.png)

#### Senha boa

![Indicador de senha boa no cpanel]({{site.img}}indicador_senha_boa_cpanel.png)

#### Senha regular

![Indicador de senha regular no cpanel]({{site.img}}indicador_senha_regular_cpanel.png)

#### Senha fraca

![Indicador de senha fraca no cpanel]({{site.img}}indicador_senha_fraca_cpanel.png)

Em relação ao nível de segurança da senha, nossa recomendação é:

> Jamais utilize senhas fracas, sempre utilize senhas fortes. Dê preferência para senhas geradas pelo gerador aleatório de senhas.

### Confirmando a alteração da senha

Quando estiver satisfeito com a nova senha e o nível de segurança da mesma, para confirmar a alteração da senha, siga até o final da página e clique no botão azul **Update Email Settings**, conforme destacado com uma seta vermelha na imagem abaixo.

![Confirmar alteração de email no cpanel]({{site.img}}confirmar_alteracao_email_cpanel.png)

Uma vez que a senha tenha sido alterada será exibida a mensagem de confirmação a seguir na tela.

![Mensagem de confirmação de alteração da senha do e-mail.]({{site.img}}mensagem_cpanel_email_alterado_sucesso.png)

A mensagem desaparecerá automaticamente da tela em alguns segundos.