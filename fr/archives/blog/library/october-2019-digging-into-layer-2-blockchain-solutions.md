---
title: Creuser les solutions blockchain de couche 2
description: Découvrez les technologies qui s'efforcent de résoudre les problèmes d'échelle de la crypto.
published: true
date: 2021-12-20T23:02:33.907Z
tags: library, bitcoin, cryptocurrency, ethereum, needs-review, crypto-monnaie
editor: markdown
dateCreated: 2021-12-20T23:02:33.907Z
---

# Creuser les solutions blockchain de couche 2

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f294424536954b69806bd_1_L8GpHTyR1-JRyyo31JzZeQ.png)

**Les geeks** de la blockchain et les amateurs de crypto utilisent souvent les termes couche 2 et Lightning Network de manière interchangeable lorsqu'ils font référence aux solutions d'évolutivité de blockchain. La vérité est que ces termes ne sont ***pas*** interchangeables.<br/> 

## Au-delà du Bitcoin : montée en charge avec la couche 2

Le terme **couche 2** fait référence à une deuxième couche de codage qui existe au-dessus de la structure de codage originale d'une blockchain. Cela permet à une blockchain décentralisée d'évoluer et de faire face à une poignée de problèmes tels que :

* L'augmentation du volume et de la vitesse des paiements
* L'augmentation de la création et de l'exécution de contrats intelligents
* L'exécution de calculs hors chaîne

La mise à niveau du Lightning Network de Bitcoin est spécifique à la montée en charge des paiements, mais ce n'est qu'un des projets dédiés à la résolution de ce problème. Pour mieux comprendre les solutions de couche 2, il faut aller au-delà de Bitcoin et examiner les différentes blockchains qui utilisent cette technologie.<br/> 

## **Pourquoi la montée en charge est-elle un problème?**

La montée en charge fait simplement référence à la capacité d'un réseau à gérer un nombre élevé de transactions par seconde. L'augmentation du nombre de transactions qu'une blockchain peut traiter est fondamentalement considérée comme l'un des plus grands obstacles auxquels sont confrontées les crypto-monnaies et les plateformes de paiement décentralisées. La mise à l'échelle est considérée comme le plus grand obstacle entre la crypto et l'adoption de masse.

