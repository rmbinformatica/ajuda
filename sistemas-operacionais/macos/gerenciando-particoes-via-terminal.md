---
description: Como alterar o mapa de partições a partir do terminal
---

# Gerenciando partições via terminal

## Listar partições existentes

```bash
diskutil list
```

Em todos os comandos a seguir considere o _N_ de _diskN_ como o identificador do disco, conforme mostrado na listagem do comando acima.

## Desmontando uma unidade de disco

```bash
diskutil umountDisk /dev/diskN
```

## Removendo uma partição GPT

```bash
gpt remove -i 2 /dev/diskN
```

Nesse caso seria removido a partição relativa à entrada # 2 da listagem.

## Removendo todas as partições GPT

```bash
gpt destroy /dev/diskN
```

## Apagando todo o conteúdo de um disco e deixando sem partições

```bash
diskutil zeroDisk /dev/diskN
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}