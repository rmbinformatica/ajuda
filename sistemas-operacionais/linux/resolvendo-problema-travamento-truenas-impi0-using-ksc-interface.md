---
description: Solução para o problema "ipmi0 using KSC interface" que causa travamento no TrueNAS durante o boot do sistema.
---

# Resolvendo problema de inicialização do TrueNAS onde trava na mensagem ipmi0: using KSC interface

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

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% tab title="Artigos relacionados" %}
* [Forum TrueNas: Boot hang: IPMI system interface?](https://www.truenas.com/community/threads/boot-hang-ipmi-system-interface.69103/)
{% endtab %}
{% endtabs %}