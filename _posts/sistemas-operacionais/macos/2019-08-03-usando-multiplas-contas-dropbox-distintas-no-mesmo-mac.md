---
title: Usando múltiplas contas dropbox distintas no mesmo Mac
author: "Renato Monteiro Batista"
date: 2019-08-03
category: [sistemas-operacionais, macos]
layout: post
revisao: 2023-11-20
keywords: dropbox, macos, multiplos dropbox
description: >-
  Este artigo descreve como executar o aplicativo de sincronização do dropbox no
  mesmo usuário no MacOS
---

O [Dropbox](https://db.tt/P5toR86EQi) é uma ferramenta fantástica, pela rapidez, confiabilidade e segurança dos dados. Mas em alguns cenários podemos necessitar usar mais de uma conta dropbox, ex.: separar arquivos profissionais dos pessoais, ou separar arquivos de projetos diferentes.

> ##### ESTE MÉTODO NÃO SUPORTA VERSÕES MAIS RECENTES DO DROPBOX
>
> Informamos que esse método não é compatível com as versões mais recentes do Dropbox onde tornou-se obrigatório salvar os arquivos na pasta `~/Library/CloudStorage`. Ainda não temos uma solução compatível com tais versões.
{: .block-danger }

## Pré-requisitos

Instale o Dropbox normalmente e configure sua primeira conta ou conta principal.

## Crie uma versão customizada do Dropbox com o Automator

Abra o automator, escolha novo Aplicativo.

![Tela inicial de novo projeto do automator.]({{site.img}}mac-automator-tela-inicial.png)

Digite a palavra **shell** na busca e clique duas vezes na opção de executar script de shell.

![Criação de novo script Shell no automator]({{site.img}}mac-automator-novo-script-shell.png)

Copie e cole o script de exemplo abaixo, e faça as devidas modificações:

```bash
bash
HOME=/Volumes/4TERA/DBoxDois /Applications/Dropbox.app/Contents/MacOS/Dropbox &
```

No exemplo acima, a pasta onde será feita a sincronização da segunda conta do Dropbox ficará num hd externo cujo caminho é _/Volumes/4TERA_ e o nome da pasta é _DBoxDois_. Modifique conforme sua necessidade.

Nota: o caracter **&** faz com que o aplicativo rode em segundo plano e faz parte do comando, não remover.

Teste o aplicativo utilizando o botão executar do automator:

![Botão de executar do automator]({{site.img}}mac-automator-botao-executar.png)

Será exibida a tela inicial do Dropbox pedindo para configurar a conta. Configure a segunda conta normalmente. Você poderá observar que haverá mais de um ícone do aplicativo Dropbox na barra superior:

![Duas instâncias do Dropbox em execução]({{site.img}}mac-dois-dropbox.png)

Uma vez que estiver satisfeito com os testes, você poderá encerrar o aplicativo dropbox clicando no ícone e sair.

![Saindo do dropbox]({{site.img}}mac-desligando-dropbox.png)

No automator, abra o menu **Arquivo** e escolha a opção **Salvar**... Escolha qualquer nome e salve o arquivo aonde desejar.

![Tela de salvar do automator]({{site.img}}mac-salvar-como.png)

Pronto, agora sempre que quiser abrir o sincronizador da outra conta do dropbox basta abrir o arquivo do automator no local salvo.

Repita o processo caso necessite de utilizar mais contas.