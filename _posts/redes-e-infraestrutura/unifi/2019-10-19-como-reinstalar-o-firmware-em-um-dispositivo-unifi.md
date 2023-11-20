---
title: Como reinstalar o firmware em um dispositivo Ubiquiti Unifi
author: "Renato Monteiro Batista"
date: 2019-10-19
category: [redes-e-infraestrutura, unifi]
layout: post
revisao: 2023-11-19
keywords: unifi, ssh, access point, ubiquiti, unifi controller, firmware, upgrade, info, set-inform
description: >-
  Este artigo descreve o procedimento para reinstalação do firmware em um
  dispositivo unifi
---

> ##### LEIA ANTES DE PROSSEGUIR
>
> _**Este procedimento, se realizado de maneira incorreta, pode danificar o dispositivo de maneira definitiva. Se você não se sente seguro para realizar o procedimento ou não entender alguma das etapas do procedimento: NÃO REALIZE!!! Não nos responsabilizamos por eventuais danos causados em dispositivos decorrentes do uso das informações contidas nesse artigo. É recomendado o uso de no-break durante a reinstalação do firmware pois uma eventual falha de energia durante o procedimento irá danificar o equipamento.**_
{: .block-danger }

> ##### CONTRATE NOSSOS PROFISSIONAIS QUALIFICADOS PARA REALIZAR O PROCEDIMENTO
>
> Para realização da reinstalação do firmware do seu dispositivo de maneira correta envie-nos o equipamento para que o procedimento seja realizado pela nossa equipe. [Entre em contato conosco](https://rmbinformatica.com/contato.html) para maiores informações.
{: .block-tip }

## Preparando o dispositivo para reinstalação do firmware

1. Desligue o dispositivo Ubiquiti Unifi
2. Configure seu computador com IP Manual **192.168.1.254** e conecte o cabo do computador diretamente a porta LAN do POE do dispositivo.
3. Pressione o botão reset do dispositivo, mantenha pressionado e ligue o dispositivo, aguarde aproximadamente 8 segundos até que a os [LEDs do dispositivo](cores-do-led-do-unifi) indiquem o modo TFTP (Piscando branco/azul/off para dispositivos mais novos ou laranja/verde/off para modelos antigos).
4. Verifique se o dispositivo responde ping através do ip **192.168.1.20** antes de prosseguir.

## Download do firmware

Realize o download do firmware respectivo ao seu equipamento no [site do fabricante](https://community.ui.com/releases). **Sempre [verifique o hash dos arquivos](http://rmbinformatica.com.br/hash.php) para certificar-se que o arquivo baixado não está corrompido**!

## Instalando o firmware no dispositivo

Conecte-se no dispositivo utilizando o protocolo TFTP e inicie a transmissão do arquivo .bin em modo binário para o dispositivo.

### No MacOS

```bash
meumac:~ usuario$ tftp
tftp> connect 192.168.1.20
tftp> binary
tftp> put [nomeDoArquivo].bin
```

### No Linux 

```bash
root@ubuntu:tftp 192.168.1.20
tftp> bin
tftp> trace
tftp> put [nomeDoArquivo].bin
Sent 1965199 bytes in 35.2 seconds 
tftp> exit
```

### No Windows 10 usando o cmd

```
tftp -i 192.168.1.20 put [nomeDoArquivo].bin
```

O windows possui um cliente de TFTP integrado mas o fabricante também recomenda o [tftp2](https://github.com/rmbinformatica/downloads/raw/main/tftp2.exe) ou o _tftpd64_ que pode ser baixado do [repositório oficial do tftpd64](https://bitbucket.org/phjounin/tftpd64/downloads/) ou do [repositório de downloads da RMB Informática](https://github.com/rmbinformatica/downloads/raw/main/tftpd64.464.zip)

![Cliente TFTP2 para Windows]({{site.img}}tftp2-windows.png)

Após o envio do novo arquivo de firmware aguarde alguns minutos até que os [LEDs do dispositivo](cores-do-led-do-unifi) indiquem o status de padrão de fábrica.

## Veja também

- [Cores do LED do Ubiquiti Unifi](/ajuda/redes-e-infraestrutura/unifi/cores-do-led-do-unifi)
- [Acessando o Ubiquiti Unifi via SSH](/ajuda/redes-e-infraestrutura/unifi/)
- [Instalando o gerenciador Unifi no Linux CentOS](/ajuda/redes-e-infraestrutura/unifi/instalando-o-gerenciador-unifi-no-centos)