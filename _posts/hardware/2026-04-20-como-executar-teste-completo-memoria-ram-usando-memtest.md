---
title: Como executar o teste completo da memória RAM do computador usando o memtest86+
author: "Renato Monteiro Batista"
date: 2026-04-20
category: [hardware]
layout: post
revisao: 2026-04-20
keywords: hardware, memória, RAM, memória RAM, memory, memtest, memtest86+
description: Como configurar o memtest86+ para realizar o teste completo da memória RAM do computador.
---

## Realize o boot pelo pendrive com o memtest86+

Realize o download do [Memtest86+](https://www.memtest.org) e grave em um pendrive usando o [Rufus](https://rufus.ie/pt_BR/) ou [Ventoy](https://www.ventoy.net/en/download.html). Recomendamos o Ventoy pois com ele você pode criar um pendrive único com diversas ferramentas para vários propósitos. Faça o boot na máquina por esse pendrive.

Quando o memtest86+ iniciar, configure-o para testar toda a memória seguindo os passos:

### 1. Pressione a tecla F1 de Configuração

Na tela inicial do memtest86+ pressione a Tecla **F1** para acessar o menu de configuração.

![Tela inicial do Memtest]({{site.img}}memtest-f1-configuration.png)

### 2. Pressione novamente a tecla F1 para acessar Test Selection

No menu de configuração pressione a tecla **F1** para acessar a tela de **Test Selection**.

![Memtest - Configuration]({{site.img}}memtest-config-f1-test-selection.png)

### 3. Pressione a tecla F5 para Add All tests e depois F10

Na tela de test selection, pressione a tecla **F5** para a opção **Add All tests** e, em seguida, pressione a tecla **F10** para retornar ao menu anterior.

![Memtest - Test selection]({{site.img}}memtest-testselection-f5-all-tests.png)

### 4. Pressione a tecla F2 para acessar Address range

Retornando ao menu inicial, pressione a tecla F2 para acessar a tela de **Address range**.

![Memtest - Configuration]({{site.img}}memtest-config-f2-address-range.png)

### 5. Na tela de Address Range pressione a tecla F3 Test all memory e depois F10

Na tela de Address range pressione a tecla **F3** para a opção **Test all memory** e em seguida pressione a tecla **F10** para retornar ao menu anterior.

![Memtest - Address Range]({{site.img}}memtest-f2-test-all-memory.png)

### 6. No menu de configuração pressione F10 para sair do menu

Ao retornar ao menu de configuração pressione a tecla F10 para sair do menu de configuração.

![Memtest - Configuration]({{site.img}}memtest-config-f10-exit.png)

Aguarde até que o teste de memória conclua, o tempo do teste vai variar conforme a quantidade de memória a ser testada na máquina.

## Conclusão do teste de memória RAM com o memtest86+

Ao concluir o teste de memória RAM o memtest86+ irá exibir um banner de PASS caso não sejam encontrados problemas na memória RAM. Se outra mensagem for exibida indica problemas na memória RAM.

![Memtest - Pass Banner]({{site.img}}memtest-pass-banner.png)