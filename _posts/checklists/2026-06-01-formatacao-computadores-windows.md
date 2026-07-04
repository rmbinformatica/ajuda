---
title: Checklist - Formatação de computadores e reinstalação do Windows
author: "Renato Monteiro Batista"
date: 2026-06-01
category: checklists
layout: post
revisao: 2026-07-04
keywords: checklist, formatacao, windows
description: Checklist para formatação de computadores e reinstalação do Microsoft Windows
---

Antes de iniciar o processo de formatação, é imprescindível realizar o backup de todos os arquivos importantes do usuário. Certifique-se de ter em mãos a chave de ativação do sistema e os drivers de rede salvos em um dispositivo externo. O processo de instalação do Windows 10/11 foi simplificado, mas a atenção na escolha da partição correta evita a perda acidental de dados de outros discos.

## Backup de dados do cliente

- [ ] Realizar uma imagem de disco utilizando o [disk2vhd](https://docs.microsoft.com/en-us/sysinternals/downloads/disk2vhd) para criar um disco virtual idêntico ao disco físico do computador.
- [ ] Desativar licença de antivírus existente do cliente e anotar o código de ativação para reinstalação posterior.
- [ ] Desvincular o office da conta do cliente (logoff) e anotar o e-mail para vinculação posterior.
- [ ] Identificar e relacionar as contas de e-mail configuradas no microsoft outlook. Pode-se utilizar o [nirsoft MailPassview](https://www.nirsoft.net/utils/mailpv.html) para visualizar as senhas salvas caso o cliente não lembre alguma.
- [ ] No painel de controle - mail, para cada arquivo de dados do outlook configurado utilizar o botão "Compactar agora" para reduzir o tamanho do arquivo de dados.
- [ ] Realizar o backup de todos os arquivos de dados do outlook para um disco externo.
- [ ] Anote os serviços de nuvem utilizados pelo cliente e os respectivos logins. Verifique se os arquivos estão sincronizados com a nuvem antes de desvincular as contas.
- [ ] Exportar as senhas salvas em todos os navegadores instalados no computador, caso não estejam sincronizadas com a nuvem.
- [ ] Exportar os favoritos de todos os navegadores instalados no computador, caso não estejam sincronizadas com a nuvem.
- [ ] Anotar caminhos de unidades de rede mapeadas e as respectivas letras de unidade.
- [ ] Verificar se existem arquivos importantes nas pastas Desktop, Documentos, Downloads, Imagens, Músicas e Vídeos. Verifique também se há mais de um usuário no computador e se há arquivos importantes nas respectivas pastas do(s) outro(s) usuário(s).
- [ ] Realize o backup de qualquer outra pasta que o cliente solicitou.
- [ ] Transfira a pasta com todos os backups para um disco externo identificando claramente o nome do cliente e a data do backup.
- [ ] Verifique se há softwares do governo (Imposto de renda, sefip, DIRF, etc) instalados na máquina e utilize a opção de backup de cada um desses softwares que eventualmente estejam em uso na máquina.
- [ ] Certifique-se de possuir, no mínimo, duas cópias em discos externos DIFERENTES de todos os arquivos do backup do cliente. Compare os tamanhos das pastas após o término de cada cópia. Somente prossiga com a formatação depois de certificar-se de que possui realmente DUAS cópias em discos diferentes.
- [ ] Exportar a lista de redes wifi salvas no computador utilizando o [nirsoft WirelessKeyView](https://www.nirsoft.net/utils/wireless_key.html) ou o [script Powershell para listar redes Wifi Conhecidas](https://github.com/rmbinformatica/scripts-windows/blob/master/listar-wifi-senhas-salvas.ps1).
- [ ] Realize uma última inspeção rápida dos arquivos que ficaram no disco do cliente para certificar-se de que não esqueceu nada.
- [ ] Desconecte o hd externo do computador, é recomendável que o disco com o backup permaneça DESCONECTADO da máquina até o término da formatação.

## Formatação e instalação do Windows

- [ ] Se não possuir, crie um pendrive bootável com a imagem do Windows utilizando o Media Creation Tool para [Windows 10](https://www.microsoft.com/pt-br/software-download/windows10) ou [Windows 11](https://www.microsoft.com/pt-br/software-download/windows11).
- [ ] Crie um arquivo autounattend.xml para automatizar a instalação do Windows. Utilize o [Gerador de autounattend.xml](https://instalar-windows.rmbinformatica.com.br/) para criar o arquivo, ou siga a instalação manual.
- [ ] Inicie o computador com o pendrive bootável e instale o Windows.
- [ ] Aguarde a conclusão da instalação do windows
- [ ] Crie uma pasta c:\instalar e copie os instaladores dos programas que serão utilizados pelo cliente (navegador de internet, office, pdf, dropbox, etc).
- [ ] Execute o [Instalador RMB](https://github.com/rmbinformatica/scripts-windows/blob/master/instalador_RMB.bat) para configuração inicial do windows e instalação dos programas básicos.
- [ ] Copie o backup do cliente do hd externo para o disco do computador.
- [ ] Configure o anydesk: Audio - Desativar transmissão e reprodução de audio, Exibição - Melhor velocidade de reação.
- [ ] Instale as ferramentas adicionais de acesso remoto (meshcentral) e RMM (rport) em caso de cliente que possua contrato de suporte com nossa empresa.
- [ ] Configure as redes wifi salvas.
- [ ] Instale todas as atualizações automáticas do windows.
