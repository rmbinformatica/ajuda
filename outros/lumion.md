---
description: Este artigo descreve dicas técnicas para o uso do software lumion
---

# Lumion

## Resolvendo o problema quando o lumion exibe a mensagem StyleTransfer.dll

Esse problema está ocorrendo devido a atualização da versão 2020 do Windows 10, tanto para novas instalações quando para atualizações automáticas que migraram para esta versão.

Para resolvê-lo, acesse o windows explorer, abra a pasta `C:\Arquivos de Programas\Lumion xx\3rd`

Recorte o arquivo `onxruntime.dll` e cole na pasta `C:\Arquivos de Programas\Lumion...`

Feito isto basta abrir o lumion novamente e funcionará normalmente.

## Configurando placa de vídeo AMD para uso do Lumion

1. Clique com o botão direito em um espaço vazio da área de trabalho do windows e escolha a opção **configurações do radeon**
2. Na última aba, altere a opção de _aplicativos em execução_ para **aplicativos com perfil instalado**.
3. Clique em procurar e localize o executável do Lumion na pasta (`c:\arquivos de programas\Lumion...`)
4. Altere a opção do aplicativo `Lumion`_` para **Alto desempenho**.

## Configurando placa de vídeo Nvidia para uso do Lumion

1. Clique com o botão direito em um espaço vazio da área de trabalho do windows e escolha a opção **Painel de controle nvidia**
2. Altere o processador gráfico preferido para **Processador nvidia de alto desempenho**.
3. Acesse a aba **configurações do programa** e clique no botão **adicionar**
4. Localize o executável do Lumion na pasta (_c:\arquivos de programas\Lumion xx_)
5. Na opção _2 Selecionar o processador gráfico deste programa_ escolha a opção **Processador nvidia de alto desempenho** e salve clicando no botão **aplicar**.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}