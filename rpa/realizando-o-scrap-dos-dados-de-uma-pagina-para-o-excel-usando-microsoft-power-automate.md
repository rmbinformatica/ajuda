---
description: >-
  Exemplo de implementação de uma ferramenta de captura de dados de uma página
  web para uma planilha de excel por meio de automação de processo robótico
  (RPA) usando o Microsoft Power Automate
---

# Realizando o scrap dos dados de uma página para o Excel usando Microsoft Power Automate

Clique em novo fluxo, atribua um nome e clique em criar.

No menu de ações, adicionar uma ação iniciar novo navegador, podendo ser escolhido o navegador da sua preferência. Atribua a url. ser acessada.&#x20;

Clique no botão de gravação, ao entrar no modo de gravação acesse a url desejada. Em seguida vá clicando com o botão direito nos campos que deseja extrair os dados, repita os passos para mais de um registro e normalmente o Power Automate já passa a identificar os campos a partir do segundo registro.

No link para a próxima página de resultados, clicar com o botão direito e defina o elemento como paginador. Ao final dos passos clique no botão concluído.

Ao retornar para a tela do fluxo main, clique duas vezes na variável OutputData, vamos modificar o modo de armazenamento de variável para Planilha do Excel.

No menu de ações vamos incluir a ação Salvar o Excel. Clicando duas vezes na variável ExcelInstance dessa ação recém adicionada vamos alterar o modo salvar para Salvar documento como, formato Excel, escolher o caminho e nome do arquivo que será criado com as informações.

Como último passo opcional podemos adicionar uma ação para fechar o excel e o navegador.

Ao fim dos passos, salvar o projeto e depois verificar o funcionamento clicando no botão Executar (símbolo de play ▶️).
