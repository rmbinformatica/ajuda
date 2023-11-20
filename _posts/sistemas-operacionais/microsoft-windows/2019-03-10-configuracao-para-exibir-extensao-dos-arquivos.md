---
title: Como configurar o Windows para mostrar a extensão dos seus arquivos
author: "Renato Monteiro Batista"
date: 2019-03-10
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, extensão, arquivo
description: Como configurar o windows para mostrar a extensão dos seus arquivos
---

## Como mostrar a extensão dos arquivos no windows através do painel de controle

Por padrão o windows vem configurado com a opção de ocultar a extensão dos arquivos conhecidos. Mas isso pode ser facilmente alterado.

Procedimento:\
1 - Acesse o **painel de controle**\
2 - Acesse **Opções de pasta**\
a) Se seu painel de controle estiver com _Exibir por: Ícones grandes_, você verá opções de pasta na tela principal do painel de controle.\
b) Se seu painel de controle estiver com _Exibir por: Categorias_, você verá opções de pasta dentro da opção _Aparência e Personalização_.\
****3 - Clique na aba **Modo de exibição**\
****4 - Em _Configurações avançadas_, **desmarque** a opção **Ocultar as extensões dos tipos de arquivos conhecidos**.\
5 - Clique OK

## Automatizando a configuração para exibir a extensão dos arquivos no windows via script

Para automatizar a configuração via script, execute o seguinte comando:

```batch
REG ADD "HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /v HideFileExt /t REG_DWORD /d 0 /f
```