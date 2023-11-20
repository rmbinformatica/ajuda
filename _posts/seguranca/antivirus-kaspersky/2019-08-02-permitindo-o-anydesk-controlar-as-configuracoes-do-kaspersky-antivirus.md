---
title: Permitindo o anydesk controlar as configurações do Kaspersky antivírus
author: "Renato Monteiro Batista"
date: 2019-08-02
category: [seguranca, antivirus-kaspersky]
layout: post
revisao: 2023-11-19
keywords: kaspersky, antivirus, anydesk, acesso, remoto, controle, configuracoes
description: >-
  Esta página descreve instruções de configuração para permitir que um usuário
  remoto, por meio da ferramenta de acesso remoto anydesk, tenha acesso a
  gerenciar as configurações do kaspersky
---

## Configurando o Kaspersky antivírus para permitir o uso por programas de acesso remoto

Por padrão o antivírus Kaspersky antivírus não permite que usuários remotos conectados via anydesk gerenciem as configurações do antivírus.

Para permitir que alguém conectado remotamente a sua máquina através do anydesk configure seu antivírus, é necessário realizar alguns ajustes nas configurações, são eles:

![Clique no ícone da engrenagem na parte inferior esquerda da tela principal do kaspersky]({{site.img}}kaspersky-botao-configuracoes.png)

### Em versões mais novas do anti-vírus Kaspersky

Nas versões mais novas do Kaspersky entre na opção **Geral** do lado esquerdo, ao lado direito procure a seção **Autodefesa** e marque a opção **Permitir o gerenciamento de configurações do Kaspersky por meio de aplicativos de controle remoto**.

![Configurando a auto-defesa do kaspersky para permitir aplicativos de controle remoto]({{site.img}}kaspersky-autodefesa-novo.png)

### Em versões mais antigas do anti-vírus Kaspersky

Abra o menu adicional e clique na opção autodefesa.

![Abra o menu adicional e clique na opção autodefesa]({{site.img}}kaspersky-config-adicional-autodefesa.png)

Se não houver uma opção de **permitir o gerenciamento de configurações do Kaspersky por meio de aplicativos de controle remoto**, desmarque a opção **Ativar autodefesa**.

![Desmarque a opção "ativar autodefesa"]({{site.img}}kaspersky-config-desativar-autodefesa.png)

Pronto, agora o técnico conectado via anydesk conseguirá realizar as configurações no seu antivírus Kaspersky.

Após o acesso remoto finalizado recomendamos ativar novamente a opção autodefesa.
