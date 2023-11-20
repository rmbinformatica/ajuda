---
title: Configurando o Conectividade Social no Windows 11
author: "Renato Monteiro Batista"
date: 2022-04-27
category: [outros, conectividade-social]
layout: post
keywords: conectividade social, windows 11, java, microsoft edge, ie tab, navegador, certificado, a3, caixa, conectividade, social, windows, 11
description: >-
  Este artigo descreve o todas as etapas do procedimento necessário para
  configurar o Windows 11 para acessar o conectividade social da caixa
  utilizando o navegador Microsoft Edge e a extensão IE Tab.
revisao: 2023-11-19
---

O primeiro passo para configurar o Windows 11 para utilizar o conectividade social é a instalação do Java 32 bits, que pode ser baixado na [página de download do Java](https://java.com/pt-BR/download/manual.jsp). Instale o java após o download.

## Configurando o Java para o Conectividade Social no Windows 11

Após instalado acesse o **Configurar Java**. Você pode encontrar essa opção em _iniciar - todos os programas - java - configurar java_, ou: _painel de controle - java_.

### Excluindo arquivos temporários do java e versões em cache de applets

Se o java já estava instalado anteriormente, é recomendado que seja feita uma limpeza nos arquivos temporários do Java. Caso tenha instalado o java agora siga para a etapa [configurações de segurança do java](windows-11-e-conectividade-social.md#configuracoes-de-seguranca-do-java).

Para excluir os arquivos temporários acesse a aba geral, na seção **Arquivos Temporários na Internet**, clique no botão **Definições** e clicar no botão **Excluir Arquivos...**, na janela que aparece marque todas as opções:

* [x] Rastrear e Resetar Arquivos
* [x] Aplicativos e Applets Armazenados no Cache
* [x] Aplicativos e Applets Instalados

Clique OK para confirmar todas as janelas até sair do configurador do java.

### Configurações de segurança do Java

Acesse novamente o **Configurar Java** e siga para a aba **Segurança**. Certifique-se que a primeira caixa de seleção esteja marcada.

* [x] Ativar Conteúdo de Java para aplicativos de browser e Web Start

Certifique-se que o nível de segurança selecionado esteja marcado na opção **Alta**. Em seguida clique no botão **Editar Lista de Sites** e adicione todos os sites da lista abaixo na _Lista de Exceções de Sites_, será necessário adicionar um por um.

```
http://caixa.gov.br
http://conectividade.caixa.gov.br:80/static;cxpostal/applet/cnsenvio.jar
https://conectividade.caixa.gov.br/registro/registrar.m?tkeut=2872728090006ea71ce431cdab2ab7afa7de75254a6ae07a6bb3a840cc18bb16e84dde9ded5e0a7f6a297fd244afa9f7d18a895b6474ff34f73760b1705597925732effb6d7c01ff952c3cb0b849f35b34f150e00fd86fa0732e962d673ffa190c323a3abd398a9f9898fe280cf84109dfafb761bda8f13f96e528a37c086fa2201402100955290&amp;ticketdata=20140210095529&amp;lcr=0
http://cmt.caixa.gov.br
http://cmt.caixa.gov.br/*
http://cmt.caixa.gov.br/cse
http://conectividade.caixa.gov.br
http://conectividade.caixa.gov.br/*
http://conectividade.caixa.gov.br:80
https://conectividade.caixa.gov.br:443
https://conectividade.caixa.gov.br/*
https://conectividade.caixa.gov.br:80
http://conectividade.caixa.gov.br:80/static/sicnsregistro/applet/assinar1.jar
https://conectividade.caixa.gov.br
https://conectividade.caixa.gov.br/registro/registrar.m?null
https://conectividade.caixa.gov.br:443
```

Após adicionar todos os sites acima, siga para a aba **Avançado**.

### Configurações Avançadas do java

Na seção _Definições de Segurança Avançadas_, desmarque a caixa de seleção:

* [ ] TLS 1.0
* [ ] TLS 1.2
* [ ] TLS 1.3

Deixe marcada somente a opção:

* [x] TLS 1.1

Clique no botão **Aplicar** e em seguida clique no botão **OK**.

> ##### DICA PARA CERTIFICADOS A3
>
> Se você precisa utilizar certificados A3 é _necessário_ deixar a opção TLS 1.2 **desmarcada**, ao passo que se você lida com _outros_ sites que precisam do java pode ser necessário deixar as opções TLS 1.0 e/ou 1.2 marcadas. Ao alterar essas configurações verifique se outros sites em java que você acessa continuam funcionando. Para o uso do conectividade social é **necessário** apenas a opção TLS 1.1 habilitada.
{: .block-tip }

## Configurando o navegador Edge para usar o conectividade social

No **Painel de controle** acesse **Opções de internet**.

### Configurações da aba Segurança

Na aba **Segurança**, selecione a zona **Sites confiáveis**, altere o _nível de segurança desta zona_ para **Baixo** e clique no botão **Aplicar**.

![Opções da internet - Segurança - Sites confiáveis]({{site.img}}ie-sites-confiaveis-seguranca-baixa.png)

Em seguida clique no botão **Sites**.

![Opções da Internet - Sites confiáveis]({{site.img}}ie-opcoes-internet-botao-sites-confiaveis.png)

Preencha a lista de sites abaixo e clique no botão **Adicionar**, _um de cada vez_. Para adicionar o último endereço é necessário _desmarcar_ a opção "_Exigir verificação do servidor (https:) para todos os sites dessa zona_".

```
https://www.caixa.gov.br
https://*.caixa.gov.br
https://conectividade.caixa.gov.br
http://conectividade.caixa.gov.br
```

Após adicionados os quatro sites, clique no botão **Fechar**.

![Sites da caixa na lista de sites confiáveis das opções da internet]({{site.img}}ie-sites-confiaveis-caixa.png)

### Configurações da aba privacidade

Na aba **Privacidade**, _**DESMARQUE**_ a opção:

* [ ] Ativar Bloqueador de Pop-ups

![Opções da Internet - Privacidade - Bloqueador Popups]({{site.img}}ie-configuracoes-privacidade-desativar-bloqueador-popup.png)

Após desmarcado, clique no botão **Aplicar**.

### Configurações da aba Programas

Na aba **Programas** clique no botão **Gerenciar Complementos**.

![Opções da internet - Programas - Gerenciar complementos]({{site.img}}w11-propriedades-internet-programas-gerenciar-complementos.png)

Na parte esquerda da tela, escolha na opção **Mostrar**: _Todos os Complementos_. No lado direito da tela certifique-se que todas as opções que contém java encontram-se **habilitadas**. (Para habilitar uma opção basta clicar com o botão _direito_ e escolher _habilitar_.)

![Tela de complementos do navegador com o Java habilitado]({{site.img}}ie-complementos-habilitar-java.png)

### Configurações da aba Avançado

Acesse a aba **Avançado** e, na _seção Segurança_, certifique-se que as caixas de seleção estão marcadas conforme a relação abaixo:

* [ ] Usar protocolo TLS 1.3
* [ ] Usar SSL 3.0
* [ ] Usar TLS 1.0
* [x] Usar TLS 1.1
* [ ] Usar TLS 1.2

> ##### OPÇÕES TLS
>
> A opção _Usar TLS 1.3_ deve ser **desmarcada**. Para uso do conectividade social é necessário que a opção _Usar TLS 1.1_ esteja **marcada**. Se você utiliza certificados do tipo **A3** é necessário **desmarcar** a opção _Usar TLS 1.2_. As opções _Usar SSL 3.0_ e _Usar TLS 1.0_, _verificar revogação de certificados do servidor_ e _verificar se há certificados revogados do fornecedor_ não costumam interferir no funcionamento do conectividade social mas podem impactar o funcionamento de outros sites, com elas desmarcadas o acesso se torna mais rápido mas isso só é recomendado se o navegador Microsoft Edge for utilizado _apenas_ para o conectividade social.
{: .block-tip }

![Tela de configurações do navegador - Opções avançadas de TLS]({{site.img}}navegador-opcoes-avancadas-tls.png)

### Extensão para tornar o Microsoft Edge compatível com o conectividade social

Utilizando o navegador Microsoft Edge acesse a [página da extensão IE Tab na loja de complementos do Edge](https://microsoftedge.microsoft.com/addons/detail/ie-tab/npjkkakdacjaihjaoeliacmecofghagh). Em seguida clique no botão **Obter**.

![Extensão IE-Tab para o Microsoft Edge]({{site.img}}edge-extensao-ie-tab.png)

No pop-up que será exibido, clique no botão Adicionar Extensão.

![Tela de confirmação da instalação da extensão IE Tab no Edge]({{site.img}}edge-confirmacao-instalacao-extensao-ietab.png)

Você pode configurar para a extensão ficar sempre visível clicando no botão extensões e clicando no olho que fica ao lado da extensão IE Tab.

![Exibindo a extensão IE Tab no Edge]({{site.img}}habilitar-extensao-ie-tab-edge.png)

## Acessando o Conectividade Social através da extensão IE Tab

Feito todos os passos acima, para acessar o Conectividade Social, clique no ícone da extensão IE Tab.

![Botão da extensão IE Tab no Edge]({{site.img}}edge-botao-extensao-ie-tab.png)

No primeiro acesso pode ser que a extensão baixe um arquivo chamado `ietabhelper.exe`, basta **executar** esse arquivo ao término do download. Se ocorrer isso após abrir o arquivo clique novamente no ícone da extensão IE Tab.

Uma vez que a extensão esteja aberta, você verá uma tela conforme a imagem abaixo. Digite o endereço conectividade.caixa.gov.br na barra de endereços da extensão, no campo ao lado da palavra _Address_, conforme indicado na seta da imagem abaixo. Após digitar o endereço, pressione a tecla **enter**.

![Acessando o conectividade social no IE Tab pelo Microsoft Edge]({{site.img}}edge-acessar-conectividade-social-ie-tab.png)

O acesso ao Conectividade Social, no Windows 11, deve ser feito sempre utilizando a extensão IE Tab no navegador Microsoft Edge.

Resolveu seu problema? [Lembre de mandar um pix para contribuir com nosso trabalho](/ajuda/colabore-com-nosso-sited). Caso utilize o [anti-vírus Kaspersky](windows-11-e-conectividade-social.md#anti-virus-kaspersky) há uma configuração adicional que precisa ser feita ao final desta página.

## Anti-vírus Kaspersky

Caso utilize o anti-vírus Kaspersky na máquina, altere as configurações do anti-vírus para _**Não verificar conexões criptografadas**_ pois essa configuração pode causar mau funcionamento do site da conectividade social.

_Caso persistam problemas após os procedimentos acima, revise os procedimentos para verificar se não esqueceu de executar alguma das etapas. Persistindo os problemas mesmo após a execução de todas etapas consulte seu técnico de informática para avaliar a necessidade de reinstalação do windows._

## Veja também

* [Usando o Conectividade Social com Windows 10](/ajuda/outros/conectividade-social)
