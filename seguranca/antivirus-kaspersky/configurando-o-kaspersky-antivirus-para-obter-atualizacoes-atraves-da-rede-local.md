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

![Clique no ícone da engrenagem na parte inferior esquerda da tela principal do kaspersky](<../../.gitbook/assets/image (72).png>)

![Clique no menu "Adicional" do lado esquerdo e em seguida clique na opção Atualização.](<../../.gitbook/assets/image (19) (1).png>)

![Clique na opção selecionar fontes de atualização](<../../.gitbook/assets/image (20) (1).png>)

![Clique no botão adicionar](<../../.gitbook/assets/image (76).png>)

![Informe o caminho das atualizações\* e clique selecionar.](<../../.gitbook/assets/image (23) (1).png>)

O caminho das atualizações é a pasta local ou da rede onde o seu atualizador está realizando o download das novas definições de vírus. _**Consulte o seu administrador de rede para saber o que deve ser preenchido neste campo**_.

Esse caminho pode ser uma pasta local (ex.: **`c:\temp\antivirus`**) ou um compartilhamento de rede (ex.: **`\\192.168.0.4\antivirus`**).

![Após adicionado o caminho, escolha a ordem utilizando as setas de direção.](<../../.gitbook/assets/image (84).png>)

Recomendamos que a primeira posição seja sempre o caminho local.

## Desativando o servidor de atualizações do Kaspersky Lab

Também é possível desativar o uso do servidor de atualização do Kaspersky Lab, de modo que o computador apenas busque as atualizações na rede local. Para isso, siga o procedimento:

Clique com o **botão direito** do mouse na palavra **Ativo** ao lado de **Servidores de atualização da Kaspersky Lab**, no menu que surgir escolha a opção **Desativar**.



![Clique na opção desativar](<../../.gitbook/assets/image (6).png>)

Após desativar, verifique se a opção mudou de ativo para **Inativo**.

![Verifique se consta a palavra inativo e em seguida feche a janela.](<../../.gitbook/assets/image (68).png>)

## Realizando a atualização do Kaspersky antivírus

Volte para a tela inicial e clique no botão **Atualização do banco de dados**.

![Botão atualização do banco de dados](<../../.gitbook/assets/image (6) (1).png>)

![Na tela de atualização clique no botão atualizar e aguarde a conclusão.](<../../.gitbook/assets/image (91).png>)

## Artigo relacionado

{% content-ref url="criando-um-servidor-interno-de-atualizacao-do-kaspersky-antivirus-no-linux.md" %}
[criando-um-servidor-interno-de-atualizacao-do-kaspersky-antivirus-no-linux.md](criando-um-servidor-interno-de-atualizacao-do-kaspersky-antivirus-no-linux.md)
{% endcontent-ref %}