Les cartes de crédit comme Visa et Mastercard peuvent gérer jusqu'à 47 000 transactions par seconde à tout moment. En fait, on estime qu'au cours de la fameuse [Journée des célibataires en Chine](https://techcrunch.com/2018/11/09/alibaba-singles-day-11-festival/), ces sociétés de cartes de crédit peuvent traiter près de 100 000 transactions par seconde.

En comparaison, Bitcoin effectue environ [4,6 transactions](https://hackernoon.com/the-blockchain-scalability-problem-the-race-for-visa-like-transaction-speed-5cce48f9d44) par seconde. La raison de cet écart important est que Visa et MasterCard font partie du système bancaire centralisé, qui existe depuis plus de 100 ans. Les technologies décentralisées doivent toujours faire face à ce que l'on appelle le "triangle impossible".

**Le triangle impossible** fait référence aux trois principes qui donnent à une blockchain son utilité :

1. Sécurité
2. Montée en charge
3. Décentralisation

À l'heure actuelle, il n'y a pas une seule crypto-monnaie sur une blockchain entièrement publique qui maîtrise les trois éléments ci-dessus. Ripple gère actuellement [1 500 transactions par seconde](https://www.ripple.com/xrp/). La blockchain EOS a un débit de près de [4 000 transactions par seconde](https://thenextweb.com/hardfork/2018/11/01/eos-blockchain-benchmark/). On peut dire sans se tromper qu'à ce jour, le triangle s'avère toujours impossible à maîtriser. C'est pourquoi les approches de couche 2 sont de plus en plus connues comme solution de montée en charge.<br/>

## **Le Lightning Network**

Le [Lightning Network](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f) permet d'effectuer de petites transactions par le biais de canaux de paiement. L'ouverture d'un canal de paiement est idéale pour les petites transactions récurrentes, comme l'achat d'un café tous les jours. Un grand amateur de café peut acheter trois tasses par jour, ce qui représente 21 transactions par semaine. Le Lightning Network permet aux utilisateurs de créer un canal de paiement qui confirme ces 21 transactions, le solde initial et le solde final de toutes ces transactions sur la blockchain.

Le Lightning Network est nécessaire car la [transaction moyenne en bitcoins](https://hackernoon.com/2019-blockchain-layer-2-solution-review-d00385147396#1cee) vaut environ 50 dollars, avec des frais d'environ 20 dollars. Il n'est donc pas pratique de conserver les petites transactions "sur la chaîne". Les transactions hors chaîne réduisent la charge de la blockchain. Le Lightning Network permet également d'utiliser une adresse à signatures multiples, ce qui signifie que deux parties ne peuvent pas se manipuler mutuellement pour effectuer une transaction. L'inconvénient est que le Lightning Network ne peut pas être utilisé hors ligne. Il ne peut pas non plus être utilisé pour les gros montants, et il permet aux nœuds de devenir potentiellement de grands centres de paiement qui détiennent de grosses sommes d'argent.

[*>>> En savoir plus sur le Lightning Network de Bitcoin <<<*](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f)

## Canaux de paiements

Du point de vue du codage, un canal de paiements n'est en réalité qu'une itération d'une solution de couche 2 de canal d'état (state channel). Une implémentation de canal d'état :

* Permet de verrouiller une partie de l'état de la blockchain à l'aide d'adresses multi-signatures ou de contrats intelligents.
* Permet aux participants de mettre à jour l'état de cette partie de la chaîne.
* Soumet l'état mis à jour à la blockchain.

Cette approche du canal d'état est plus facilement comprise dans un échange monétaire ; l'échange pourrait être n'importe quoi. Elle pourrait être utilisée pour suivre tout autre type de changement de l'état d'une blockchain, que la transaction soit liée à l'argent, à la propriété intellectuelle, à l'identification gouvernementale, etc.<br/> 

## **Solutions de montée en charge d'Ethereum**

Ethereum a pour objectif d'être le superordinateur décentralisé du monde. Son existence donne aux développeurs une plateforme pour construire et lancer des applications décentralisées que tout le monde peut utiliser. C'est ce qui le différencie du Bitcoin. Ce qui rend les deux crypto-monnaies similaires, c'est qu'elles utilisent toutes deux l'algorithme de consensus [proof-of-work](https://medium.com/shapeshift-stories/exploring-consensus-algorithms-8403c301b2ff).

## Casper

Casper est la mise à jour qui permettra à Ethereum d'adopter l'approche "proof-of-stake", sans doute plus efficace. Les algorithmes de preuve d'enjeu rendent la validation des transactions plus efficace, tant sur le plan technique qu'en termes de coûts énergétiques.

## Plasma

Là où un algorithme de consensus proof-of-stake valide les transactions, la mise à niveau Plasma applique la deuxième couche de contrats intelligents à la blockchain. Elle permettra de remplacer les fermes de serveurs par un réseau pair-à-pair qui rendra l'exécution d'applications décentralisées plus optimisés pour la montée en charge. Comme l'explique le [livre blanc Plasma](https://plasma.io/plasma-deprecated.pdf), les transactions peuvent avoir lieu en privé entre les utilisateurs sur des chaînes privées, puis être représentées sur la chaîne publique.

## Sharding

Le sharding complétera Casper et Plasma en rendant la blockchain d'Ethereum plus optimisés pour la montée en charge. Il permet de [diviser les données](https://www.trustnodes.com/2018/05/01/sharding-proof-concept-launches-casper-32-staking-eth-requirements-coming-says-vitalik-buterin) et de les héberger sur plusieurs serveurs. Cela signifie que le Grand Livre public devient fragmenté, mais que toutes les transactions seront toujours comptabilisées.

## Transactions sur les chaînes latérales (sidechains) et hors chaîne (off-chain)

Vous connaissez maintenant deux des approches les plus populaires de la montée en charge des paiements et des contrats intelligents. Il existe deux autres solutions de couche 2 dignes d'intérêt à explorer.

## Chaîne latérale (Sidechain)

Une sidechain est une blockchain séparée qui est attachée à une chaîne mère à l'aide d'un peg (lien) bidirectionnel, ce qui permet d'échanger des actifs les uns contre les autres à un taux fixe. Les chaînes latérales peuvent être utilisées pour toutes sortes d'actifs numériques et ont besoin de leurs propres mineurs pour rester sécurisées. Les projets utilisant efficacement les chaînes latérales comprennent [OmiseGO](https://omisego.co/), [POA Network](https://poa.network/) et [Alacris](https://alacris.io/).

## **Hors chaîne** (Off-chain)

Les transactions hors chaîne se font complètement en dehors d'une blockchain. Cela peut se faire par le biais d'un accord de transfert entre les deux parties, par le biais d'un tiers garant (similaire à ce que Paypal fait dans le monde de la monnaie fiduciaire), ou en utilisant un mécanisme de coupon. Les transactions hors chaîne peuvent être effectuées instantanément, sans frais et dans un plus grand anonymat. Les projets mettant en œuvre une approche hors chaîne comprennent [Provable](https://provable.xyz/), [AlphaWallet](https://alphawallet.com/) et [Transmute](https://www.transmute.industries/).

## Preuves à divulgation nulle de connaissance (Zero-Knowledge Proofs)

Saviez-vous que les fondements cryptographiques qui permettent la confidentialité sur Zcash peuvent également être exploités pour augmenter la montée en charge ? Cette approche prometteuse de la couche 2 est actuellement en cours d'élaboration sur Ethereum, à l'aide de STARKS et SNARKS (les deux principaux types de preuves à divulgation nulle de connaissance).

Du côté de STARKS, l'entreprise israélienne [STARKWARE](https://starkware.co/) élabore une solution innovante capable de traiter des milliers de transactions hors chaîne sans avoir besoin d'une installation de confiance. Gardez également un œil sur [Matter Labs](https://matter-labs.io/) et ses "roll-ups" basés sur SNARK.

Même si ces solutions sont loin d'être parfaites, le potentiel pour faire passer la technologie blockchain au niveau supérieur est là. Avec des avancées en matière de montée en charge comme les solutions de couche 2, la mission consistant à faire adopter les cryptos par le grand public semble se profiler à l'horizon.<br/> 

---

> Ce document a été publié à l'origine le 2019-10-17 par ShapeShift Team et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/digging-into-layer-2-blockchain-solutions).
{.is-success}

---

- bounty: true
- amt: 54
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}