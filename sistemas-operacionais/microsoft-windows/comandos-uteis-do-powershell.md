---
description: Este artigo descreve alguns comandos úteis do powershell
---

# Comandos úteis do PowerShell

## Acessando a linha de comando Windows PowerShell

Para acessar a linha de comando Windows PowerShell clique com o botão _direito_ no menu iniciar e escolha a opção **Windows Powershell (Admin)**.

![](<../../.gitbook/assets/image (15).png>)

## Alterar o perfil de rede do Windows para público ou particular utilizando a linha de comando Windows PowerShell

Primeiramente é necessário verificar quais as conexões existem na máquina, isso pode ser feito através do comando:

```powershell
Get-NetConnectionProfile
```

No retorno apresentado o que nos interessa para essa configuração é  o **`Name`** da conexão apresentado, exemplo na imagem a seguir:

![](<../../.gitbook/assets/image (20).png>)

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

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><a href="http://renato.ovh">Renato Monteiro Batista</a></td><td>Engenheiro de Computação</td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Artigos relacionados" %}
* [CMD & Batch Script](cmd)
{% endtab %}
{% endtabs %}