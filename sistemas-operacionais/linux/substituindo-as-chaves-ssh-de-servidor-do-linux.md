---
description: >-
  Este artigo descreve o processo de substituição das chaves SSH de servidor de
  um linux.
---

# Substituindo as chaves SSH de servidor do linux

## Realize um backup das chaves anteriores

Antes de proceder a substituição das chaves recomendamos o backup das chaves anterior para caso de necessidade futura.

```bash
tar -cf antigo.tar /etc/ssh/*key*
```

## Removendo as chaves antigas

```bash
rm -fv /etc/ssh/*key*
```

## Reiniciando o serviço SSHD

Ao reiniciar o serviço sshd as novas chaves serão geradas automaticamente.

```bash
service sshd restart
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}