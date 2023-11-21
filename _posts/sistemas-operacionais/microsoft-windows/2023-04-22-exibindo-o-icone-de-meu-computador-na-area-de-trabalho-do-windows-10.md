---
title: Exibindo o ícone de "Meu Computador" na área de trabalho do Windows 10
author: "Renato Monteiro Batista"
date: 2023-04-22
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, desktop, area de trabalho, icone, meu computador, windows 10, win 10, win10, w10, windows 11, win 11, win11, w11, computador, computador, este computador, computer, mostrar computador
description: >-
  Este artigo descreve como exibir o ícone do Meu computador na área de trabalho
  do Windows 10, tanto pelo método da interface gráfica do windows quanto
  através de linha de comando ou script.
---

A partir do Windows 10 a Microsoft optou por remover o ícone do Meu Computador da área de trabalho do Windows. O que costumava ser um padrão nas versões anteriores. Mas ainda há a opção de reexibir essa opção seguindo os passos abaixo:

## Método A - Configurando o Windows 10 para exibir o ícone do "Meu Computador" na área de trabalho

Clique com o botão **direito** em qualquer área vazia da área de trabalho e, sem seguida, clique na opção **Personalizar**.

![windows botão direito área de trabalho personalizar]({{site.img}}windows-desktop-personalizar.png)

Na janela que surgirá clique na opção **Temas** que aparece do lado esquerdo e, em seguida, na opção **Configurações de ícones da área de trabalho**, conforme mostrado na figura abaixo:

![Opção de configuração de ícones da área de trabalho]({{site.img}}windows-temas-icones-desktop.png)

Na janela a seguir, selecione a opção **Computador** e, em seguida, clique **OK**.

![configurações de ícones da área de trabalho]({{site.img}}windows-config-desktop-meu-computador.png)

Pronto, o ícone do computador passará a ser exibido na área de trabalho.

## Método B - Chave de registro para exibir o ícone do "Meu computador" na área de trabalho do Windows 10

_Esse método é somente para usuários avançados que desejem automatizar o processo de configuração por meio de scripts._

Inclua ou altere na chave de registro **`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\HideDesktopIcons\NewStartPanel`** o valor **`{20D04FE0-3AEA-1069-A2D8-08002B30309D}`** como **`DWORD`** e com dados **`0`**.

Script para exibir o ícone de meu computador na área de trabalho:

```batch
REG ADD HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\HideDesktopIcons\NewStartPanel /f /t REG_DWORD /v "{20D04FE0-3AEA-1069-A2D8-08002B30309D}" /d 0
```
