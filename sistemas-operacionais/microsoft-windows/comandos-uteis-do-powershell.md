---
description: Este artigo descreve alguns comandos úteis do powershell
---

# Comandos úteis do PowerShell

## Acessando a linha de comando Windows PowerShell

Para acessar a linha de comando Windows PowerShell clique com o botão _direito_ no menu iniciar e escolha a opção **Windows Powershell (Admin)**.

![](<../../.gitbook/assets/image (64).png>)

## Alterar o perfil de rede do Windows para público ou particular utilizando a linha de comando Windows PowerShell

Primeiramente é necessário verificar quais as conexões existem na máquina, isso pode ser feito através do comando:

```powershell
Get-NetConnectionProfile
```

No retorno apresentado o que nos interessa para essa configuração é  o **`Name`** da conexão apresentado, exemplo na imagem a seguir:

![](<../../.gitbook/assets/image (65).png>)

Nesse caso podemos mudar o perfil de rede da conexão wifi chamada `Fibra_Exotica` para **Pública** executando o seguinte comando:

```powershell
Set-NetConnectionProfile -Name "Fibra_Exotica" -NetworkCategory Private
```

Da mesma forma, podemos alterar o Perfil de rede da conexão `OpenVPN TAP-Windows6` para **Particular** executando o seguinte comando:

```powershell
Set-NetConnectionProfile -Name "OpenVPN TAP-Windows6" -NetworkCategory Public
```

## Adicionando uma pasta às exclusões de verificação do Windows Defender através da linha de comando

Utilizando o Windows PowerShell é possível adicionar uma pasta às exclusões de verificação do Windows Defender através do comando a seguir:

```powershell
Add-MpPreference -ExclusionPath "C:\pasta"
```

No exemplo acima altere o `c:\pasta` para o caminho que deseja excluir das verificações.
