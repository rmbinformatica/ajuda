---
title: Quais chaves de registro altrear manualmente para receber as Atualizações de Segurança Estendidas do windows 10?
author: "Renato Monteiro Batista"
date: 2025-11-24
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2025-11-24
keywords: windows, windows 10, esu, atualizações, atualização, atualizacao, windows update, update, atualizacao seguranca estendida, registro, registry, ESUEligibility, ESU Eligibility, ConsumerESU, consumer esu, esuTouLink, esuPrivacyLink
description: Este artigo descreve como habilitar manualmente as atualizações de segurança estendidas do windows 10 através de alterações de chaves do registro do windows.
---

## Quais chaves de registro altrear manualmente para estender as atualizações automáticas do windows 10?

Em alguns computadores foi observado que ao tentar se registrar n programa ESU (Atualizações de Segurança Estendidas) do windows 10 era exibida a mensagem **você concorda com os {esuTouLink} e as {esuPrivacyLink}."**, seguida da informação **Algo deu errado** e **Não foi possível registrar você nas Atualizações de Segurança Estendidas neste momento. Feche esta janela e tente novamente.** o que impedia dos usuários de continuarem a receber as atualizações nessas máquinas tornando os dispositivos vulneráveis.

Para esses casos a solução foi incluir as chaves de registro manualmente para indicar ao windows que o dispositivo já está inscrito no programa ESU de modo que ele continue buscando as atualizações.

### Arquivo de registro para registro automático no ConsumerESU

```text
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Windows\ConsumerESU]
"ESUEligibility"=dword:00000003
"ESUEligibilityResult"=dword:00000001
```

O download do arquivo da [registro automático ConsumerESU](https://github.com/rmbinformatica/downloads/blob/main/esu.reg) pode ser realizado diretamente do nosso GitHub.