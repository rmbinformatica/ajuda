---
title: Como desativar a reinicialização automática do Windows nos erros de Blue Screen Of Death (BSOD)
author: "Renato Monteiro Batista"
date: 2026-04-20
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2026-04-20
keywords: windows, windows 10, windows 11, bsod, desativar reinicialização automática, reinicio automático, desativar reinicio, bsod, blue screen of death, tela azul da morte, exibir bsod, exibir tela azul
description: Como configurar o windows para exibir a Tela Azul (Blue Screen of Death - BSOD) em caso de erros de hardware desativando a reinicialização automática.
---

## Configurando o windows para exibir a tela azul em vez de reiniciar automaticamente

Por padrão o windows vem configurado com a opção de reinicar automaticamente em caso de erros, sem exibir a famosa Tela Azul da Morte (Blue Screen Of Death - BSOD). Porém, em caso de falhas de hardware o ideal é que a tela azul seja exibida para identificar mais facilmente qual o motivo do problema que está causando a reinicialização.

Para mudar a configuração padrão para que o Windows exiba o BSOD em vez de reiniciar automaticamente, siga os passos abaixo:

### 1. Acesse o Painel de Controle - Sistema

Para acessar o **painel de controle - Sistema** você pode simplesmente buscar pela palavra **sistema** na pesquisa do windows e clicar na opção que aparece nos resultados.

![Pesquisar sistema na busca do windows]({{site.img}}windows-pesquisar-sistema.png)

Outra forma de acessar o painel de controle - Sistema é clicar com o **botão direito** no ícone de **Este computador** e, em seguida, clicar na opção **Propriedades**.

![Botão direito Este computador - Propriedades]({{site.img}}windows-botao-direito-computador-propriedades.png)

### 2. Clique na opção Configurações avançadas do sistema

Quando abrir a tela de Painel de controle - Sistema, clique na opção **Configurações avançadas do sistema**, conforme mostrado na imagem abaixo:

![Opção configurações avançadas do sistema]({{site.img}}windows-sistema-configuracoes-avancadas-sistema.png)

### 3. Clique no botão de Configurações na seção Inicialização e Recuperação

Na tela de Propriedades de Sistema, na aba **Avançado**, na seção **Inicialização e Recuperação**, clique no botão **Configurações**.

![Propriedades de sistema - Avançado]({{site.img}}windows-propriedades-sistema-inicializacao-recuperacao-configuracoes.png)

### 4. Desmarque a caixa de seleção Reiniciar automaticamente

Na tela de Inicialização e Recuperação, na seção **Falha do Sistema**, **desmarque** a caixa de seleção **Reiniciar automaticamente**. Em seguida clique no botão **OK**.

![Propriedades de sistema - Avançado]({{site.img}}windows-inicializacao-e-recuperacao.png)

## Automatizando a configuração para exibir BSOD no windows via script

Para automatizar a configuração via script, execute o seguinte comando:

```batch
REG ADD "HKLM\SYSTEM\CurrentControlSet\Control\CrashControl" /v AutoReboot /t REG_DWORD /d 0 /f
```