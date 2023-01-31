---
description: Este artigo descreve como gerar uma chave SSH para uso com o guacamole
---

# Gerando uma chave SSH compatível o Guacamole

## Descrição do problema

Ao tentar conectar via SSH utilizando o Apache Guacamole a conexão não é estabelecida gerando uma entrada de log:

`guacd[pid] DEBUG: Auth key import failed: (null)`

Verifique se a chave privada gerada possui o cabeçalho (primeira linha):

`-----BEGIN OPENSSH PRIVATE KEY-----`

Sendo esse o caso a chave gerada é do novo padrão e não é suportada pela versão atual do guacamole, sendo necessário gerar uma chave cujo cabeçalho seja:

`-----BEGIN RSA PRIVATE KEY-----`

## Resolução

Para resolver esse problema gere uma nova chave ssh com o comando a seguir:

```bash
ssh-keygen -m PEM
```

Utilize a nova chave privada gerada.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}