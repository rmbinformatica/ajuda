---
description: Este artigo descreve dicas técnicas para o uso do software lumion
---

# Lumion

## Resolvendo o problema quando o lumion exibe a mensagem StyleTransfer.dll

Esse problema está ocorrendo devido a atualização da versão 2020 do Windows 10, tanto para novas instalações quando para atualizações automáticas que migraram para esta versão.

Para resolvê-lo, acesse o windows explorer, abra a pasta `C:\Arquivos de Programas\Lumion xx\3rd`

Recorte o arquivo onxruntime.dll e cole na pasta `C:\Arquivos de Programas\Lumion xx`

Feito isto basta abrir o lumion novamente e funcionará normalmente.

## Configurando placa de vídeo AMD para uso do Lumion

1. Clique com o botão direito em um espaço vazio da área de trabalho do windows e escolha a opção **configurações do radeon**
2. Na última aba, altere a opção de _aplicativos em execução_ para **aplicativos com perfil instalado**.
3. Clique em procurar e localize o executável do Lumion na pasta \(_c:\arquivos de programas\Lumion xx_\)
4. Altere a opção do aplicativo _Lumion_ para **Alto desempenho**.

## Configurando placa de vídeo Nvidia para uso do Lumion

1. Clique com o botão direito em um espaço vazio da área de trabalho do windows e escolha a opção **Painel de controle nvidia**
2. Altere o processador gráfico preferido para **Processador nvidia de alto desempenho**.
3. Acesse a aba **configurações do programa** e clique no botão **adicionar**
4. Localize o executável do Lumion na pasta \(_c:\arquivos de programas\Lumion xx_\)
5. Na opção _2 Selecionar o processador gráfico deste programa_ escolha a opção **Processador nvidia de alto desempenho** e salve clicando no botão **aplicar**.



