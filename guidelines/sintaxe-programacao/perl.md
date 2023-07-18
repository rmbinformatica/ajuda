---
description: >-
  Estruturas de sintaxe básicas do Perl.
---
## Estruturas de sintaxe básicas do Perl

### Comentários em Perl

Comentários são blocos de texto que não são interpretados pela linguagem de programação. Eles são utilizados para documentar o código, explicar o que está sendo feito, ou para desabilitar uma parte do código.

```perl
# Isto é um comentário de uma linha

=pod
Isto é um comentário
de múltiplas linhas
=cut
```

### Declaração de variáveis em Perl

```perl
# Variável escalar
$var = "Perl";
```

### Declaração de arrays em Perl

```perl
# Array
@array = ("Foo", "Bar", "Baz");
```

### Ler input do usuário, atribuir a uma variável e depois imprimir na tela em Perl

```perl
# Ler um input do usuário e guardar na variável nome
print "Qual é o seu nome? ";
$nome = <>;

# Remover a quebra de linha do final da variável nome
chomp $nome;

# Imprimir a variável nome
print "Olá, $nome!\n";
```

## Estruturas de seleção em Perl

### if em Perl

```perl
# Testar uma expressão usando if
if (EXPRESSÃO) {
  # Executar este bloco se a expressão for verdadeira
}

# Testar uma expressão usando if e else
if (EXPRESSÃO) {
  # Executar este bloco se a expressão for verdadeira
} else {
  # Executar este bloco se a expressão for falsa
}

# Testar uma expressão usando if, elsif e else
if (EXPRESSÃO1) {
  # Executar este bloco se a expressão1 for verdadeira
} elsif (EXPRESSÃO2) {
  # Executar este bloco se a expressão2 for verdadeira e a expressão1 for falsa
} else {
  # Executar este bloco se nenhuma das expressões anteriores for verdadeira
}
```

### switch em Perl

```perl
# Importar o módulo Switch
use Switch;

# Testar o valor de uma variável usando switch
switch ($VARIÁVEL) {
  case VALOR1 {
    # Executar este bloco se a variável for igual a VALOR1
  }
  case VALOR2 {
    # Executar este bloco se a variável for igual a VALOR2
  }
  else {
    # Executar este bloco se a variável não for igual a nenhum dos valores anteriores
    # Este é o caso default
  }
}
```

## Estruturas de repetição em Perl

### for em Perl

```perl
# Iterar sobre uma lista de valores com um passo usando for
for ($i = 1; $i <= 10; $i += PASSO) {
  # Executar este bloco para cada valor de i
}
```

### while em Perl

```perl
# Executar um bloco de código enquanto uma expressão for verdadeira usando while
while (EXPRESSÃO) {
  # Executar este bloco enquanto a expressão for verdadeira
}
```

### do while em Perl

```perl
# Executar um bloco de código pelo menos uma vez e enquanto uma expressão for verdadeira usando do-while
do {
  # Executar este bloco pelo menos uma vez
} while (EXPRESSÃO);
```

### foreach em Perl

```perl
# Iterar sobre uma lista
@lista = (1, 2, 3, 17);
foreach $valor (@lista) {
  print "O valor atual é $valor\n";
}

# Iterar sobre um hash
%hash = (
  "um" => 1,
  "dois" => 2,
  "três" => 3,
  "dezessete" => 17
);
foreach $chave (keys %hash) {
  print "\$hash{$chave} => $hash{$chave}\n";
}
```

Mais detalhes e exemplos em [Perl for loop - perlmaven.com](https://perlmaven.com/perl-for-loop).

## Funções em Perl

```perl
# Declarar uma função chamada soma que recebe dois parâmetros
sub soma {
  my ($a, $b) = @_; # Atribui os elementos do array @_ às variáveis locais a e b
  return $a + $b; # Retorna a soma de a e b
}

# Declarar uma função chamada multiplica que recebe dois parâmetros
sub multiplica {
  my ($a, $b) = @_; # Atribui os elementos do array @_ às variáveis locais a e b
  $a * $b; # Retorna o produto de a e b sem usar o comando return
}

# Chamar as funções e imprimir seus valores de retorno
print "O resultado da soma é " . soma(3, 4) . "\n"; # Imprime "O resultado da soma é 7"
print "O resultado da multiplicação é " . multiplica(3, 4) . "\n"; # Imprime "O resultado da multiplicação é 12"
```

Mais detalhes e exemplos em [Perl Functions - Tutorialspoint](https://www.tutorialspoint.com/perl/perl_functions.htm).

## Links úteis

- [Perl Documentation](https://perldoc.perl.org/)

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}
