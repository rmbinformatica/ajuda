---
title: Powershell comandos úteis
author: "Renato Monteiro Batista"
date: 2022-04-28
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, powershell, comandos
description: Este artigo descreve alguns comandos úteis do powershell
---

## Acessando a linha de comando Windows PowerShell

Para acessar a linha de comando Windows PowerShell clique com o botão _direito_ no menu iniciar e escolha a opção **Windows Powershell (Admin)**.

![Windows - (botão direito) Iniciar - PowerShell (admin)]({{site.img}}windows-botao-direito-iniciar-powershell-admin.png)

## Alterar o perfil de rede do Windows para público ou particular utilizando a linha de comando Windows PowerShell

Primeiramente é necessário verificar quais as conexões existem na máquina, isso pode ser feito através do comando:

```powershell
Get-NetConnectionProfile
```

No retorno apresentado o que nos interessa para essa configuração é  o **`Name`** da conexão apresentado, exemplo na imagem a seguir:

![Retorno do comando Get-NetConnectionProfile]({{site.img}}windows-powershell-netconnectionprofile.png)

Nesse caso podemos mudar o perfil de rede da conexão wifi chamada `Fibra_Exotica` para **Particular** executando o seguinte comando:

```powershell
Set-NetConnectionProfile -Name "Fibra_Exotica" -NetworkCategory Private
```

Da mesma forma, podemos alterar o Perfil de rede da conexão `OpenVPN TAP-Windows6` para **Pública** executando o seguinte comando:

```powershell
Set-NetConnectionProfile -Name "OpenVPN TAP-Windows6" -NetworkCategory Public
```

## Adicionando uma pasta às exclusões de verificação do Windows Defender através da linha de comando

Utilizando o Windows PowerShell é possível adicionar uma pasta às exclusões de verificação do Windows Defender através do comando a seguir:

```powershell
Add-MpPreference -ExclusionPath "C:\pasta"
```

No exemplo acima altere o `c:\pasta` para o caminho que deseja excluir das verificações.

## Listar o escopo de endereços o qual uma regra de firewall está aplicada usando o Windows PowerShell

```powershell
Get-NetFirewallRule -DisplayName "Nome da regra" | Get-NetFirewallAddressFilter
```

{% include gads.html %}

## Criar uma nova regra do windows firewall permitindo todas as conexões a partir de um endereço de ip específico usando o powershell

No exemplo abaixo vamos utilizar *192.168.0.1* como endereço de ip remoto (de onde as conexões serão permitidas).

```powershell
New-NetFirewallRule -DisplayName "NomeDaRegra" -Direction Inbound -LocalAddress Any -RemoteAddress 192.168.0.1 -Action Allow
```

## Obter o nome atual do computador utilizando o powershell

```powershell
Get-ComputerInfo -Property "CsName"
```

## Altear o nome atual do computador utilizando o PowerShell

```powershell
Rename-Computer -NewName "NovoNomeDoComputador"
```

## Obter a lista de usuários do computador local

```powershell
Get-LocalUser
```

## Redefinir a senha de um usuário do computador local utilizando o Powershell

```powershell
$NomeDoUsuario = "NomeDoUsuario"
$NovaSenha = ConvertTo-SecureString "senha" -AsPlainText -Force
Set-LocalUser -Name $NomeDoUsuario -Password $NovaSenha
```

## Reiniciar o computador utilizando o Powershell

```powershell
Restart-Computer
```

## Ver a lista de programas instalados no computador local utilizando o Powershell

```powershell
Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\* |
Select-Object DisplayName, DisplayVersion, Publisher, InstallDate |
Where-Object { $_.DisplayName -ne $null } |
Sort-Object DisplayName
```

## Veja também

* [CMD & Batch Script](/ajuda/sistemas-operacionais/microsoft-windows/cmd)