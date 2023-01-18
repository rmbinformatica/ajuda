---
author: Renato Monteiro Batista
date: 2023-01-18 12:28
description: >-
  Por _Renato Monteiro Batista_ em 18/01/2023 12:28.
  Este artigo descreve como bloquear a função de hotspot do windows 10
  através da linha de comando do powershell.
---

# O que é o hotspot do windows 10?

O hotspot do windows 10 é uma função que permite compartilhar a conexão de internet do computador com outros dispositivos, como celulares, tablets, notebooks, etc.

Essa função é muito útil para quem precisa compartilhar a internet do computador com outros dispositivos principalmente em ambientes de uso doméstico ou individual. Mas nem sempre é desejável que essa função esteja disponível, por exemplo, em ambientes corporativos a política da empresa não permite o acesso por meio de dispositivos pessoais.

## Como bloquear o hotspot do windows 10?

Para bloquear o hotspot do windows 10, basta executar o seguinte comando no powershell:

```powershell
REG ADD HKLM\Software\Microsoft\Windows\CurrentVersion\SharedAccess /v EnableRebootPersistConnection /d 4 /f
REG ADD HKLM\SYSTEM\CurrentControlSet\Services\ICSSVC /v Start /t REG_DWORD /d 4 /f
sc config icssvc start= disabled
netsh wlan set hostednetwork mode=disallow
```

Após a execução dos comandos acima é necessário a reinicialização do computador.

Uma vez executado o comando acima, o hotspot do windows 10 estará bloqueado e não será possível mais compartilhar a conexão de internet do computador com outros dispositivos.

## Como desfazer o bloqueio de hotspot do windows 10?

Para desfazer o bloqueio do hotspot do windows 10, basta executar o seguinte comando no powershell:

```powershell
netsh wlan set hostednetwork mode=allow ssid=HotspotWifi key=YourPassword
```