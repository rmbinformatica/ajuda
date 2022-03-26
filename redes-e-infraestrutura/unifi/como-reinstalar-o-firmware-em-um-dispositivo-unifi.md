---
description: >-
  Este artigo descreve o procedimento para reinstalação do firmware em um
  dispositivo unifi
---

# Como reinstalar o firmware em um dispositivo Unifi

## LEIA ANTES DE PROSSEGUIR:

_**Este procedimento, se realizado de maneira incorreta, pode danificar o dispositivo de maneira definitiva. Se você não se sente seguro para realizar o procedimento ou não entender alguma das etapas do procedimento: NÃO REALIZE!!! Não nos responsabilizamos por eventuais danos causados em dispositivos decorrentes do uso das informações contidas nesse artigo. É recomendado o uso de no-break durante a reinstalação do firmware pois uma eventual falha de energia durante o procedimento irá danificar o equipamento.**_

_**Para realização da reinstalação do firmware do seu dispositivo de maneira correta envie-nos o equipamento para que o procedimento seja realizado pela nossa equipe.**_

## Preparando o dispositivo para reinstalação do firmware

1. Desligue o dispositivo
2. Configure seu computador com IP Manual **192.168.1.254** e conecte o cabo do computador diretamente a porta LAN do POE do dispositivo.
3. Pressione o botão reset do dispositivo, mantenha pressionado e ligue o dispositivo, aguarde aproximadamente 8 segundos até que a os [LEDs do dispositivo](cores-do-led-do-unifi.md) indiquem o modo TFTP (Piscando branco/azul/off para dispositivos mais novos ou laranja/verde/off para modelos antigos).
4. Verifique se o dispositivo responde ping através do ip **192.168.1.20** antes de prosseguir.

## Download do firmware

Realize o download do firmware respectivo ao seu equipamento no [site do fabricante](https://www.ui.com/download/). **Sempre verifique o hash dos arquivos para certificar-se que o arquivo baixado não está corrompido**!

## Instalando o firmware no dispositivo

Conecte-se no dispositivo utilizando o protocolo TFTP e inicie a transmissão do arquivo .bin em modo binário para o dispositivo.

{% tabs %}
{% tab title="MacOS" %}
```
meumac:~ usuario$ tftp
tftp> connect 192.168.1.20
tftp> binary
tftp> put [nomeDoArquivo].bin
```
{% endtab %}

{% tab title="Linux" %}
```
root@ubuntu:tftp 192.168.1.20
tftp> bin
tftp> trace
tftp> put [nomeDoArquivo].bin
Sent 1965199 bytes in 35.2 seconds 
tftp> exit
```
{% endtab %}

{% tab title="Windows 10 cmd" %}
```
tftp -i 192.168.1.20 put [nomeDoArquivo].bin
```
{% endtab %}

{% tab title="Cliente FTP Windows" %}
O cliente TFTP windows recomendado pelo fabricante é o [tftp2](https://drive.google.com/file/d/0B768Y1mpfkhGcVpIRmkxRVB3d3c/view)

![](<../../.gitbook/assets/image (21).png>)
{% endtab %}
{% endtabs %}

Após o envio do novo arquivo de firmware aguarde alguns minutos até que os [LEDs do dispositivo](cores-do-led-do-unifi.md) indiquem o status de padrão de fábrica.
