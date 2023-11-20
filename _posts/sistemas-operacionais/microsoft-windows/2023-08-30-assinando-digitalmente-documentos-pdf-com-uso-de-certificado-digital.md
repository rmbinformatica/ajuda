---
title: Assinando digitalmente documentos PDF com uso de certificado digital
author: "Renato Monteiro Batista"
date: 2023-08-30
category: [sistemas-operacionais, microsoft-windows]
layout: post
revisao: 2023-11-20
keywords: windows, pdf, assinatura, digital, certificado, adobe, acrobat
description: >-
  Este artigo descreve o procedimento para assinar digitalmente arquivos PDF,
  usando certificado digital por meio do Adobe Acrobat Reader
---

## Como assinar digitalmente um arquivo PDF usando certificado digital no Adobe Acrobat Reader

Para poder seguir as instruções desse artigo será necessário:

* Possuir o [Adobe Acrobat Reader](https://apps.microsoft.com/store/detail/XPDP273C0XHQH2?ocid=pdpshare) instalado
* Estar com o certificado digital instalado na máquina

Nesse artigo não será detalhado as etapas acima, o foco será somente a etapa de assinatura digital.

### Passo a passo para assinatura de PDF utilizando certificado digital

1 - **Abra** o arquivo PDF

2 - Com o arquivo aberto clique na aba **Ferramentas**

![Aba de ferramentas do Adobe Acrobat Reader]({{site.img}}adobe-reader_seta-ferramentas.png)

3 - Escolha a opção **Certificados**

![Opção Certificados nas ferramentas do Adobe Acrobat Reader]({{site.img}}adobe-reader-certificados.png)

4 - Clique em **Assinar Digitalmente**

![Opção de assinar digitalmente do Adobe Acrobat Reader]({{site.img}}adobe-reader-assinar-digitalmente.png)

5 - **Marque no PDF um local** onde será acrescentado o carimbo indicando que o arquivo foi assinado digitalmente.

![Marque a área da assinatura desenhando um retângulo com o mouse]({{site.img}}adobe-reader-retangulo-assinatura-digital.png)

6 - **Escolha** o **certificado** digital que será usado e clique no botão **Continuar**

![Tela de seleção do certificado digital do Adobe Reader]({{site.img}}adobe-reader-escolha-certificado-digital.png)

7 - Escolha a aparência do carimbo de assinatura, você pode personalizar a fonte etc conforme suas preferências. Depois de escolhida clique no botão **Assinar**.

![Tela de confirmação de assinatura digital no adobe reader]({{site.img}}adobe-reader-confirmacao-assinatura.png)

8 - Indique o **nome do arquivo** que será gravado com a assinatura digital e, em seguida, clique no botão **Salvar**.

![Adobe Reader - Tela de salvar]({{site.img}}adobe-reader-salvar.png)

9 - Caso solicitado digite a senha do certificado digital para confirmar a assinatura.

10 - No arquivo assinado você poderá ver que constará a indicação que o documento foi assinado digitalmente e que a assinatura é válida, bem como o carimbo da assinatura.

![Exemplo de validação de assinatura através do Adobe Reader]({{site.img}}adobe-reader-documento-assinado.png)

## Outras opções de assinatura digital

Outras opções de assinatura digital de arquivos:

* [Assinador ITI](https://assinador.iti.br/) permite assinatura digital de arquivos com uso da conta gov.br sem a necessidade de certificado digital
* [Assinador Serpro](https://www.serpro.gov.br/links-fixos-superiores/assinador-digital/assinador-serpro)
* [E-notariado](https://www.e-notariado.org.br/notary/assinatura) permite assinatura digital com certificado emitido por um cartório local, é cobrado o valor de um reconhecimento de firma para cada assinatura.

> ##### VALIDAÇÃO DE ASSINATURA DIGITAL
>
>Para validar um arquivo assinado digitalmente você também pode fazê-lo através do site [VALIDAR do Instituto Nacional de Tecnologia da Informação](https://validar.iti.gov.br/).
{: .block-tip }
