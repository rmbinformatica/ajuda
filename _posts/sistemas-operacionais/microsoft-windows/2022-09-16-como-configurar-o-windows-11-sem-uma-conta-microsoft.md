---
title: Como configurar o Windows 11 sem uma conta Microsoft
author: "Renato Monteiro Batista"
date: 2022-09-16
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, conta, microsoft, local, instalar, configurar, sem conta, sem conta microsoft, sem conta hotmail, sem conta live, sem conta outlook, windows 11 sem conta microsoft, windows 11 sem internet, como pular conta microsoft w11, oobe, bypassnro, pular conta microsoft, windows 11, w11, entrar sem conta microsoft, ativar windows 11, ativar windows 11 sem internet, conta offline, iniciar windows sem conta microsoft, configurar, sem internet, burlar conta microsoft, windows sem rede, offline, off-line, windows 11 sem email, iniciar windows sem conta, sem rede, sem wifi, sem wi-fi, sem e-mail, sem email, sem internet, sem conexão, sem conexão com a internet, sem conexão com internet, conta local, conta local windows 11, conta local windows, conta local w11, w11, comando, taskmgr, usar, logar, formatar, entrar, pular, burlar, logar, abrir, acessar, iniciar, win11, pular tela, saltar tela, avançar sem e-mail, avançar sem email,
description: Solução para inicializar windows 11 sem conta Microsoft, usando conta local do sistema Windows e sem a necessidade de conexão à internet para acessar o windows. 
---

## Descrição do problema

A Microsoft recentemente adicionou o Windows 11 Pro na lista de versões que requerem o uso de uma conta Microsoft.

### Mas por que alguém não iria querer ter uma conta Microsoft?

Uma conta Microsoft autentica seu usuário através dos servidores da Microsoft, o que pode causar complicações no acesso em ambientes onde a internet não está disponível ou não é confiável.  Além disso isso levanta uma questão: de quem é a propriedade do computador? É legítimo o fabricante do sistema operacional precisar permitir que você utilize seu computador? Entendemos que a Microsoft está infringindo o direito de propriedade do computador ao fazer esse tipo de exigência.

## Inicializando o Windows sem conexão à internet

### Método A - Inicializar um Windows pré-instalado ou recém instalado sem conexão à internet

Na tela da primeira inicialização do Windows siga o fluxo normal de inicialização:

1. Escolha o país
2. Escolha o layout de teclado
3. Escolha se deseja ou não adicionar um segundo layout de teclado

Feito isso, na tela seguinte, será solicitado que você se conecte à internet. Note que não há a opção de prosseguir sem acesso à internet. Nesta tela pressione a combinação de teclas **SHIFT** + **F10** e surgirá a janela do _prompt de comando_, execute o comando abaixo:

```batch
oobe\bypassnro
```

Pressione **ENTER** para executar o comando e seu computador será reiniciado na tela inicial da inicialização do Windows. Siga novamente os passos 1 a 3 descritos acima e você verá que na tela que solicita conexão de rede haverá uma opção de prosseguir sem conexão à internet.

Assim você poderá prosseguir a inicialização do windows criando uma conta local sem a necessidade de internet.

### Método B - Finalizando o processo de conexão de rede

Na tela da primeira inicialização do Windows siga o fluxo normal de inicialização:

1. Escolha o país
2. Escolha o layout de teclado
3. Escolha se deseja ou não adicionar um segundo layout de teclado

Feito isso, na tela seguinte, será solicitado que você se conecte à internet. Note que não há a opção de prosseguir sem acesso à internet. Nesta tela pressione a combinação de teclas **SHIFT** + **F10** e surgirá a janela do _prompt de comando_, execute o comando abaixo:

```batch
taskmgr
```

O gerenciador de tarefas será exibido, clique em mais detalhes e finalize o processo **Network Connection Flow**.

Feito isso você poderá prosseguir a inicialização do windows sem a necessidade de criar uma conta Microsoft.

## Inicializando o Windows com conexão à internet

### Método C - Removendo o endereço de IP do adaptador

Na tela da primeira inicialização do Windows siga o fluxo normal de inicialização:

1. Escolha o país
2. Escolha o layout de teclado
3. Escolha se deseja ou não adicionar um segundo layout de teclado
4. Estabeleça uma conexão Wifi caso não esteja conectado via cabo de rede
5. Aguarde que o instalador conclua as atualizações do Windows

Quando for exibida a tela exigindo que você faça login na sua conta Microsoft, pressione as teclas **SHIFT** + **F10** e surgirá a tela do _prompt de comando_. Execute o comando a seguir:

```batch
ipconfig /release
```

Feito isso o seu adaptador de rede estará sem endereço de IP atribuído. Na tela onde é exibida a conta Microsoft clique no botão voltar e será exibida uma tela com a opção de criar uma conta local para login no windows.

### Método D - Utilizando um nome de login inválido para conta Microsoft

Na tela da primeira inicialização do Windows siga o fluxo normal de inicialização:

1. Escolha o país
2. Escolha o layout de teclado
3. Escolha se deseja ou não adicionar um segundo layout de teclado
4. Estabeleça uma conexão Wifi caso não esteja conectado via cabo de rede
5. Aguarde que o instalador conclua as atualizações do Windows

Quando for exigido que você forneça sua conta Microsoft simplesmente digite o nome de uma conta local (sem o uso de e-mail), exemplo: _renato_. Na tela seguinte informe a senha desejada para o usuário.

Será exibida a mensagem de que um erro aconteceu, nesse caso basta clicar no botão **avançar** para prosseguir a ativação de uma conta local.
