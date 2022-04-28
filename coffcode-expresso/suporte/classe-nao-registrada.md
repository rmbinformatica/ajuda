---
description: >-
  Erro ao tentar configurar o certificado digital no sistema Coffcode Expresso,
  apresenta a mensagem de classe não registrada ao clicar no botão de selecionar
  certificado digital.
---

# Classe não registrada

## Verifique a instalação do certificado digital

Primeiramente verifique se o certificado digital está instalado, uma maneira simples de fazê-lo é tentar acessar o [e-cac da receita federal](https://cav.receita.fazenda.gov.br/autenticacao/login) e verificar se consegue fazer login.

## Registre as classes não registradas

Acesse o prompt de comando (**`cmd`**) através da opção de executar **como administrador** e execute os comandos a seguir:

```batch
cd\coffcode\expresso
regsvr32 capicom.dll
regsvr32 msxml5.dll
```

Se sua instalação foi realizada em um diretório diferente de **`c:\coffcode`** faça os ajustes necessários nos comandos anteriores.

Após a execução do comando deve ser exibida a mensagem de que o registro da classe **obteve êxito** para os dois últimos comandos.

Abra o sistema expresso e tente vincular o certificado digital.
