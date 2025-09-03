---
title: Configurando uma nova placa de rede no proxmox via CLI (shell bash)
author: "Renato Monteiro Batista"
date: 2025-09-03 18:36:00 -0300
category: [sistemas-operacionais, linux]
layout: post
revisao: 2025-09-03
keywords: proxmox, rede, configuração, CLI, shell, bash
description: Guia para configurar uma nova placa de rede no Proxmox utilizando a linha de comando.
---

Quando você instala uma nova placa de rede no servidor Proxmox, o sistema operacional (baseado em Debian) normalmente a detecta automaticamente, mas ela ainda precisa ser configurada para uso. Aqui está um passo a passo para identificar e ativar a nova interface:

## 1 - Verificar se o sistema detectou a placa

```bash
ip link show
ip a
```

Isso lista todas as interfaces de rede detectadas (enpXsY, eth0, etc.).

Para ver detalhes do hardware:

```bash
lspci | grep -i ethernet
```

ou, para informações mais completas:

```bash
dmesg | grep -i eth
```

## 2 - Confirmar o nome da nova interface

O Proxmox usa nomes previsíveis para interfaces (enp3s0, enp4s0f1 etc.). Se a placa antiga queimou, o nome da nova pode ser diferente — e isso precisa ser ajustado na configuração de rede.

## 3 - Editar a configuração de rede

Edite o arquivo de configuração de rede:

```bash
nano /etc/network/interfaces
```


Adicione uma nova seção para a nova interface, por exemplo:

```plaintext
auto enp4s0f1
iface enp4s0f1 inet dhcp
```

ou, para um IP estático:

```plaintext
auto lo
iface lo inet loopback

auto vmbr0
iface vmbr0 inet static
    address 192.168.0.10/24
    gateway 192.168.0.1
    bridge_ports enp3s0
    bridge_stp off
    bridge_fd 0
```

Troque bridge_ports para o nome da nova interface detectada no passo 1.

## 4 - Aplicar as mudanças

Reinicie a rede para aplicar as mudanças:

```bash
systemctl restart networking
```

Ou, se preferir, reinicie o servidor:

```bash
reboot
```

## 5 - Verificar a nova configuração

```bash
ip a
ping -c 4 8.8.8.8
```

Verifique se a nova interface está ativa e se você consegue pingar um endereço externo.

## 6 - Atualizar o Proxmox GUI (opcional)

Se você usa a interface web do Proxmox, vá para Datacenter -> Node -> Network e verifique se a nova interface aparece corretamente.

Seguindo esses passos, você deve conseguir configurar e ativar a nova placa de rede no seu servidor Proxmox via linha de comando.

## Dicas adicionais

- Sempre faça backup do arquivo `/etc/network/interfaces` antes de editá-lo.
- Use `ip link set enp4s0f1 up` para ativar a interface manualmente, se necessário.
- Verifique logs em `/var/log/syslog` para mensagens relacionadas à rede.
- Se quiser ver todas as interfaces com detalhes, use:

```bash
ethtool <nome_da_interface>
```

## Referências

- [Proxmox VE Administration Guide](https://pve.proxmox.com/pve-docs/)
- [Debian Network Configuration](https://wiki.debian.org/NetworkConfiguration)
