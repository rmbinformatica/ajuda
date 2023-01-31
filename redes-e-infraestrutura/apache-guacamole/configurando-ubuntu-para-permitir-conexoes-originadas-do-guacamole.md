---
description: >-
  Este artigo descreve uma solução para conseguir conectar em servidores linux
  ubuntu 22.04 utilizando o apache guacamole
---

# Configurando ubuntu para permitir conexões originadas do guacamole

## Detalhamento do problema

Devido às bibliotecas de ssh utilizadas pelo apache guacamole, não é possível estabelecer uma conexão ssh com servidores ubuntu. Apresentando a mensagem de erro no log:

`guacd[pid] ERROR: SSH handshake failed.`

## Resolução

{% hint style="info" %}
A solução abaixo deve ser utilizada somente em redes internas, uma vez que os protocolos apresentados podem apresentar risco de segurança por estarem defasados.
{% endhint %}

Edite o arquivo de configuração do sshd:

```bash
sudo nano /etc/ssh/sshd_config
```

Inclua as linhas à seguir:

```
PubkeyAcceptedKeyTypes +ssh-rsa
KexAlgorithms +diffie-hellman-group14-sha1
HostKeyAlgorithms +ssh-rsa
```

Reinicie o serviço SSHD:

```bash
sudo systemctl restart ssh
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}