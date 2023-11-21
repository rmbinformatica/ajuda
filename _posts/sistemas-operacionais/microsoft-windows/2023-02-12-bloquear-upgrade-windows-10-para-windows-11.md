---
title: Como bloquear o upgrade automático do Windows 10 para Windows 11?
author: "Renato Monteiro Batista"
date: 2023-02-12
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, upgrade, windows 11, bloquear, powershell, windows update, atualização, atualizacao, atualizacao automatica, manter windows 10, impedir windows 11, windows 10, windows 11, win10, win11, win 10, win 11, w10, w11, permanecer, evitar
description: >-
  Este artigo descreve como bloquear o Upgrade automático do Windows 10 para Windows 11, nos computadores compatíveis, usando o powershell.
---

## Caso de uso

Em alguns ambientes corporativos é desejável manter o Windows na versão 10 por motivos de incompatibilidade de algum software usado na empresa. Por exemplo, em ambientes onde é utilizado algum software legado que não seja compatível com a nova versão do windows.

## Riscos de desabilitar o upgrade automático

Desabilitar quaisquer tipo de atualizaçÕes de software implica em riscos de segurança pois poderá haver falhas no software que não foram corrigidas pela falta da atualização. Por isso entedemos que cabe ao departamento de TI avaliar se é desejável ou não desabilitar o upgrade automático do Windows 10 para Windows 11.

## Como bloquear upgrade automático do windows 10 para o windows 11?

Para acessar o powershell, clique com o botão direito no botão iniciar e escolha a opção "Windows PowerShell (Admin)".

Para bloquear o upgrade automático, mantendo o recebimento de atualizações para o release atualmente instalado do windows, execute os comandos abaixo no powershell:

```powershell
$releaseVersion = (Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion" -Name DisplayVersion).DisplayVersion
New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Force | Out-Null
Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Name "TargetReleaseVersion" -Type DWord -Value 1
Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Name "TargetReleaseVersionInfo" -Type String -Value $releaseVersion
```

Após a execução dos comandos acima é necessário a reinicialização do computador.

Uma vez executado o comando acima, o widnows update continuará recebendo as atualizações do release atualmente instalado e o upragde para o Windows 11 não será realizado automaticamente.