---
description: Orientações sobre o mysql
---

# MySQL

## mysqldump

O _mysqldump_ é uma ferramenta muito útil para backup de banco de dados mysql. Mas é preciso se atentar para algumas questões no uso dessa ferramenta.

### Sintaxe básica

A sintaxe padrão para uso do mysqldump é:

```bash
mysqldump -u [usuario] [banco] [tabela]
```

Se a tabela for omitida será feito o dump de todo o banco de dados. Para realizar o dump de todos os bancos de dados existentes no servidor basta incluir na linha de comando `--all-databases`.

Para automatização de scripts para rotinas de backup do banco de dados pode ser criado um usuário para essa finalidade, com permissões de leitura do banco e que possa fazer login a partir do localhost sem a necessidade de senha. Caso o usuário em questão possua senha é necessário incluir no comando `-p`.

Por padrão o mysqldump irá exibir o resultado na tela, sendo muito comum direcionar a saida para um arquivo acrescentando `> arquivo.sql` ao final do comando.

### Salvamento o resultado em um arquivo

Embora seja muito comum, o salvamento usando `> arquivo.sql` não é uma boa prática, principalmente quando se envolve a cópia do arquivo entre sistemas operacionais diferentes, esse uso pode fazer com que o arquivo resultante apresente dados corrompidos tais como problemas de acentuação.&#x20;

Para evitar que haja problemas de acentuação com o uso do mysqldump ou qualquer outra corrupção de dados, é recomendado salvar o arquivo usando a opção `--result-file=arquivo.sql` ou `-r arquivo.sql`.

Exemplo para salvar arquivo com nome backup.sql:

```bash
mysqldump -u [usuario] [banco] -r backup.sql
```

### Desabilitando o trancamento de tabelas

Em alguns cenários de uso pode ser necessário evitar que o mysqldump inclua no arquivo as chamadas para trancar e destrancar as tabelas com lock e unlock.

Arquivos contendo lock tables e que por algum motivo não consigam ser processados por completo podem deixar as tabelas trancadas e causar dor de cabeças na hora de acessar o servidor.

Por exemplo: se a única forma de acesso ao servidor for via phpMyAdmin e as tabelas estiverem trancadas o phpMyAdmin pode travar e não funcionar corretamente.

Para desativar o trancamento de tabelas basta acrescentar a linha de comando a opção `--skip-add-locks`.

```bash
mysqldump -u [usuario] [banco] --skip-add-locks -r backup.sql
```

### Replace em vez de insert

Para se restaurar um banco de dados que contenha triggers que realizem inserções em outras tabelas pode gerar problemas na importação do arquivo de dump em decorrência de chaves duplicadas.

Em um cenário de restauração completa onde o banco de dados está vazio uma alternativa para fazê-lo poderia ser remover as triggers que se enquadram nessa situação.

Mas considerando que há cenários que não seja possível desativar as triggers o ideal é que o arquivo de dump tenha sido criado com a opção `--replace` pois nesse caso o mysqldump irá gerar as linhas de inserção com o comando `REPLACE` em vez do `INSERT`.

```bash
mysqldump -u [usuario] [banco] --replace -r backup.sql
```

### Trabalhando com colunas binárias

Se o banco em questão possuir colunas binárias, tais como uuid. É importantíssimo o uso da opção `--hex-blob` a fim garantir que os dados binários sejam gravados de maneira correta.

```bash
mysqldump -u [usuario] [banco] --hex-blob -r backup.sql
```

### Definindo o charset

Em alguns casos abrir o arquivo exportado pelo mysqldump no workbench pode apresentar uma mensagem reclamando do charset do arquivo. Conforme imagem abaixo:

![Erro quando o workbench não consegue identificar o charset do arquivo](<../.gitbook/assets/image (22).png>)

Uma das maneiras de contornar esse problema seria definir o charset na geração do arquivo no mysqldump através da opção `--default-character-set=[charset]`.

Exemplo, para salvar o arquivo com o charset _latin1_:

```bash
mysqldump -u [usuario] [banco] --default-character-set=latin1 -r backup.sql
```

### Exportando somente os dados sem a estrutura de tabelas

Para exportar somente o DML, sem a estrutura das tabelas (DDL), é recomendável a combinação das opções `--no-create-info` e `--skip-triggers` caso exista alguma tabela com triggers.

### Combinando opções

Todas as opções disponíveis para linha de comando do mysqldump podem ser combinadas em qualquer ordem. Exemplo:

```bash
mysqldump -u [usuario] --no-create-info --skip-triggers [banco] --default-character-set=latin1 --hex-blob --replace --skip-add-locks -r [arquivo]
```

Para uma lista de todas as opções disponíveis e seu uso, consulte a [documentação oficial do mysqldump](https://dev.mysql.com/doc/refman/8.0/en/mysqldump.html).
