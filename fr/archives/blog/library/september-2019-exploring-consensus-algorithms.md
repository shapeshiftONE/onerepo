---
title: Exploration des algorithmes de consensus
description: Proof of Work contre Proof of Stake.
published: true
date: 2021-12-20T23:02:35.048Z
tags: library, bitcoin, cryptocurrency, finance, needs-review, crypto-monnaie
editor: markdown
dateCreated: 2021-12-20T23:02:35.048Z
---

# Exploration des algorithmes de consensus

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f57ee07bdfea1e7ac96ac_1_tQ_nSdkltp2lDkk2IOGfnw.png)

**Les algorithmes de consensus** sont les mécanismes qui permettent aux blockchains de rester sécurisées et de récompenser les utilisateurs qui agissent comme leurs gardiens. Les deux types d'algorithmes de consensus qui dominent le paysage des crypto-monnaies : Proof of Work et Proof of Stake.

Une fois que vous aurez dépassé l'excitation initiale de l'achat de vos premiers bitcoins, vous serez peut-être intéressé par le fonctionnement du Proof of Work et par les blockchains qui utilisent le Proof of Stake.<br/> 

## **Proof of Work** (PoW)

L'ensemble du concept de **Proof of Work** (preuve de travail) consiste à sécuriser un réseau et à le rendre digne de confiance, tout en récompensant les gestionnaires qui contribuent à cette mission. Certains adeptes précoces attribuent à Satoshi Nakamoto, l'inventeur de Bitcoin, la première description de l'algorithme Proof of Work dans le [livre blanc de Bitcoin](https://bitcoin.org/bitcoin.pdf) (2008). Bien qu'en réalité, l'idée originale de la preuve de travail provienne d'un livre blanc antérieur : [Pricing via Processing or Combatting Junk Mail](http://www.wisdom.weizmann.ac.il/~naor/PAPERS/pvp.pdf) (1993).<br/> 

## Comment Proof of Work fonctionne avec Bitcoin ?

Bitcoin est un système de paiement décentralisé de pair à pair qui permet aux individus d'échanger des valeurs entre eux, sans avoir recours à un tiers. Chaque transaction est enregistrée dans un Grand Livre public accessible à tous. Ce Grand Livre est connu sous le nom de blockchain. Les utilisateurs agissent en tant que [nœuds](https://medium.com/coinmonks/blockchain-what-is-a-node-or-masternode-and-what-does-it-do-4d9a4200938f) et entretiennent le réseau de manière volontaire. L'algorithme Proof of Work fonctionne en demandant à tous les nœuds de résoudre des énigmes cryptographiques. Le premier mineur à résoudre l'énigme gagne de la crypto-monnaie comme récompense.

Au fur et à mesure que les énigmes sont résolues, elles deviennent plus difficiles. Il n'y aura jamais plus qu'un nombre fini de bitcoins (21 millions pour être exact). Cela garantit que les bitcoins ne seront jamais dévalués en raison de l'inflation, comme le sont les monnaies fiduciaires. Cependant, cela signifie également que le coût de l'extraction minière augmente avec le temps. Pourquoi ? Parce que de plus en plus de nœuds s'affrontent pour résoudre des énigmes qui sont non seulement plus difficiles, mais aussi plus rémunératrices. Ainsi, de grands pools miniers se développent, rendant le pouvoir de confirmer les transactions plus centralisé. Un résultat qui peut sembler peu compatible avec les valeurs du Bitcoin.

Aujourd'hui, les mineurs utilisent collectivement [suffisamment d'énergie](https://digiconomist.net/bitcoin-energy-consumption) pour alimenter des pays entiers. En réponse à cela, un [post](https://bitcointalk.org/index.php?topic=27787.0) sur le forum BitcoinTalk a introduit l'idée d'un algorithme plus économe en énergie appelé **Proof of Stake** (2011).<br/> 

## Proof of Stake (PoS)

Un algorithme **Proof of Stake** (preuve de l'enjeu) sélectionne un nœud dans un réseau pour valider le prochain bloc de transactions. La sélection est légèrement aléatoire afin de s'assurer que tous les mineurs (appelés validateurs dans le jargon PoS) ne sont pas en compétition au même moment et ne gaspillent pas d'énergie.

Alors que dans un système de PoW, un nœud n'a besoin que de puissance de calcul supplémentaire, les validateurs de PoS doivent déposer des monnaies ou les mettre en jeu sur le réseau. Plus un nœud donné peut déposer de monnaie sur le réseau, plus il a de chances d'être sélectionné comme validateur. C'est pourquoi la sélection d'un validateur est légèrement aléatoire. Cela permet de s'assurer que les nœuds qui mettent le plus de monnaie n'obtiennent pas trop de récompenses trop rapidement et de centraliser le contrôle du réseau.<br/> 

## Proof of Work contre Proof of Stake

L'algorithme de consensus **Proof of Work** offre deux avantages principaux. Le premier est qu'il s'agit de l'algorithme qui pilote Bitcoin, la crypto-monnaie la plus précieuse et la plus connue au monde. Deuxièmement, les gens font confiance à Bitcoin et à son Grand Livre. Les enthousiastes pensent que la blockchain Bitcoin sera toujours le meilleur moyen de sécuriser une plateforme publique sans autorisation et de maintenir l'honnêteté de tous les participants, malgré ses défauts.

*Comme nous l'avons déjà mentionné*, le PoW n'est pas parfait. Les besoins en énergie pour le minage continueront d'augmenter et de peser sur le réseau électrique mondial. Les pools de mineurs vont continuer à augmenter en taille et à dominer le processus de validation.

Le fait qu'un seul grand groupe de mineurs puisse dominer plus de 50 % du réseau et détermine quelles transactions sont validées et lesquelles ne le sont pas est connu comme une [attaque à 51 %](https://www.investopedia.com/terms/1/51-attack.asp). L'utilisation d'un modèle **Proof of Stake** rend une attaque à 51 % moins probable. Le fonctionnement d'une blockchain basée sur PoS est également plus rapide, plus économe en énergie et moins coûteux.

L'inconvénient du PoS est que les riches continueront à s'enrichir et à contrôler potentiellement le consensus de la blockchain, sans avoir besoin d'investir dans des équipements ou des compétences de minage. Pour tenter de combattre ce problème, plusieurs projets blockchain ont adopté ce que l'on appelle le système de **preuve d'enjeu déléguée** (Delegated Proof of Stake, DPoS). Dans ce système, plutôt que les participants utilisent leur richesse pour voter sur le consensus, ils utilisent leur richesse pour voter sur les délégués. Ces délégués parviennent ensuite à une conclusion sur le consensus. Cette petite astuce rend le système beaucoup plus difficile à manipuler.<br/> 

## Les crypto-monnaies utilisant la preuve de travail (Proof of Work)

Bitcoin et tous ses forks (par exemple, Bitcoin Cash, Bitcoin Gold) utilisent le mécanisme de consensus **Proof of Work**, comme la plupart des autres crypto-monnaies. Il s'agit d'un effet secondaire de l'école de pensée *"si ce n'est pas cassé, ne le réparez pas"*.

Parmi les autres projets utilisant le PoW, on trouve des monnaies de confidentialité comme [Monero](https://www.getmonero.org/) ou [Verge](https://vergecurrency.com/), des monnaies d'échange de crypto décentralisées comme [Digibyte](https://www.digibyte.co/) et des blockchains dédiées à la création d'applications décentralisées comme [Ethereum](https://www.ethereum.org/) *(qui va bientôt passer à un modèle PoS).*<br/>

## Cryptocurrencies utilisant la preuve d'enjeu (Proof of Stake)

Comme nous l'avons mentionné, Ethereum fonctionne actuellement en utilisant PoW, mais il évolue vers un protocole **Proof of Stake** appelé [Casper](https://blockgeeks.com/guides/ethereum-casper/). Casper permet de faire perdre en partie la mise d'un validateur s'il agit de manière malveillante. Cela permet également à la blockchain et à ses participants de résoudre le problème des acteurs malveillants même lorsque certains éléments d'information cruciaux sont manquants. *Un dilemme désigné sous le nom de *[*problème des généraux byzantins*](https://fr.wikipedia.org/wiki/Probl%C3%A8me_des_g%C3%A9n%C3%A9raux_byzantins)*.*

**De nombreux projets dans l'espace crypto utilisent maintenant un modèle PoS :**

* [NavCoin](https://navcoin.org/en) : Une crypto-monnaie basée sur la confidentialité.
* [NEO](https://neo.org/) : Une plateforme open-source de contrats intelligents, surnommée l'Ethereum de la Chine.
* [ARK](https://ark.io/) : Un projet visant à faciliter la création de blockchains.
* [Komodo](https://komodoplatform.com/) : Un projet visant à faciliter la mise en œuvre de solutions blockchain d'entreprise.<br/> 

## L'objectif final de tous les algorithmes de consensus

Que ce soit la preuve de travail, la preuve d'enjeu, la preuve d'enjeu déléguée ou tout autre type d'algorithme de consensus qui prévale, l'objectif général sera le même : rendre les blockchains plus rapides, plus efficaces, plus capable de monter en charge et plus immuables.

Les crypto-monnaies et les blockchains qui propulseront l'humanité dans le futur pourraient inclure des règles et des idées qui n'ont même pas encore été inventées. Mais c'est une raison d'être enthousiaste et non inquiet. Garder un œil sur l'avenir et explorer ce que nous ne savons pas encore, c'est là que réside l'innovation.

---

> Ce document a été publié à l'origine le 2019-09-10 par ShapeShift Team et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/exploring-consensus-algorithms).
{.is-success}

---

- bounty: true
- amt: 52
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}