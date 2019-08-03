---
description: >-
  Este artigo descreve o procedimento para configurar o antivírus kaspersky para
  obter atualizações do antivírus diretamente na rede local em vez dos
  servidores kaspersky na internet.
---

# Configurando o Kaspersky antivírus para obter atualizações através da rede local

## Objetivo:

Este artigo é voltado para ambientes com múltiplos computadores em rede, onde se possui instalado um [agente de atualização do Kaspersky](https://support.kaspersky.com/updater3#downloads) realizando regularmente o download das atualizações do Kaspersky antivírus.

O objetivo desse tipo de cenário é economia de dados de internet bem como proporcionar que os computadores sejam atualizados mais rapidamente uma vez que eles realizarão as cópias dos arquivos diretamente da rede local em vez da internet.

## Configuração nos computadores onde o Kaspersky antivírus está instalado

Abra o Kaspersky antivírus através do ícone na área de trabalho, menu iniciar ou próximo do relógio do sistema.

![Clique no &#xED;cone da engrenagem na parte inferior esquerda da tela principal do kaspersky](../../.gitbook/assets/image%20%286%29.png)

![Clique no menu &quot;Adicional&quot; do lado esquerdo e em seguida clique na op&#xE7;&#xE3;o Atualiza&#xE7;&#xE3;o.](../../.gitbook/assets/image%20%2810%29.png)

![Clique na op&#xE7;&#xE3;o selecionar fontes de atualiza&#xE7;&#xE3;o](../../.gitbook/assets/image%20%2811%29.png)

![Clique no bot&#xE3;o adicionar](../../.gitbook/assets/image%20%284%29.png)

![Informe o caminho das atualiza&#xE7;&#xF5;es\* e clique selecionar.](../../.gitbook/assets/image%20%2814%29.png)

O caminho das atualizações é a pasta local ou da rede onde o seu atualizador está realizando o download das novas definições de vírus. _**Consulte o seu administrador de rede para saber o que deve ser preenchido neste campo**_.

Esse caminho pode ser uma pasta local \(ex.: **c:\temp\antivirus**\) ou um compartilhamento de rede \(ex.: **\\192.168.0.4\antivirus**\).

![Ap&#xF3;s adicionado o caminho, escolha a ordem utilizando as setas de dire&#xE7;&#xE3;o.](../../.gitbook/assets/image%20%281%29.png)

Recomendamos que a primeira posição seja sempre o caminho local.

## Desativando o servidor de atualizações do Kaspersky Lab

Também é possível desativar o uso do servidor de atualização do Kaspersky Lab, de modo que o computador apenas busque as atualizações na rede local. Para isso, siga o procedimento:

Clique com o **botão direito** do mouse na palavra **Ativo** ao lado de **Servidores de atualização da Kaspersky Lab**, no menu que surgir escolha a opção **Desativar**.



![Clique na op&#xE7;&#xE3;o desativar](../../.gitbook/assets/image%20%2813%29.png)

Após desativar, verifique se a opção mudou de ativo para **Inativo**.

![Verifique se consta a palavra inativo e em seguida feche a janela.](../../.gitbook/assets/image%20%289%29.png)

## Realizando a atualização do Kaspersky antivírus

Volte para a tela inicial e clique no botão **Atualização do banco de dados**.

![Bot&#xE3;o atualiza&#xE7;&#xE3;o do banco de dados](../../.gitbook/assets/image%20%283%29.png)

![Na tela de atualiza&#xE7;&#xE3;o clique no bot&#xE3;o atualizar e aguarde a conclus&#xE3;o.](../../.gitbook/assets/image%20%2812%29.png)



