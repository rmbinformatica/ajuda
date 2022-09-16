---
description: >-
  Este artigo descreve como configurar o Windows 11 com uma conta local sem a
  necessidade de utilizar uma conta Microsoft
---

# Como configurar o Windows 11 sem uma conta Microsoft

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

```
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

```
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

```
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
