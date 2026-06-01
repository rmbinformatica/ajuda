---
title: Como ver quantos slots de memoria estão ocupados e o tipo da memória instalada no windows sem precisar abrir o computador?
author: "Renato Monteiro Batista"
date: 2026-06-01
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2026-06-01
keywords: windows, windows 10, windows 11, cmd, wmic, memory, memória, tipo de memória, frequência, slots ocupados, prompt de comandos
description: Como ver quais as memórias estão instaladas no computador a partir do prompt de comandos do windows.
---
## Método A - Exibindo quantas memórias e o tipo das memórias instalados no computador a partir do prompt de comandos do Windows

É possível identificar qual memória RAM está instalada no computador, bem como sua velocidade, sem a necessidade de abrir fisicamente o computador, através do prompt de comando do windows. Para fazê-lo, siga os passos:

### 1. Acesse o prompt de comando

Pressione a combinação de teclas **Windows + R**, quando abrir a janela *Executar*, digite `cmd` e pressione *Enter*.

### 2. Execute no prompt de comando

Quando a janela do prompt de comando abrir, execute o comando abaixo e pressione enter:

```
wmic memorychip get devicelocator, capacity, speed, manufacturer, partnumber
```

Será exibido um resultado no formato:

```text
Capacity    DeviceLocator  Manufacturer  PartNumber          Speed
8589934592  DIMM1          999900009999  SXXXXXXXXXXXXXXXXG  3200
8589934592  DIMM2          999900009999  SXXXXXXXXXXXXXXXXG  3200
```

O valor da capacidade é dado em bytes, para saber em Gigabytes, divida o valor que apareceu em capacity `8589934592` por `1073741824`.

No exemplo acima estão instalados no computador dois módulos de **8GB** de velocidade **3200** e do modelo **SXXXXXXXXXXXXXXXXG**.

> ##### ALGUMAS VERSÕES MAIS RECENTES DO WINDOWS PODEM NÃO TER A FERRAMENTA WMIC
>
> Algumas versões mais recentes do Microsoft Windows podem não trazer a ferramenta wmic instalada, se for o seu caso vai ser exibida a mensagem de comando não encontrado, tente o método 2.
{: .block-tip }

## Método B - Exibindo quantas memórias e o tipo das memórias instaladas no computador a partir do PowerShell do Windows

Também é possível realizar o mesmo procedimento via PowerShell, siga os passos:

### 1. Acesse o PowerShell

Clique com o botão **direito** no botão **Iniciar** do windows e escolha **Terminal** ou **PowerShell**, a depender da versão do Windows.

### 2. Execute no PowerShell

Quando a janela do PowerShell abrir, execute o comando abaixo e pressione enter:

```powershell
Get-CimInstance -ClassName Win32_PhysicalMemory | Select-Object BankLabel, Capacity, Speed, MemoryType, SMBIOSMemoryType
```

Será exibido na tela o resultado no formato:

```text
BankLabel        :
Capacity         : 8589934592
Speed            : 3200
MemoryType       : 0
SMBIOSMemoryType : 26

BankLabel        :
Capacity         : 8589934592
Speed            : 3200
MemoryType       : 0
SMBIOSMemoryType : 26
```

O valor da capacidade é dado em bytes, para saber em Gigabytes, divida o valor que apareceu em capacity `8589934592` por `1073741824`.

No exemplo acima estão instalados no computador dois módulos de **8GB** de velocidade **3200**.

A informação `SMBIOSMemoryType` identifica o tipo da memória, na tabela abaixo listamos os mais comuns:

| SMBIOSMemoryType | Tipo da memória |
|------------------|-----------------|
| 20 | DDR   |
| 21 | DDR2  |
| 24 | DDR3  |
| 26 | DDR4  |
| 34 | DDR5  |

