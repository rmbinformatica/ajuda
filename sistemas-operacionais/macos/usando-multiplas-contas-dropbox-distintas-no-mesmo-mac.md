---
description: >-
  Este artigo descreve como executar o aplicativo de sincronização do dropbox no
  mesmo usuário no MacOS
---

# Usando múltiplas contas dropbox distintas no mesmo Mac

O [Dropbox](https://db.tt/P5toR86EQi) é uma ferramenta fantástica, pela rapidez, confiabilidade e segurança dos dados. Mas em alguns cenários podemos necessitar usar mais de uma conta dropbox, ex.: separar arquivos profissionais dos pessoais, ou separar arquivos de projetos diferentes.

## Pré-requisitos

Instale o Dropbox normalmente e configure sua primeira conta ou conta principal.

## Crie uma versão customizada do Dropbox com o Automator

Abra o automator, escolha novo Aplicativo.

![Tela inicial de novo projeto do automator.](<../../.gitbook/assets/image (29).png>)

Digite a palavra **shell** na busca e clique duas vezes na opção de executar script de shell.

![](<../../.gitbook/assets/image (14) (1).png>)

Copie e cole o script de exemplo abaixo, e faça as devidas modificações:

{% code title="exemplo_script_shell" %}
```bash
bash
HOME=/Volumes/4TERA/DBoxDois /Applications/Dropbox.app/Contents/MacOS/Dropbox &
```
{% endcode %}

No exemplo acima, a pasta onde será feita a sincronização da segunda conta do Dropbox ficará num hd externo cujo caminho é _/Volumes/4TERA_ e o nome da pasta é _DBoxDois_. Modifique conforme sua necessidade.

Nota: o caracter **&** faz com que o aplicativo rode em segundo plano e faz parte do comando, não remover.

Teste o aplicativo utilizando o botão executar do automator:

![](<../../.gitbook/assets/image (5) (1).png>)

Será exibida a tela inicial do Dropbox pedindo para configurar a conta. Configure a segunda conta normalmente. Você poderá observar que haverá mais de um ícone do aplicativo Dropbox na barra superior:

![Duas instâncias do Dropbox em execução](<../../.gitbook/assets/image (18) (1).png>)

Uma vez que estiver satisfeito com os testes, você poderá encerrar o aplicativo dropbox clicando no ícone e sair.

![Saindo do dropbox](<../../.gitbook/assets/image (45).png>)

No automator, abra o menu **Arquivo** e escolha a opção **Salvar**... Escolha qualquer nome e salve o arquivo aonde desejar.

![Tela de salvar do automator](<../../.gitbook/assets/image (64).png>)

Pronto, agora sempre que quiser abrir o sincronizador da outra conta do dropbox basta abrir o arquivo do automator no local salvo.

Repita o processo caso necessite de utilizar mais contas.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}