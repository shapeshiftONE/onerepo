---
title: Explorando Algoritmos de Consenso
description: Proof of Work vs. Proof of Stake
published: true
date: 2021-12-20T23:02:35.048Z
tags: bitcoin, pos, pow, consenso, algoritimo, educativo
editor: markdown
dateCreated: 2021-12-20T23:02:35.048Z
---

# Explorando Algoritmos de Consenso

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f57ee07bdfea1e7ac96ac_1_tQ_nSdkltp2lDkk2IOGfnw.png)

Os algoritmos de **Consenso** são os mecanismos que permitem que as blockchains permaneçam seguras e recompensem os usuários que atuam como seus guardiões. Os dois tipos de algoritmos de consenso que dominam o cenário das criptomoedas: Prova de Trabalho e Prova de Participação.

Depois de superar a empolgação inicial de comprar seu primeiro bitcoin, você pode se interessar em como a Prova de Trabalho funciona e quais blockchains usam a Prova de Participação.<br/>

## **Prova de Trabalho** (PoW)

Todo o conceito por trás da **Prova de Trabalho** é manter uma rede segura e torná-la confiável, ao mesmo tempo em que recompensa os administradores que contribuem para essa missão. Alguns pioneiros creditam ao inventor do Bitcoin, Satoshi Nakamoto, o primeiro delineamento do algoritmo de Prova de Trabalho no [whitepaper Bitcoin](https://bitcoin.org/bitcoin.pdf) (2008). Embora, na verdade, a ideia original do PoT tenha vindo de um whitepaper anterior: [Pricing via Processing or Combatting Junk Mail](http://www.wisdom.weizmann.ac.il/~naor/PAPERS/pvp.pdf) (1993).<br/>

## Como Funciona a Prova de Trabalho com Bitcoin

Bitcoin é um sistema de pagamento peer-to-peer descentralizado que permite que indivíduos troquem valor entre si, sem a necessidade de terceiros. Cada transação é registrada em um registro financeiro público para que todos possam ver. Esse registro financeiro é também conhecido como blockchain. Os usuários agem como [nodes](https://medium.com/coinmonks/blockchain-what-is-a-node-or-masternode-and-what-does-it-do-4d9a4200938f) e mantêm a rede voluntariamente. O algoritmo de Prova de Trabalho funciona fazendo com que todos os nodes resolvam quebra-cabeças criptográficos. O primeiro minerador a resolver o quebra-cabeça ganha criptomoedas como recompensa.

À medida que os quebra-cabeças são resolvidos, eles se tornam mais desafiadores. Apenas um número finito de bitcoins existirá (21 milhões para ser exato). Isso garante que os bitcoins nunca serão desvalorizados por causa da inflação, da mesma forma que as moedas fiduciárias são desvalorizadas. No entanto, isso também significa que o custo da mineração aumenta ao longo do tempo. Por quê? Porque existem cada vez mais nós, que estão correndo para resolver quebra-cabeças que não são apenas mais difíceis, mas também financeiramente mais recompensadores. Assim, grandes pools de mineração estão se desenvolvendo, tornando o poder de confirmar transações mais centralizado. Um resultado que pode não parecer congruente com os valores do Bitcoin.

Hoje, os mineradores estão coletivamente [usando energia suficiente](https://digiconomist.net/bitcoin-energy-consumption) para abastecer países inteiros. Em resposta a isso, um [post](https://bitcointalk.org/index.php?topic=27787.0) no fórum BitcoinTalk introduziu a ideia de um algoritmo mais eficiente em termos de energia chamado **Prova de Participação** (2011 ).<br/>

## Prova de Participação (PoS)

Um algoritmo de **Prova de Participação** seleciona um node em uma rede para validar o próximo bloco de transações. A seleção é levemente aleatória para garantir que nem todo minerador (chamado de validador, no jargão PoS) esteja competindo ao mesmo tempo e desperdiçando energia.

Onde tudo que um node precisa em um sistema PoS é mais poder de computação, os validadores PoS devem depositar moedas ou investir na rede. Quanto mais moedas um determinado node puder investir na rede, maior a probabilidade de esse node ser selecionado como validador. É por isso que selecionar um validador é um pouco aleatório. Isso garante que os nodes que investem mais moedas não recebam muitas recompensas muito rápido e centralizem o controle da rede.<br/>

## Prova de Trabalho vs. Prova de Participação

O algoritmo de consenso baseado em **Prova de Trabalho** oferece dois benefícios principais. Uma é ser o algoritmo que impulsiona o Bitcoin, a criptomoeda mais valiosa e conhecida do mundo. Em segundo lugar, as pessoas confiam no Bitcoin e em seu registro financeiro. Os entusiastas acreditam que a blockchain do bitcoin sempre será a melhor maneira de proteger uma plataforma pública e sem permissão e manter todos os participantes honestos, apesar de suas falhas.

*Como mencionamos anteriormente*, PoW não é perfeito. Os requisitos de energia da mineração continuarão a aumentar e sobrecarregar a rede elétrica mundial. Os pools de mineração continuarão a aumentar de tamanho e dominarão o processo de validação.

Ter um grande grupo de mineradores dominando mais de 50% da rede e determinando quais transações são validadas e quais não são é conhecido como um [ataque de 51%](https://www.investopedia.com/terms/1/51- ataque.asp). O uso de um modelo **Prova de Participação** reduz a probabilidade de um ataque em 51%. Também é mais rápido, mais eficiente em termos de energia e custa menos para executar um blockchain baseado em PoS.

A desvantagem do PoS é que os ricos ficarão ainda mais ricos e potencialmente controlarão o consenso do blockchain – sem a necessidade de investir em equipamentos ou conhecimentos de mineração. Para tentar combater esse problema, vários projetos de blockchain adotaram o que é conhecido como **Prova de Participação Delegada** (DPoS). Nesse sistema, em vez de os participantes usarem sua riqueza para votar em consenso, eles usam sua riqueza para votar nos delegados. Esses delegados, então, chegam a uma conclusão por consenso. Essa pequena reviravolta torna essencialmente mais difícil se aproveitar do sistema.<br/>

## Criptomoedas Usando Prova de Trabalho

Bitcoin e todos os seus forks (por exemplo, Bitcoin Cash, Bitcoin Gold) usam o mecanismo de consenso **Prova de Trabalho**, assim como a maioria das outras criptomoedas. Chame isso de efeito colateral da escola de pensamento *'se não está quebrado, não conserte'*.

Outros projetos que usam PoW incluem moedas de privacidade como [Monero](https://www.getmonero.org/) ou [Verge](https://vergecurrency.com/), moedas de troca de criptografia descentralizadas como [Digibyte](https:/ /www.digibyte.co/) e blockchains dedicados à construção de aplicativos descentralizados como [Ethereum](https://www.ethereum.org/) *(que será migrado para um modelo PoS em breve).*<br/>

## Criptomoedas Usando Prova de Participação

Como mencionado, a Ethereum atualmente opera usando PoW, mas está se movendo em direção a um protocolo **Prova de Participação** chamado [Casper](https://blockgeeks.com/guides/ethereum-casper/). O Casper permite que a participação de um validador seja reduzida se ele agir de maneira maliciosa. Isso também permite que o blockchain e seus participantes resolvam o problema de agentes mal-intencionados, mesmo quando certos elementos cruciais de informação estão faltando. *Um dilema conhecido como *[*falha bizantina*](https://en.wikipedia.org/wiki/Byzantine_fault)*.*

**Muitos projetos no mundo cripto estão usando um modelo PoS agora:**

* [NavCoin](https://navcoin.org/en): Uma criptomoeda baseada em privacidade.
* [NEO](https://neo.org/): Uma plataforma de contratos inteligentes de código aberto, apelidada de “Ethereum da China”.
* [ARK](https://ark.io/): Um projeto que visa facilitar a construção de blockchains.
* [Komodo](https://komodoplatform.com/): Um projeto que facilita a implementação de soluções corporativas de blockchain.<br/>

## O Objetivo Final de Todos os Algoritmos de Consenso

Seja Prova de Trabalho, Prova de Participação, Prova de Participação Delegada ou qualquer outro tipo de algoritmo de consenso que prevaleça, o objetivo mais amplo será o mesmo: tornar os blockchains mais rápidos, eficientes, escaláveis e imutáveis.

As criptomoedas e blockchains que impulsionarão a humanidade para o futuro podem incluir regras e ideias que ainda nem foram inventadas. Mas essa é uma razão para estar animado, e não preocupado. Olhar para o futuro e explorar aquilo que ainda não conhecemos é a alma da inovação.

---

> Este documento foi publicado originalmente em 10/09/2019 pela Equipe ShapeShift e pode ter sido ligeiramente modificado para tradução pelo fluxo de trabalho de Informação e Globalização para um projeto de arquivamente em andamento.
>
> O artigo original pode ser encontrado [aqui](https://shapeshift.com/library/exploring-consensus-algorithms).


{.is-success}

---

- bounty: true
- amt: 52
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}
