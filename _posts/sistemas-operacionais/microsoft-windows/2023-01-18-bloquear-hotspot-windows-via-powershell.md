---
title: Como bloquear a função hotspot do Windows
author: "Renato Monteiro Batista"
date: 2023-01-18
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, hotspot, compartilhamento, internet, bloquear, impedir, windows 10, w10, win10, win 10, windows 11, win11, win 11, w11, desativar, desabilitar, compartilhar, SharedAccess, hostednetwork, icssvc
description: Solução para impedir o compartilhamento de internet do windows utilizando a função hotspot do windows 10. Comandos para bloqueio do compartilhamento hotspot no windows.
---

## O que é o hotspot do windows 10?

O hotspot do windows 10 é uma função que permite compartilhar a conexão de internet do computador com outros dispositivos, como celulares, tablets, notebooks, etc.

Essa função é muito útil para quem precisa compartilhar a internet do computador com outros dispositivos principalmente em ambientes de uso doméstico ou individual. Mas nem sempre é desejável que essa função esteja disponível, por exemplo, em ambientes corporativos a política da empresa não permite o acesso por meio de dispositivos pessoais.

### Como bloquear o hotspot do windows 10?

Para bloquear o hotspot do windows 10, basta executar o seguinte comando no powershell:

```powershell
REG ADD HKLM\Software\Microsoft\Windows\CurrentVersion\SharedAccess /v EnableRebootPersistConnection /d 4 /f
REG ADD HKLM\SYSTEM\CurrentControlSet\Services\ICSSVC /v Start /t REG_DWORD /d 4 /f
sc config icssvc start=disabled
netsh wlan set hostednetwork mode=disallow
```

Após a execução dos comandos acima é necessário a reinicialização do computador.

Uma vez executado o comando acima, o hotspot do windows 10 estará bloqueado e não será possível mais compartilhar a conexão de internet do computador com outros dispositivos.

{% include gads.html %}

### Como desfazer o bloqueio de hotspot do windows 10?

Por motivos de segurança optamos por não divulgar como desativar o bloqueio de hotspot para impedir que usuários alterem a configuração em ambientes corporativos.

Se você é profissional de TI busque o commit `c331c98` do nosso repositório de [ajuda](https://github.com/rmbinformatica/ajuda) no GitHub ou [fale conosco](https://rmbinformatica.com/contato.html).
