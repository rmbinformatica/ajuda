---
description: >-
  Este artigo descreve a instalação e configuração do agente de atualização do
  kaspersky
---

# Criando um servidor interno de atualização do Kaspersky antivírus no linux

No servidor linux onde o serviço de atualização será instalado, crie um diretório onde o atualizador será armazenado e baixe a versão mais recente do [Kaspersky Update Utility](https://support.kaspersky.com/updater3#downloads) adequada a versão do seu sistema operacional.

```text
mkdir kasper
cd kasper
wget -c https://products.s.kaspersky-labs.com/special/kasp_updater3.0/3.2.0.153/english-20181221.11.081/5f207288/kuu3.2.0.153_x86_64_en.tar.gz
```

Em seguida descompacte o arquivo baixado:

```text
tar -zxvf kuu3.2.0.153_x86_64_en.tar.gz
```

Altere o arquivo **updater.ini** e habilite as versões de produtos que deverão ser baixadas substituindo false por **true** na seção **ComponentSettings**.

```text
nano updater.ini 

[ComponentSettings]
KasperskyAntiVirus_16_0_1=true
```

Execute o script **uu-console.sh** e aceite os termos de uso.

```text
./uu-console.sh
```

## Exemplo de script para tarefa cron

Para que esse tipo de cenário funcione corretamente é recomendado que seja agendada uma tarefa cron que realize o procedimento de atualização regularmente.

{% code title="atualiza\_kasper.sh" %}
```text
#!/bin/bash
cd /root/kasper
./uu-console.sh  -u
lftp -f /root/sync.ftp
```
{% endcode %}

No exemplo acima os arquivos de atualização são copiados para um outro local na rede através da ferramenta [lftp](https://lftp.yar.ru/) \(linha 4\). 

Linha do arquivo cron para execução automática diariamente no horário de 2h da manhã.

```text
0 2 * * * /root/atualiza_kasper.sh #Atualizacao definicoes antivirus
```

