---
description: >-
  LFTP é um cliente de ftp baseado em linha de comando que permite a elaboração
  de scripts FTP para automatizar tarefas de transferências de arquivos.
---

# LFTP

## Sintaxe da linha de comando

### Executando o LFTP diretamente na linha de comando bash ou utilizando scripts

```bash
lftp [-d] [-e cmd] [-p port] [-u user[,pass]] [site]
```

### Executando um script de comandos do lftp

```
lftp -f script_file
```

## Desabilitando verificação de SSL no LFTP

Para conexão a servidores FTP internos que não possuem certificado SSL instalado pode ser necessário desativar o suporte SSL do LFTP.

```
set ftp:ssl-allow no
```

## Espelhando diretórios locais e remotos

### Trazendo arquivos do servidor remoto para a pasta local

Este procedimento faz o diretório local ficar com a mesma estrutura e arquivos do servidor remoto.

```
mirror
```

### Enviando arquivos do diretório local para o servidor remoto

Este procedimento faz o diretório do servidor remoto ficar com a mesma estrutura e arquivos do diretório local.

```
mirror -R
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Veja também" %}
* [Documentação oficial do LFTP](https://lftp.yar.ru/lftp-man.html)
{% endtab %}
{% endtabs %}