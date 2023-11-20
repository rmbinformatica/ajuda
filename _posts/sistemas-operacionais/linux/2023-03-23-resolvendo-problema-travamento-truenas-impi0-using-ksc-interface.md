---
title: Resolvendo problema de inicialização do TrueNAS onde trava na mensagem ipmi0 using KSC interface
author: "Renato Monteiro Batista"
date: 2023-03-23
category: [sistemas-operacionais, linux]
layout: post
revisao: 2023-11-20
keywords: truenas, ipmi, ipmi0, ksc, interface, travamento, boot, inicialização, mensagem, erro, problema, solução, fix, howto, tutorial, dica, guia, passo a passo, tutorial, howto, tutorial, dica, guia, passo a passo
description: Solução para o problema "ipmi0 using KSC interface" que causa travamento no TrueNAS durante o boot do sistema.
---

## Detalhamento do problema

O problema ocorre quando o TrueNAS tenta inicializar alguns modelos de Placa de rede Realtek onde há uma incompatibilidade com o IPMI  (Intelligent Platform Management Interface), que é um padrão de interface de gerenciamento de sistema para servidores. Ele permite o monitoramento e gerenciamento remoto de servidores, incluindo o controle de energia, o monitoramento de hardware e o gerenciamento de alertas.

## Solução para o erro ipmi0 Using KSC interface no TrueNAS

Para resolver o problema, siga as seguintes etapas.

### 1 - Desabilite a placa de rede na BIOS/Setup

Se a placa de rede for onboard, é necessário desabilitar a placa de rede LAN na BIOS. Caso seja offboard será necessário remover a placa de rede fisicamente da máquina. Consulte um técnico de informática de sua confiança para realizar essa tarefa.

### 2 - Iniciando o TrueNAS em Single User Mode

Após desativar/remover a placa de rede, ao iniciar o TrueNAS, quando for exibido o menu inicial, escolha a opção 6 (Boot Options). No menu de Boot Options escolha a opção 4 (Single User) e em seguida a opção 1 para retornar ao menu principal. No menu principal escolha a opção 1 ou Enter para Boot no modo Single User.

### 3 - Execute os seguintes comandos no shell

Se for perguntado qual shell usar, escolha o padrão sugerido pressionando Enter. Uma vez que tenha acessado o shell execute os seguintes comandos:

```bash
su -
mount -u -w /
cd /boot/kernel
rm ipmi.ko
rm ipmi_linux.ko
exit
reboot
```

### 4 - Ative a placa de rede novamente

Ao reiniciar o equipamento ative novamente a placa de rede na BIOS/Setup em caso de placa onboard ou insira novamente a placa de rede offboard. Consulte um técnico de informática em caso de dúvidas sobre essa etapa.

## Conclusão

Após a realização dos procedimentos descritos acima o TrueNAS deve iniciar normalmente sem apresentar a mensagem de erro *ipmi0: using KSC interface*.

## Veja também

* [Forum TrueNas: Boot hang: IPMI system interface?](https://www.truenas.com/community/threads/boot-hang-ipmi-system-interface.69103/)