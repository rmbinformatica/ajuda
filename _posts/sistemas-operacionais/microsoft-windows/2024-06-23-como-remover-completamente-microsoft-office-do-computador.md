---
title: Como remover completamente o Microsoft Office do computador?
author: "Renato Monteiro Batista"
date: 2024-06-23
category: [sistemas-operacionais, microsoft-windows]
layout: post
keywords: windows, cmd, office, remover, removedor, office 365, microsoft, microsoft 365, desinstalar, desinstalação
description: >-
  Instruções para realizar a desinstalação completa do Microsoft Office do seu computador Windows
---

## Visualizando e removendo as chaves de produto (product key) do Microsoft Office instaladas na máquina

Todos os comandos precisam ser executados a partir da pasta onde o office está instalado, neste exemplo consideraremos que o office está instalado no caminho **`C:\Program Files\Microsoft Office\Office16`** faça os ajustes necessários conforme seu caso.&#x20;

```batch
cd "C:\Program Files\Microsoft Office\Office16"
cscript ospp.vbs /dstatus
cscript ospp.vbs /unpkey:[FinalChave]
```

Na segunda linha o comando exibe as chaves atualmente instaladas, note que haverá uma ou mais linhas no resultado contendo a informação: **`Last 5 characters of installed product key: XYZ99`** nesse caso o _XYZ99_ seria a informação que seria preenchida no comando da terceira linha no espaço indicado como **`[FinalChave]`**.

## Ferramenta de remoção do Microsoft Office

A Microsoft disponibiliza uma ferramenta de [remoção do Office e Microsoft 365](https://aka.ms/SaRA-officeUninstallFromPC), baixee execute a ferramenta e siga as instruções para remover completamente o Office do seu computador.

Recomendamos a escolha da opção _Todas as versões do Microsoft Office_ quando a ferramenta questionar qual versão deseja remover. Se você possui mais de uma versão do Office instalada em seu computador e escolher remover somente uma das versões a outra versão pode apresentar problemas de funcionamento. Dessa forma recomendamos remover todas as versões e em seguida reinstalar a versão desejada, se for o caso.

## Veja também

* [Desinstalar o Office de um computador - Suporte Microsoft](https://support.microsoft.com/pt-br/office/desinstalar-o-office-de-um-computador-9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)