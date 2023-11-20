---
title: Como alterar a senha do e-mail no webmail cPanel
author: "Renato Monteiro Batista"
date: 2021-04-01
category: [hospedagem-cpanel, alteracao-da-senha-de-e-mail]
layout: post
keywords: cpanel, email, senha, alterar senha, alterar senha cpanel via webmail
description: >-
  Este artigo descreve como efetuar a alteração da senha do seu próprio e-mail
  através do webmail cPanel
revisao: 2023-11-19
---

## Acessando o webmail

Acesse o seu endereço de webmail, o endereço padrão de acesso do webmail pelo navegador é `webmail.[dominio.com.br]`, exemplo: se seu e-mail é `meunome@rmbinformatica.com.br` você deve acessar no seu navegador o endereço `webmail.rmbinformatica.com.br`.

Ao abrir a página inicial do seu webmail será solicitado que efetue login, conforme a imagem abaixo, preencha o seu e-mail completo e a senha atual.

![Tela inicial de login do webmail]({{site.img}}tela_login_webmail.png)

### O que fazer se não lembrar a senha atual do e-mail

Caso não lembre a senha atual do e-mail é necessário [redefinir uma nova senha através do painel de controle do cPanel](como-redefinir-a-senha-de-um-e-mail-no-painel-de-controle-cpanel.md).

## Alterando a senha de acesso

Uma vez que foi feito login no webmail, você provavelmente será redirecionado para a tela das mensagens, conforme mostrado na imagem abaixo. Nesse caso clique para acessar o painel da conta de e-mail clicando na imagem webmail home conforme destacado com uma seta verde na figura abaixo.

![Tela de mensagens do webmail]({{site.img}}tela_webmail_cpanel.png)

Se o seu webmail não mostrar a tela de mensagens significa que ele já carregou a página do painel do webmail, conforme mostrado na figura abaixo.

![Painel de configuração do webmail]({{site.img}}tela_configuracoes_webmail_cpanel.png)

Clique na opção **Password & Security,** representada pela figura a seguir.

![Opção que deve ser acessada para alterar a senha]({{site.img}}opcao_password_webmail_cpanel.png)

### Definindo a nova senha de acesso

Preencha os campos **New Password** com a nova senha desejada repita a nova senha no campo **Confirm New Password**. Conforme mostrado na imagem abaixo.

![Tela de alteração de senha do webmail]({{site.img}}tela_alteracao_senha_webmail_cpanel.png)

#### Gerando uma senha aleatória automaticamente

Se tiver com dificuldades para escolher uma senha nova, ou desejar uma senha totalmente aleatória basta clicar no botão **Password Generator**. Ao escolher essa opção será exibida a nova senha aleatória gerada.

![Gerador de senhas do webmail cpanel]({{site.img}}gerador_senhas_webmail_cpanel.png)

Neste exemplo acima a senha aleatória criada foi **UCFos8jc%P4I**, caso não esteja satisfeito com essa senha e deseje outra senha aleatória basta clicar novamente no botão azul **Generate Password**.&#x20;

Uma vez que esteja satisfeito com a senha gerada, marque a caixa de seleção **I have copied this password in a safe place**, e em seguida clique no botão **Use Password**.

### Critérios para criação da senha

* A senha deve possuir no mínimo 5 caracteres.
* A senha não pode ficar em branco.
* O nível de segurança deve ser superior a 70.

### Nível de segurança da senha

Caso esteja digitando uma senha aleatória, atente-se para o nível de segurança da senha que será mostrado na barra Password Strength. Os níveis de segurança podem ser:

#### Senha forte

![Barra indicando senha forte]({{site.img}}barra_senha_forte.png)

Normalmente ao ser usado o gerador de password da página a senha será forte. Prefira a utilização de senhas fortes, anote a senha em um local seguro.

#### Senha boa

![Barra indicando senha boa]({{site.img}}barra_indicando_senha_boa.png)

#### Senha regular

![Barra indicando senha OK]({{site.img}}barra_indicando_senha_ok.png)

**Senha fraca**

![Barra indicando senha fraca]({{site.img}}barra_indicando_senha_fraca.png)

## Confirmando a alteração da senha

Uma vez que esteja satisfeito com a senha e o nível de segurança da senha, basta clicar no botão **Gravar** para salvar a nova senha, conforme destacado com seta vermelha na imagem abaixo.

![Confirmar alteracao de senha webmail cpanel]({{site.img}}confirmar_alteracao_senha_webmail_cpanel.png)

Será exibida a mensagem de que a senha foi alterada com sucesso.

![Mensagem de confirmação de senha alterada com sucesso]({{site.img}}mensagem_confirmacao_senha_alterada_webmail_cpanel.png)