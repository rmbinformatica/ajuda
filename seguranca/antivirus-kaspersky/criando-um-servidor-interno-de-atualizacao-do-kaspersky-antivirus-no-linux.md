---
description: >-
  Este artigo descreve a instalação e configuração do agente de atualização do
  kaspersky
---

# Criando um servidor interno de atualização do Kaspersky antivírus no linux

No servidor linux onde o serviço de atualização será instalado, crie um diretório onde o atualizador será armazenado e baixe a versão mais recente do [Kaspersky Update Utility](https://support.kaspersky.com/updater3#downloads) adequada a versão do seu sistema operacional.

```bash
mkdir kasper
cd kasper
wget -c https://products.s.kaspersky-labs.com/special/kasp_updater3.0/3.2.0.153/english-20181221.11.081/5f207288/kuu3.2.0.153_x86_64_en.tar.gz
```

Em seguida descompacte o arquivo baixado:

```bash
tar -zxvf kuu3.2.0.153_x86_64_en.tar.gz
```

Altere o arquivo **updater.ini** e habilite as versões de produtos que deverão ser baixadas substituindo false por **true** na seção **ComponentSettings**.

{% code title="updater.ini" %}
```
[ComponentSettings]
KasperskyAntiVirus_16_0_1=true
```
{% endcode %}

Execute o script **uu-console.sh** e aceite os termos de uso.

```bash
./uu-console.sh
```

## Exemplo de script para tarefa cron

Para que esse tipo de cenário funcione corretamente é recomendado que seja agendada uma tarefa **`cron`** que realize o procedimento de atualização regularmente.

{% code title="atualiza_kasper.sh" %}
```bash
#!/bin/bash
cd /root/kasper
./uu-console.sh  -u
lftp -f /root/sync.ftp
```
{% endcode %}

No exemplo acima os arquivos de atualização são copiados para um outro local na rede através da ferramenta [`lftp`](https://lftp.yar.ru/) (linha 4).&#x20;

Linha do arquivo `cron` para execução automática diariamente no horário de 2h da manhã.

```
0 2 * * * /root/atualiza_kasper.sh #Atualizacao definicoes antivirus
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}