---
description: >-
  Este artigo descreve todas as configurações necessárias ao funcionamento do
  conectividade social.
---

# Conectividade Social

O conectividade social é um software da caixa usado pelo departamento pessoal e escritórios de contabilidade para envio de arquivos que são exigência legal impostas pelo governo. É um sistema cuja configuração exige muitas etapas e costuma apresentar muitos problemas de compatibilidade com outros programas.

## Instalação do Java

É necessário o java instalado na versão mais atual. Em alguns casos mesmo com o java instalado ao tentar acesso ao site é exibida a mensagem <mark style="color:red;">**O CNS requer utilização do Plug-in Java 1.5.0 ou superior, para executar corretamente em sua máquina. A página não poderá ser carregada, pois não foi detectado uma versão do Plug-in instalado.**</mark>.

Nesse caso recomendamos a remoção/desinstalação de qualquer versão pré-existente do java e a instalação da versão mais atual que pode ser baixada através do site [https://www.java.com/pt-BR/download/](https://www.java.com/pt-BR/download/).

Siga o procedimento normal de instalação do java, não é necessário alterar nenhuma opção nessa etapa. Caso o instalador pergunte se deseja remover versões antigas do java escolha a opção sim para _remover versões anteriores_.

### Configuração do java

Após instalado acesse o **Configurar Java**. Você pode encontrar essa opção em i_niciar - todos os programas - java - configurar java_, ou: _painel de controle - java_.

#### Excluindo arquivos temporários do java e versões em cache de applets

Na aba geral, na seção **Arquivos Temporários na Internet**, clique no botão **Definições** e clicar no botão **Excluir Arquivos...**, na janela que aparece marque todas as opções:

* [x] Rastrear e Resetar Arquivos
* [x] Aplicativos e Applets Armazenados no Cache
* [x] Aplicativos e Applets Instalados

Clique OK para confirmar todas as janelas até sair do configurador do java.

#### Configurações de segurança do Java

Acesse novamente o **Configurar Java** e siga para a aba Segurança. Certifique-se que a primeira caixa de seleção esteja marcada.

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

Configurações Avançadas do java

Na seção Definições de Segurança Avançadas, desmarque a caixa de seleção:

* [ ] TLS 1.0
* [ ] TLS 1.2
* [ ] TLS 1.3

Deixe marcada somente a opção:

* [x] TLS 1.1

Clique no botão **Aplicar** e em seguida clique no botão **OK**.

## Configurações do Internet Explorer

### Habilitar o complemento do java

No internet explorer clique na engrenagem de configurações e no menu clique opção** Gerenciar Complementos**.

![](<../.gitbook/assets/image (73).png>)

Na parte esquerda da tela, escolha na opção **Mostrar**: _Todos os Complementos_. No lado direito da tela certifique-se que todas as opções que contém java encontram-se **habilitadas**.

![](<../.gitbook/assets/image (72).png>)

### Colocar o site da caixa em modo de compatibilidade

No internet explorer clique na engrenagem de configurações e no menu clique na opção **Configurações do Modo de Exibição de Compatibilidade**.

![](<../.gitbook/assets/image (71).png>)

Digite o site `caixa.gov.br`, clique no botão **Adicionar** e, em seguida, no botão **Fechar**.

![](<../.gitbook/assets/image (68).png>)

### Opções da Internet

No internet explorer clique na engrenagem de configurações e no menu clique na opção **Opções da Internet**.

![](<../.gitbook/assets/image (70).png>)

Na aba **Privacidade**, _**DESMARQUE**_ a opção:

* [ ] Ativar Bloqueador de Pop-ups

![](<../.gitbook/assets/image (63).png>)

Após desmarcado, clique no botão **Aplicar**.

Na aba **Segurança**, selecione a zona **Sites confiáveis**, altere o _nível de segurança desta zona_ para **Baixo** e clique no botão **Aplicar**.

![](<../.gitbook/assets/image (62).png>)

Em seguida clique no botão **Sites**.

![](<../.gitbook/assets/image (61).png>)

Preencha a lista de sites abaixo e clique no botão **Adicionar**, _um de cada vez_.

```
https://www.caixa.gov.br
https://*.caixa.gov.br
https://conectividade.caixa.gov.br
```

Após adicionados os três sites, clique no botão **Fechar**.

![](<../.gitbook/assets/image (64).png>)

Clique no botão Aplicar.

Acesse a aba avançadas e na seção Segurança, certifique-se que as caixas de seleção estão marcadas conforme a relação abaixo:

* [ ] Usar SSL 3.0
* [ ] Usar TLS 1.0
* [x] Usar TLS 1.1
* [ ] Usar TLS 1.2
* [ ] Verificar revogação de certificados do servidor
* [ ] Verificar se há certificados revogados do fornecedor

![](<../.gitbook/assets/image (69).png>)

Por fim, clique no botão **Aplicar**. Clique no botão **OK**. _**Feche e reabra o Internet Explorer**_ e, após reabrir o navegador, acesse o site [conectividade.caixa.gov.br](http://conectividade.caixa.gov.br).

## Anti-vírus Kaspersky

Caso utilize o anti-vírus Kaspersky na máquina, altere as configurações do anti-vírus para _**Não verificar conexões criptografadas**_ pois essa configuração pode causar mau funcionamento do site da conectividade social.

_Caso persistam problemas após os procedimentos acima, revise os procedimentos para verificar se não esqueceu de executar alguma das etapas. Persistindo os problemas mesmo após a execução de todas etapas consulte seu técnico de informática para avaliar a necessidade de reinstalação do windows._
