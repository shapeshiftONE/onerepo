---
title: Explorando Algoritmos de Consenso
description: Prueba de Rrabajo frente a Prueba de Participación
published: true
date: 2022-02-24T02:21:23.461Z
tags: archivo, biblioteca
editor: markdown
dateCreated: 2022-02-24T02:21:23.461Z
---

# Exploring Consensus Algorithms

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f57ee07bdfea1e7ac96ac_1_tQ_nSdkltp2lDkk2IOGfnw.png)

Los algoritmos de **consenso** son los mecanismos que permiten que las cadenas de bloques permanezcan seguras y recompensan a los usuarios que actúan como sus guardianes. Los dos tipos de algoritmos de consenso que dominan el panorama de las criptomonedas: Prueba de trabajo y Prueba de participación.

Una vez que supere la emoción inicial de comprar su primer bitcoin, es posible que le interese saber cómo funciona la Prueba de trabajo y qué cadenas de bloques utilizan la Prueba de participación.<br/>

## **Prueba de trabajo** (PoW)

Todo el concepto detrás de **Prueba de trabajo** es mantener una red segura y hacerla confiable, mientras se recompensa a los administradores que contribuyen a esa misión. Algunos de los primeros usuarios dan crédito al inventor de Bitcoin, Satoshi Nakamoto, por delinear por primera vez el algoritmo de Prueba de trabajo en el [documento técnico de Bitcoin](https://bitcoin.org/bitcoin.pdf) (2008). Aunque, en realidad, la idea original de PoW provino de un documento técnico anterior: [Precios a través del procesamiento o la lucha contra el correo basura](http://www.wisdom.weizmann.ac.il/~naor/PAPERS/pvp.pdf) (1993). ).<br/>

## Cómo funciona la prueba de trabajo con Bitcoin

Bitcoin es un sistema de pago descentralizado entre pares que permite a las personas intercambiar valor entre sí, sin necesidad de un tercero. Cada transacción se registra en un libro público para que todos la vean. Ese libro mayor también se conoce como blockchain. Los usuarios actúan como [nodos](https://medium.com/coinmonks/blockchain-what-is-a-node-or-masternode-and-what-does-it-do-4d9a4200938f) y mantienen la red de forma voluntaria. El algoritmo de Prueba de trabajo funciona haciendo que todos los nodos resuelvan acertijos criptográficos. El primer minero en resolver el rompecabezas gana criptomonedas como recompensa.

A medida que se resuelven los acertijos, se vuelven más desafiantes. Solo existirá un número finito de bitcoins (21 millones para ser exactos). Esto asegura que los bitcoins nunca se devalúen debido a la inflación, de la misma manera que se devalúan las monedas fiduciarias. Sin embargo, esto también significa que el costo de la minería aumenta con el tiempo. ¿Por qué? Porque cada vez más nodos compiten para resolver acertijos que no solo son más difíciles, sino también más gratificantes económicamente. Por lo tanto, se están desarrollando grandes consorcios mineros, lo que hace que el poder de confirmar transacciones sea más centralizado. Un resultado que puede no parecer congruente con los valores de Bitcoin.

Hoy en día, los mineros están colectivamente [usando suficiente energía](https://digiconomist.net/bitcoin-energy-consumption) para abastecer a países enteros. En respuesta a esto, una [publicación](https://bitcointalk.org/index.php?topic=27787.0) en el foro de BitcoinTalk introdujo la idea de un algoritmo de mayor eficiencia energética llamado **Prueba de Participación** (2011 ).<br/>

## Prueba de participación (PoS)

Un algoritmo de **Prueba de participación** selecciona un nodo en una red para validar el siguiente bloque de transacciones. La selección es ligeramente aleatoria para garantizar que no todos los mineros (llamados validadores en la jerga de PoS) compitan al mismo tiempo y desperdicien energía.

Donde todo lo que necesita un nodo en un sistema PoW es más poder de cómputo, los validadores de PoS deben depositar monedas o depositarlas en la red. Cuantas más monedas pueda apostar un nodo determinado en la red, más probable es que ese nodo sea seleccionado como validador. Es por eso que la selección de un validador es ligeramente aleatoria. Garantiza que los nodos que apuestan la mayor cantidad de monedas no obtengan demasiadas recompensas demasiado rápido y centralicen el control de la red.<br/>

## Prueba de trabajo frente a prueba de participación

El algoritmo de consenso **Prueba de trabajo** ofrece dos ventajas principales. Una es que es el algoritmo que impulsa a Bitcoin, la criptomoneda más valiosa y conocida del mundo. En segundo lugar, la gente confía en Bitcoin y su libro mayor. Los entusiastas creen que la cadena de bloques de bitcoin siempre será la mejor manera de asegurar una plataforma pública sin permiso y mantener a todos los participantes honestos a pesar de sus fallas.

*Como mencionamos anteriormente*, PoW no es perfecto. Los requisitos de energía de la minería seguirán aumentando y ejercerán presión sobre la red eléctrica mundial. Los pools de minería seguirán aumentando de tamaño y dominarán el proceso de validación.

Tener un gran grupo de mineros dominando más del 50 % de la red y determinando qué transacciones se validan y cuáles no se conoce como un [ataque del 51 %](https://www.investopedia.com/terms/1/51-attack.asp). El uso de un modelo de **Prueba de Participación** hace que un ataque del 51 % sea menos probable. También es más rápido, más eficiente energéticamente y cuesta menos ejecutar una cadena de bloques basada en PoS.
The downside of PoS is that the rich will still get richer and potentially control the consensus of the blockchain — without the need to invest in mining equipment or expertise. To try to combat this problem, several blockchain projects have adopted what is known as the **Delegated Proof of Stake** (DPoS) system. In this system, rather than participants using their wealth to vote on consensus, they use their wealth to vote on delegates. Those delegates then reach a conclusion on consensus. This little twist essentially makes it arguably more difficult to game the system.<br/> 

## Criptomonedas usando prueba de trabajo

Bitcoin y todas sus bifurcaciones (p. ej., Bitcoin Cash, Bitcoin Gold) utilizan el mecanismo de consenso **Prueba de trabajo**, al igual que la mayoría de las demás criptomonedas. Llámalo un efecto secundario de la escuela de pensamiento *'si no está roto, no lo arregles'*.

Otros proyectos que utilizan PoW incluyen monedas de privacidad como [Monero](https://www.getmonero.org/) o [Verge](https://vergecurrency.com/), monedas de intercambio criptográfico descentralizadas como [Digibyte](https:/ /www.digibyte.co/) y cadenas de bloques dedicadas a la creación de aplicaciones descentralizadas como [Ethereum](https://www.ethereum.org/) *(que pronto pasará a un modelo PoS).*<br/>

## Criptomonedas usando prueba de participación

Como se mencionó, Ethereum actualmente opera usando PoW pero se está moviendo hacia un protocolo de **Prueba de Participación** llamado [Casper](https://blockgeeks.com/guides/ethereum-casper/). Casper permite que la participación de un validador se reduzca si actúa de manera maliciosa. Esto también permite que la cadena de bloques y sus participantes resuelvan el problema de los actores maliciosos incluso cuando faltan ciertos elementos cruciales de información. *Un dilema denominado *[*falla bizantina*](https://en.wikipedia.org/wiki/Byzantine_fault)*.*

**Muchos proyectos en el espacio criptográfico están usando un modelo PoS ahora:**

* [NavCoin](https://navcoin.org/en): una criptomoneda basada en la privacidad.
* [NEO](https://neo.org/): una plataforma de contratos inteligentes de código abierto, denominada Ethereum de China.
* [ARK](https://ark.io/): un proyecto destinado a facilitar la creación de cadenas de bloques.
* [Komodo](https://komodoplatform.com/): un proyecto que facilita la implementación de soluciones empresariales de blockchain.<br/>

## El objetivo final de todos los algoritmos de consenso

Ya sea Prueba de trabajo, Prueba de participación, Prueba de participación delegada o cualquier otro tipo de algoritmo de consenso que prevalezca, el objetivo más amplio será el mismo: hacer que las cadenas de bloques sean más rápidas, eficientes, escalables e inmutables.

Las criptomonedas y las cadenas de bloques que impulsarán a la humanidad hacia el futuro pueden incluir reglas e ideas que aún no se han inventado. Pero esa es una razón para estar emocionado, no preocupado. Mirando hacia el futuro y explorando lo que aún no sabemos es donde radica la innovación.

> *En* [*ShapeShift*](http://beta.shapeshift.com/?utm_source=content&utm_medium=medium&utm_campaign=no_account&utm_term=cta01)*, proporcionamos herramientas de siguiente nivel para la gestión de criptografía y queremos hacerlo fácil para usted probar la plataforma. 

---

> Este documento fue publicado originalmente el 10 de septiembre de 2019 por el equipo de ShapeShift y es posible que el flujo de trabajo de Información y globalización lo haya modificado ligeramente para traducirlo para un proyecto de archivo en curso.
>
> El artículo original se puede encontrar [aquí](https://shapeshift.com/library/exploring-consensus-algorithms).
{.is-success}

---

- bounty: true
- amt: 52
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}