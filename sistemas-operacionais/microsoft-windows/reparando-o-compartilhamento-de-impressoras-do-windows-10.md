---
description: >-
  Este artigo descreve como reparar a o compartilhamento de impressoras no
  windows que apresenta a mensagem "O windows não pode se conectar à
  impressora." Falha na operação com erro 0x0000011b.
---

# Reparando o compartilhamento de impressoras do Windows 10

## Descrição do problema

Após alguma atualização automática do Windows não é possível conectar-se a uma impressora compartilhada em outro computador na rede, sendo exibida a mensagem abaixo.

![O Windows não pode se conectar à impressora. Falha na operação com erro 0x0000011b.](../../.gitbook/assets/0x0000011b.jpeg)

## Solução

Necessário incluir uma chave no registro do windows, no caminho: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print` incluir uma chave do tipo _Valor DWORD (32 bits)_ com o conteúdo do valor `0`.

A chave de registro deve ser adicionada em todos os computadores, tanto no cliente quanto no servidor onde está compartilhada a impressora. Após o procedimento é necessário reiniciar todos os computadores envolvidos.

Recomenda-se também verificar se todos os computadores estão com todas as atualizações do windows instaladas.

### Arquivo de registro para correção automática

#### Conteúdo do arquivo

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print]
"RpcAuthnLevelPrivacyEnabled"=dword:00000000
```

#### Download do arquivo

{% file src="../../.gitbook/assets/correcao_rpc-0x0000011b.reg" %}
