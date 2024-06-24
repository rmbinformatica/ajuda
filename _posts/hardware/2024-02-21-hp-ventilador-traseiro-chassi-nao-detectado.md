---
title: HP desktop erro 512 Ventilador traseiro do chassi não detectado
author: "Renato Monteiro Batista"
date: 2024-02-21
category: hardware
layout: post
keywords: hp, bios, desktop, fan error, ventilador traseiro do chassi, não detectado
description: Correção do erro 512 Ventilador traseiro do chassi não detectado em desktops HP.
revisao: 2024-02-21
---

## Problema

Ao ligar o computador, o sistema exibe a mensagem de erro 512 "Ventilador traseiro do chassi não detectado" e solicita a tecla F1 para continuar.

### Causas prováveis

1. **Falha no ventilador**: O ventilador traseiro do chassi pode estar com defeito ou desconectado.
2. **Falha na placa-mãe**: O circuito de detecção do ventilador na placa-mãe pode estar com defeito.

## Solução

Para falha no ventilador é recomendada a substituição do componente. Como se trata de um ventilador de chassi, a substituição é simples e pode ser feita por qualquer técnico de hardware.

Caso não possua um ventilador de reposição pode-se realizar o teste com outro cooler de chassi ou de CPU para ver se a placa mãe detecta a rotação do ventilador. A rotação pode ser consultada na Bios (F10), no menu *Alimentação* na opção *Térmico*.

Nos casos onde a ventilador estiver girando mas a placa mãe não detecta, pode ser necessário a substituição da placa mãe ou a reconfiguração da bios para ignorar a detecção do ventilador.

### Desativando a detecção do ventilador

Por padrão, em alguns modelos de Desktop HP a opção de desativar a detecção do ventilador não está disponível na BIOS, sendo necessário acessar o modo de configurações avançadas. Para isso siga os passos:

1. Reinicie o computador e pressione a tecla `F10` para acessar a BIOS.
2. Pressione `Ctrl + A`
3. Pressione `Ctrl + Q`

Feito esses passos a opção de desativar a detecção do ventilador estará disponível na tela de configurações de alimentação.

### Referências

- [HP Community - Error 512 - rear chassis fan not detected](https://h30434.www3.hp.com/t5/Desktops-Archive-Read-Only/Error-512-rear-chassis-fan-not-detected/td-p/945027)