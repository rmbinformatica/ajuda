---
title: Configurando o Kaspersky antivírus para obter atualizações através da rede local
author: "Renato Monteiro Batista"
date: 2019-08-02
category: [seguranca, antivirus-kaspersky]
layout: post
revisao: 2023-11-19
keywords: kaspersky, antivírus, atualização, rede local, antivirus
description: >-
  Este artigo descreve o procedimento para configurar o antivírus kaspersky para
  obter atualizações do antivírus diretamente na rede local em vez dos
  servidores kaspersky na internet.
---

## Objetivo

Este artigo é voltado para ambientes com múltiplos computadores em rede, onde se possui instalado um [agente de atualização do Kaspersky](https://support.kaspersky.com/updater3#downloads) realizando regularmente o download das atualizações do Kaspersky antivírus.

O objetivo desse tipo de cenário é economia de dados de internet bem como proporcionar que os computadores sejam atualizados mais rapidamente uma vez que eles realizarão as cópias dos arquivos diretamente da rede local em vez da internet.

## Configuração nos computadores onde o Kaspersky antivírus está instalado

Abra o Kaspersky antivírus através do ícone na área de trabalho, menu iniciar ou próximo do relógio do sistema.

![Clique no ícone da engrenagem na parte inferior esquerda da tela principal do kaspersky]({{site.img}}kaspersky-botao-configuracoes.png)

![Clique no menu "Adicional" do lado esquerdo e em seguida clique na opção Atualização.]({{site.img}}kaspersky-configuracoes-atualizacao.png)

![Clique na opção selecionar fontes de atualização]({{site.img}}kaspersky-selecionar-fonte-atualizacao.png)

![Clique no botão adicionar]({{site.img}}kaspersky-adicionar-fonte-atualizacao.png)

![Informe o caminho das atualizações\* e clique selecionar.]({{site.img}}kaspersky-informar-caminho-atualizacao.png)

O caminho das atualizações é a pasta local ou da rede onde o seu atualizador está realizando o download das novas definições de vírus. _**Consulte o seu administrador de rede para saber o que deve ser preenchido neste campo**_.

Esse caminho pode ser uma pasta local (ex.: **`c:\temp\antivirus`**) ou um compartilhamento de rede (ex.: **`\\192.168.0.4\antivirus`**).

![Após adicionado o caminho, escolha a ordem utilizando as setas de direção.]({{site.img}}kaspersky-alterar-ordem-fonte-atualizacao.png)

Recomendamos que a primeira posição seja sempre o caminho local.

## Desativando o servidor de atualizações do Kaspersky Lab

Também é possível desativar o uso do servidor de atualização do Kaspersky Lab, de modo que o computador apenas busque as atualizações na rede local. Para isso, siga o procedimento:

Clique com o **botão direito** do mouse na palavra **Ativo** ao lado de **Servidores de atualização da Kaspersky Lab**, no menu que surgir escolha a opção **Desativar**.

![Clique na opção desativar](<../../.gitbook/assets/image (6).png>)

Após desativar, verifique se a opção mudou de ativo para **Inativo**.

![Verifique se consta a palavra inativo e em seguida feche a janela.]({{site.img}}kaspersky-desativar-fonte-atualizacao.png)

## Realizando a atualização do Kaspersky antivírus

Volte para a tela inicial e clique no botão **Atualização do banco de dados**.

![Botão atualização do banco de dados]({{site.img}}kaspersky-botao-atualizacao.png)

![Na tela de atualização clique no botão atualizar e aguarde a conclusão.]({{site.img}}kaspersky-botao-atualizar.png)

## Artigo relacionado

* [Criando um servidor interno de atualização do Kaspersky antivírus no linux](/ajuda/seguranca/antivirus-kaspersky/criando-um-servidor-interno-de-atualizacao-do-kaspersky-antivirus-no-linux)
