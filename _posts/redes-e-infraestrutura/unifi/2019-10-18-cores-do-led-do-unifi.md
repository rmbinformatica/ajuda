---
title: Cores do LED do Ubiquiti Unifi
author: "Renato Monteiro Batista"
date: 2019-10-18
category: [redes-e-infraestrutura, unifi]
layout: post
revisao: 2023-11-19
keywords: unifi, ubiquiti, led, cores, significado, luzes, piscando, azul, branco, uap, uap-lr, uap-outdoor5, uap-ac, uap-ac-pro, uap-ac-lite, uap-ac-lr, uap-ac-m, uap-ac-m-pro, uap-ac-mesh, uap-ac-mesh-pro, uap-ac-hd, uap-ac-shd, adoção, firmware, adotado, adpoted, 
description: Entenda o significado de cada cor do led indicativo dos Access Point Unifi
---

## LED Azul e Branco

LEDs azul e branco se aplicam a todos os access points Ubiquiti Unifi, roteadores e switches com exceção dos dispositivos antigos: UAP, UAP-LR, UAP-Outdoor5.

| Atividade | Descrição | Cor do LED |
| --------- | --------- | ---------- |
| **Inicializando** | AP está iniciando | ![Unifi inicializando]({{site.img}}UAP-AC-1-Initializing.gif) Piscando *Branco* a cada 1/2s |
| **Padrão de fábrica** | AP está aguardando adoção por um controller | ![Unifi em modo padrão de fábrica]({{site.img}}UAP-AC-2-Factory-Defaults.gif) Branco estático |
| **Adotado** | AP está em operação normal | ![Unifi em operação normal]({{site.img}}UAP-AC-4-Adopted.gif) Azul estático |
| **Erro A12** | Reiniciar o dispositivo e contactar o suporte se continuar | ![Unifi em erro A12]({{site.img}}UAP-AC-9-Error-A12.gif) Strobing Branco / Off |
| **Atualizando Firmware** | AP está em processo de upgrade. *NÃO DESLIGUE*! | ![Unifi atualizando firmware]({{site.img}}UAP-AC-7-Firmware-Upgrade.gif) Branco / Azul alternando rápido |
| **Isolado** | AP perdeu a conexão cabeada e está procurando | ![Unifi Isolado]({{site.img}}UAP-AC-5-Isolated.gif) Azul piscando a cada 5s |
| **Localizando** | Recurso de localização do dispositivo através do controller ou app | ![Unifi Localizando]({{site.img}}UAP-AC-6-Locating.gif) Azul piscando e apagando rapidamente |
| **Modo TFTP** | Dispositivo está em modo TFTP para transferência de firmware. Este modo é acionado ao segurar o botão de reset antes de ligar a energia, então permanecer segurando o reset até que a sequência Branco/Azul/Off inicie. Se esse acionamento *não for intencional verifique se o botão de reset está preso*. | ![Unifi modo TFTP]({{site.img}}UAP-AC-TFTP.gif) Flashing Branco-Blue-Off |
| **Offline** | Verificar cabos de energia, POE e rede | ![Unifi desligado]({{site.img}}UAP-AC-8-LED-Off.gif) LED desligado |

{% include gads.html %}

## Dispositivos antigos com LED laranja

Aplica-se aos modelos: UAP, UAP-LR, UAP-Outdoor5.

| Atividade | Descrição | Cor do LED |
| --------- | --------- | ---------- |
| **Inicializando** | AP está iniciando | ![Unifi UAP inicializando]({{site.img}}UAP-1-Initializing.gif) Piscando Laranja / Off a1/2s |
| **Padrão de fábrica** | AP está aguardando adoção no controller | ![Unifi UAP em modo padrão de fábrica]({{site.img}}UAP-2-Factory-Defaults.gif) Laranja estático |
| **Adotado** | AP está em operação normal | ![Unifi UAP Adotado]({{site.img}}UAP-4-Adopted.gif) Verde estático |
| **Erro A12** | Reinicie o equipamento, caso persista contactar suporte | ![Unifi UAP Erro A12 ]({{site.img}}UAP-9-Error-A12.gif) Strobing Laranja / off intermitente |
| **Atualizando firmware** | AP está em upgrade de firmware. *NÃO INTERROMPER*! | ![Unifi UAP atualizando firmware]({{site.img}}UAP-7-Firmware-Upgrade.gif) Verde / Laranja piscando rápido |
| **Isolado** | AP perdeu a conexão de rede e está buscando sinal wifi | ![Unifi UAP isolado]({{site.img}}UAP-5-Isolated.gif) Verde e piscando a cada 5s |
| **Localizando** | Recurso de buscar dispositivo através do controller ou app | ![Unifi UAP Localizando]({{site.img}}UAP-6-Locating.gif) Verde piscando rápido / off |
| **Modo TFTP** | O dispositivo está em modo TFTP para transferência de firmware. Este modo é acionado segurando o botão reset antes de energizar, e mantendo o botão pressionado até que o led fique em Laranja-Verde-Off e repetindo. Se esse modo *não foi acionado intencionalmente verifique se o botão reset não está preso*. | ![Unifi UAP TFTP]({{site.img}}UAP-TFTP.gif) Laranja - Verde - Off |
| **Offline** | Verificar energia, POE e Ethernet | ![Unifi UAP ]({{site.img}}UAP-8-LED-Off.gif) LED Off |


## Veja também

- [Artigo originalmente publicado, em inglês, na página do fabricante](https://help.ubnt.com/hc/en-us/articles/204910134-UniFi-LED-Color-Patterns-for-UniFi-Devices)
- [Acessando o Ubiquiti Unifi via SSH](/ajuda/redes-e-infraestrutura/unifi/)
- [Instalando o gerenciador Unifi no Linux CentOS](/ajuda/redes-e-infraestrutura/unifi/instalando-o-gerenciador-unifi-no-centos)
- [Como reinstalar o firmware em um dispositivo Ubiquiti Unifi](/ajuda/redes-e-infraestrutura/unifi/como-reinstalar-o-firmware-em-um-dispositivo-unifi)
