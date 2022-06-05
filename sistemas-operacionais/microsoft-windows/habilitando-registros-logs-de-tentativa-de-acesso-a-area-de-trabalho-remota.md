---
description: >-
  Este artigo detalha o passo a passo para habilitar a auditoria de logs de
  acessos com falha na área de trabalho remota do windows
---

# Habilitando registros logs de tentativa de acesso a área de trabalho remota

## Introdução

Pensar em segurança é fundamental, principalmente quando colocamos algum dispositivo online na internet. Nossa recomendação é que esse tipo de acesso seja sempre protegido  por uma VPN, bem como um firewall bem configurado.&#x20;

Infelizmente ainda é muito comum ver pessoas abrindo acesso inseguro à area de trabalho remota do windows na internet. Mas muitas pessoas não tem noção da ameaça a que estão expostas pois a configuração padrão do windows não faz o registro das tentativas de acesso com falha.

Quando se junta um ambiente não protegido com senhas inseguras, ou sistema desatualizado é muito comum sofrer ataques de roubo de dados, vírus, malwares em geral e ransomware. Lembrando que os atacantes normalmente utilizam programas de computador e scripts para ficar 24h por dia tentando invadir as máquinas expostas.

Neste artigo vamos descrever o passo a passo para você habilitar no windows o registro das tentativas de acesso à area de trabalho remota para que você possa ver qualquer login inválido.

## Como habilitar o registro das tentativas de acesso

No iniciar do windows procure o aplicativo **Editar política de grupo**:

![](<../../.gitbook/assets/image (24).png>)

Dentro do aplicativo, no lado esquerdo da tela navegue pelos menus:

### Windows em inglês

* Computer Configuration
* Windows Settings
* Security Settings
* Local Policies
* Audit Policy

### Windows em português

* Configurações do computador
* Configurações do windows
* Configurações de segurança
* Políticas locais
* Política de auditoria

![editor de política de grupo local](<../../.gitbook/assets/image (25).png>)

Você poderá observar que a configuração padrão do windows vem definida para _**sem auditoria**_. Basta clicar duas vezes nesta mensagem e será exibida uma janela, nesta janela marque a opção **falha** e clique no botão OK.

![janela de edição das propriedades](<../../.gitbook/assets/image (26).png>)

Você verá que a opção que antes estava sem auditoria agora estará como falha, conforme imagem abaixo:

![](<../../.gitbook/assets/image (27).png>)

Pronto, essa é toda a configuração necessária. Agora você poderá verificar todas as tentativas de acesso no visualizador de eventos do windows. Nos registros consta os detalhes do login que foi tentado bem como os endereços de IP de quem tentou realizar o acesso, para filtrar somente os eventos de falha de login busque pela identificação de evento **4625**..

Disponibilizamos a seguir um modo de exibição personalizado com as tentativas de login já filtradas, basta utilizar a opção "Importar modo de exibição personalizado de um arquivo" do visualizador de eventos e carregar o arquivo xml a seguir.

{% file src="../../.gitbook/assets/Falha de Login Windows.xml" %}
Modo de exibição personalizado - Falhas de login do windows
{% endfile %}
