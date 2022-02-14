---
title: Biblioteca HDWallet do ShapeShift
description: Simplifique a integração da carteira com nossa nova biblioteca de código aberto.
published: false
date: 2021-12-20T23:03:00.678Z
tags: bitcoin, hdwallet, cripto, carteira cripto, dev, desenvolvimento
editor: markdown
dateCreated: 2021-12-20T23:03:00.678Z
---

# Biblioteca HDWallet do ShapeShift

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f4822e79cc78c7a46d920_1_ds0x4HwcR-BDsq1MDoSCDw.png)


Problemas **não ortodoxos** geralmente exigem soluções não ortodoxas, e em nenhum lugar isso é mais prevalente do que no mundo ainda nascente da tecnologia blockchain. A equipe da [ShapeShift](http://shapeshift.com/) enfrentou o problema de interface das carteiras de vários fornecedores. Nossa solução foi construí-las e as disponibilizá-las em código aberto para a comunidade.

Reserve um momento para ler sobre o problema que enfrentamos que motivou esse design e como nossa solução HDWallet funciona. **Esperamos que você goste.**

*Encontre nossa página de recursos para desenvolvedores aqui:* [*pages.shapeshift.com/developer-portal*](https://pages.shapeshift.com/developer-portal/)

## **O Problema**

Os aplicativos que desejam fazer interface com várias carteiras precisam criar uma integração para cada carteira. Isso significa que para cada chamada que você deseja fazer, como obter um endereço ou assinar uma transação, você deve escrever um novo código para cada carteira.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f487c5e020326f42a1e7c_1*S73qLZhEFp_34MWa2C-L5Q.png)

## **A Solução**

Para resolver esse problema, construímos a camada de abstração HDWallet. Nós acreditamos e seguimos práticas de codificação DRY (don’t repeat yourself / não se repita) e design simples.

Com o HDWallet, seu código pode fazer uma chamada para a interface do HDWallet e, dependendo da carteira à qual você está conectado, o HDWallet traduzirá essa chamada para as especificações que cada tipo de carteira exige.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f487c75a6fe699a90b7f0_1*oLH61LKwuwowKgURNhWO9g.png)

[*>>> Confira nossa biblioteca de carteiras HD de código aberto no GitHub <<<*](https://github.com/shapeshift/HDWallet)

## **<br/>Como Isso Funciona**

O HDWallet possui um módulo separado para cada carteira com a qual se integra. Você pode vê-los no código no diretório /packages. Cada um desses módulos contém submódulos necessários que permitem a comunicação com a carteira. Há também um módulo HDWallet-core que contém funções que você precisará, independentemente da carteira à qual você esteja se conectando.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f487c02aad5cdf2fb04de_1*2H75EPG9eTVxV2uh6cj-XQ.jpeg)

## **<br/>Como Começar**

Se você estiver interessado em aprender mais sobre o HDWallet, dê uma olhada em nossos exercícios para desenvolvedores [aqui](https://codesandbox.io/s/github/keepkeyjon/teach-hdwallet/tree/master/exercises/01-pair- dispositivo?de-incorporado)). Damos exemplos práticos para navegar pelos recursos aprimorados que essa interface oferece.

Acesse todos os nossos recursos de desenvolvedor para a biblioteca HDWallet de código aberto do ShapeShift, a API ShapeShift Exchange e a API CoinCap em nosso [site](https://pages.shapeshift.com/developer-portal/).<br/>

---

> Este documento foi publicado originalmente em 30/09/2019 pela Equipe ShapeShift e pode ter sido ligeiramente modificado para tradução pelo fluxo de trabalho de Informação e Globalização para um projeto de arquivamento em andamento.
>
> O artigo original pode ser encontrado [aqui](https://shapeshift.com/library/shapeshift-hdwallet-library).

{.is-success}

---

- bounty: true
- amt: 19
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}
