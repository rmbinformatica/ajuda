---
title: Configurar conta de e-mail cPanel em celulares e tablet android
author: "Renato Monteiro Batista"
date: 2021-04-01
category: [hospedagem-cpanel]
layout: post
keywords: cpanel, email, android, imap, configurar email android, configurar email imap android
description: >-
  Este artigo descreve o passo-a-passo para realizar a configuração da sua conta
  de e-mail em um smartphone ou tablet android
revisao: 2023-11-19
---

A configuração da sua conta de e-mail pode ser realizada em qualquer aplicativo de e-mail de sua preferência que suporte o protocolo IMAP.

Recomendamos o uso do aplicativo Microsoft Outlook e é o que utilizaremos como exemplo neste passo-a-passo.

## Baixando o Microsoft Outlook na PlayStore

Baixe o Microsoft Outlook da loja de aplicativos do seu smartphone, para baixar da Play Store pesquise por _Microsoft Outlook_ ou acesse o link: [Microsoft Outlook Play Store](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)

## Configurando o Microsoft Outlook para sua conta de e-mail

Configurar o Microsoft Outlook para acessar a sua conta de e-mail é bem simples, ao abrir o aplicativo pela primeira vez será mostrado a tela de início abaixo, basta clicar no botão **Iniciar**.

![Tela inicial do aplicativo Microsoft Outlook]({{site.img}}imap01.png)

### Informe seu endereço de e-mail

Nesta tela informe seu endereço de e-mail completo, incluindo o @ e o domínio, em seguida clique no botão CONTINUAR.

![Tela do App Microsoft Outlook para informar endereço de e-mail]({{site.img}}imap02.png)

### Selecione o protocolo IMAP

O Microsoft Outlook irá tentar detectar as configurações de e-mail automaticamente, o protocolo correto a ser usado é o IMAP. Porém as vezes o outlook identifica o servidor de maneira incorreta mostrando como um servidor Exchange, dessa forma:

![Exemplo onde o outlook identifica o tipo de servidor de maneira incorreta.]({{site.img}}imap03.png)

Se for esse o caso basta clicar no ícone da interrogação **(?)** ao lado da palavra exchange e escolher a opção **Alterar provedor da conta** conforme mostrado no exemplo abaixo:

![Microsoft Outlook - Alterar provedor da conta]({{site.img}}imap04.png)

Na tela seguinte escolha a opção de protocolo IMAP.

![Microsoft Outlook - Tela de seleção do protocolo IMAP]({{site.img}}imap05.png)

Observe que, após selecionar o protocolo correto a próxima tela irá mostrar o título Conectar IMAP, conforme mostrado abaixo:

![Título da tela de configuração do IMAP no App Microsoft Outlook]({{site.img}}imap06.png)

### Informe seus dados

Informe os dados a seguir relacionados a sua conta:

* **Endereço de e-mail**: já estará preenchido com seu e-mail;
* **Senha**: A senha de acesso à sua conta, a mesma utilizada para acessar o webmail;
* **Nome para exibição**: Seu nome completo, o que os destinatários dos e-mails verão como "DE" quando receberem uma mensagem sua;
* **Descrição**: Uma descrição qualquer, recomendamos usar o domínio do seu email (tudo que vem depois do @) para facilitar a identificação.

Abaixo a imagem da tela para facilitar a identificação dos campos.

![Orientação de preenchimento da tela de configuração do IMAP]({{site.img}}imap07.png)

Após o preenchimento dos campos clique no ícone de confirmar, conforme indicado na seta vermelha na imagem acima.

O aplicativo Microsoft Outlook irá tentar realizar a configuração da conta. Caso a conta seja configurada corretamente será exibida a tela perguntando se deseja configurar outra conta de e-mail. Se houver outra conta de e-mail clique no botão **Adicionar,** conforme identificado na seta vermelha da imagem a seguir, e repita os passos acima para todas as contas de e-mail desejadas. Se não houver mais contas de e-mail basta clicar na opção **Talvez mais tarde**, conforme indicado na seta verde da imagem a seguir.

![Tela de conclusão da configuração do e-mail]({{site.img}}imap09.png)

Caso haja algum erro nessa etapa recomendamos que primeiramente _verifique se está usando a senha correta_. Se estiver usando a senha correta e com dificuldades de conectar na conta, escolha a opção configurações **avançadas**:

![Opção de configurações avançadas.]({{site.img}}imap08.png)

## Configurações avançadas

Na tela de configurações avançadas é possível especificar todos os detalhes do servidor que deseja configurar. Abaixo todas as informações que você deve preencher, onde houver identificado **\[**_**domínio**_**]** substitua pelo seu domínio, que é tudo que vem depois do arroba (@) no seu e-mail. Exemplo: Se seu email é **fulano@rmbinformatica.com.br** o domínio será **rmbinformatica.com.br**.

Você deverá preencher:

* **Endereço de e-mail**: já estará preenchido com seu e-mail;
* **Nome para exibição**: Seu nome completo, o que os destinatários dos e-mails verão como "DE" quando receberem uma mensagem sua;
* **Descrição**: Uma descrição qualquer, recomendamos usar o domínio do seu email (tudo que vem depois do @) para facilitar a identificação;
* **Nome do Host IMAP**: **mail.\[**_**domínio**_**]**&#x20;
* **Nome de usuário IMAP**: seu e-mail completo, conforme preenchido no primeiro campo (endereço de e-mail);
* **Senha IMAP**: a senha do seu e-mail, a mesma utilizada para acesso ao webmail;
* **Nome do host SMTP**: **mail.\[**_**domínio**_**]**&#x20;
* **Nome de usuário SMTP**: seu e-mail completo, conforme preenchido no primeiro campo (endereço de e-mail);
* **Senha SMTP**: a senha do seu e-mail, a mesma utilizada para acesso ao webmail.

Após o preenchimento dos campos clique no botão de confirmar no canto superior direito da tela.