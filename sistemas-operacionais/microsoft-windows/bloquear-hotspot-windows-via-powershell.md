---
author: Renato Monteiro Batista
user: renato
date: 2023-01-18 12:28
description: >-
  Por Renato Monteiro Batista em 18/01/2023 12:28. Este artigo descreve como
  bloquear a função de hotspot do windows 10 através da linha de comando do
  powershell.
---

# Como bloquear a função hotspot do Windows

## O que é o hotspot do windows 10?

O hotspot do windows 10 é uma função que permite compartilhar a conexão de internet do computador com outros dispositivos, como celulares, tablets, notebooks, etc.

Essa função é muito útil para quem precisa compartilhar a internet do computador com outros dispositivos principalmente em ambientes de uso doméstico ou individual. Mas nem sempre é desejável que essa função esteja disponível, por exemplo, em ambientes corporativos a política da empresa não permite o acesso por meio de dispositivos pessoais.

### Como bloquear o hotspot do windows 10?

Para bloquear o hotspot do windows 10, basta executar o seguinte comando no powershell:

```powershell
REG ADD HKLM\Software\Microsoft\Windows\CurrentVersion\SharedAccess /v EnableRebootPersistConnection /d 4 /f
REG ADD HKLM\SYSTEM\CurrentControlSet\Services\ICSSVC /v Start /t REG_DWORD /d 4 /f
sc config icssvc start= disabled
netsh wlan set hostednetwork mode=disallow
```

Após a execução dos comandos acima é necessário a reinicialização do computador.

Uma vez executado o comando acima, o hotspot do windows 10 estará bloqueado e não será possível mais compartilhar a conexão de internet do computador com outros dispositivos.

### Como desfazer o bloqueio de hotspot do windows 10?

Por motivos de segurança optamos por não divulgar como desativar o bloqueio de hotspot para impedir que usuários alterem a configuração em ambientes corporativos.

Se você é profissional de TI, fale conosco para maiores informações.

{% embed url="https://rmbinformatica.com/contato.html" %}
Entre em contato com a RMB Informatica
{% endembed %}

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><a href="https://app.gitbook.com/u/80TKxE2AwmXcZvJ39blpOlo3yWp2">Renato Monteiro Batista</a></td><td>Engenheiro de Computação</td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Artigos relacionados" %}
* Lista de artigos relacionados
{% endtab %}
{% endtabs %}
