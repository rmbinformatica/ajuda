---
description: >-
  Este artigo descreve informações importantes a respeito da crimpagem de cabos
  ethernet
---

# Orientações importantes sobre a crimpagem de cabos de rede ethernet

Os cabos de rede são componentes modulares, não é utilizada solda para ligar os conectores aos cabos. Todo contato elétrico é realizado por meio de prensa com o auxílio de um alicate específico em um processo chamado de crimpagem.

Deve-se evitar ao máximo o uso de emendas intermediárias, pois essas se tornam um possível ponto de falha com o passar dos anos seja pela oxidação dos contatos ou mal contato devido ao cabo não estar devidamente conectado.

Quando for necessário utilizar emendas essas podem ser feitas utilizando um conector RJ-45 fêmea. Não se deve tentar realizar emendas descascando o cabo da mesma maneira como são feitas emendas de fios elétricos.

## Sequência de cores para crimpar de cabos de rede ethernet

Para uso em redes de computadores, na prática o cabeamento irá funcionar com qualquer sequência de cores, desde que respeitada a mesma sequência na outra ponta. Porém existem duas padronizações principais EIA/TIA 568A e 568B, é recomendado seguir o padrão a fim de facilitar manutenções.

A figura abaixo apresenta a sequência de cores nos dois padrões.

![](../.gitbook/assets/image.png)

### Comprimento mínimo do cabo

É necessário respeitar a distância mínima de 0,5m para evitar que o sinal seja demasiadamente elevado a ponto de indicar uma colisão de pacotes pelo mecanismo de deteção de colisões CSMA/CD.

### Comprimento máximo do cabo

O comprimento máximo do cabo, incluindo todos os patch-cords e quaisquer caixas intermediárias existentes entre as duas pontas deve somar no máximo de 100m.&#x20;

Exemplo: ao se utilizar um patch-cord de 1m em cada lado o comprimento do cabo intermediário deve ser no máximo de 98m.

## Cabo crossover

Em algumas situações é necessário assumir configuração cruzada (crossover), esse tipo de ligação é utilizado principalmente para conexão direta entre a placa de rede de duas máquinas sem o auxílio de um switch, assim como também no caso de cascateamento de equipamentos mais antigos que não possuam porta de uplink.

### Sequência de cores para montagem de um cabo crossover

<table><thead><tr><th>Sinal</th><th data-type="number"># Pino</th><th>Lado 1 (568B)</th><th>Lado 2</th></tr></thead><tbody><tr><td>TD+</td><td>1</td><td>Laranja/branco</td><td>Verde/branco</td></tr><tr><td>TD-</td><td>2</td><td>Laranja</td><td>Verde</td></tr><tr><td>RX+</td><td>3</td><td>Verde/branco</td><td>Laranja/branco</td></tr><tr><td>BD1+</td><td>4</td><td>Azul</td><td>Marrom/branco</td></tr><tr><td>BD1-</td><td>5</td><td>Azul/branco</td><td>Marrom</td></tr><tr><td>RX-</td><td>6</td><td>Verde</td><td>Laranja</td></tr><tr><td>BD2+</td><td>7</td><td>Marrom/branco</td><td>Azul</td></tr><tr><td>BD2-</td><td>8</td><td>Marrom</td><td>Azul/branco</td></tr></tbody></table>

### Mapa de pinagem de um cabo crossover

Considerando o número do conector/pino de um cabo a montagem de um cabo crossover é realizada conectando as seguintes vias:

| Ponta 1 | Ponta 2 |
| ------- | ------- |
| 8       | 5       |
| 7       | 4       |
| 6       | 2       |
| 5       | 8       |
| 4       | 7       |
| 3       | 1       |
| 2       | 6       |
| 1       | 3       |
