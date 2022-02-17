---
title: Percer les mystères des clés privées
description: Les clés privées sont d'une importance capitale dans le secteur de la crypto. Lisez la suite pour savoir plus. 
published: true
date: 2021-12-20T23:03:19.590Z
tags: library, cryptocurrency, defi, needs-review, crypto-monnaie
editor: markdown
dateCreated: 2021-12-20T23:03:19.590Z
---

# Percer les mystères des clés privées

## ***Première partie d'une série de trois***

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/60410f04b90eef50bdcef5fb_Paper.Port_is_-_Private_Keys.4.png)

## Les clés privées : Un aperçu général

À bien des égards, posséder une crypto-monnaie se résume à détenir une clé privée. Contrairement au monde "réel", où la possession d'un bien physique implique généralement la possession d'un acte de propriété portant votre nom ou d'un reçu de vente, **posséder est équivalent à savoir dans le monde de la crypto**. En termes plus simples, connaître une clé privée équivaut à posséder des actifs crypto, puisque ce sont les clés privées qui vous permettent d'autoriser des transactions avec ces actifs.


![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604110379bf86942b436399f_Owning.png)

*L'affirmation "la connaissance est le pouvoir" n'a jamais été aussi vraie qu'elle l'est dans le domaine de la crypto.*<br/><br/>

Dans le monde réel, les transactions sont généralement autorisées par votre signature. Cependant, dans le monde cryptographique, seules les **clés privées** peuvent les autoriser, de manière cryptographique, en donnant accès aux fonds. Bien que n'importe qui puisse générer une transaction impliquant vos actifs cryptographiques, seule la personne en possession de la clé privée peut signer, et donc valider, la transaction.<br/>

> *Bien que les fausses signatures soient un problème dans le monde réel, le monde de la crypto est protégé par sa nature cryptographique sous-jacente. À ce jour, aucun piratage connu ne permet à quelqu'un de signer des transactions sur vos actifs sans votre clé.*

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604110c6415c80a0e6b91c39_Access.png)

*L'expression puissante "pas vos clés, pas votre monnaie" vient du fait qu'en ayant une clé privée, n'importe qui peut signer n'importe quelle transaction sur ces actifs et donc les transférer ou les déplacer à sa guise (ce qui rend importante la possession exclusive de ces actifs).*<br/>

## Que sont les clés privées, et comment sont-elles générées ?

Les clés privées sont des nombres compris dans un intervalle spécifique, généralement très large. D'un point de vue mathématique, une clé privée est simplement un **entier positif aléatoire**. Une description plus technique et plus précise serait toutefois la suivante : *Une clé privée est un nombre aléatoire cryptographiquement fort qui a été obtenu à l'aide d'un générateur de nombres aléatoires dans une plage positive définie*. 

La plupart du temps, les ordinateurs utilisent des **générateurs de nombres pseudo-aléatoires (PRNG)** pour générer ces nombres entiers positifs aléatoires. (Les vrais générateurs de nombres aléatoires sont difficiles à trouver ; ces générateurs nécessitent souvent du matériel spécialisé et utilisent des sources physiques telles que le bruit thermique dans les circuits électriques ou la synchronisation précise des clics d'un compteur Geiger). Les PRNG sont des fonctions cryptographiques fortes, ensemencées avec une valeur qui a suffisamment d'**entropie**. L'entropie est un concept complexe, mais son objectif est simple : fournir de l'imprévisibilité aux fonctions. En utilisant des sources d'entropie sécurisées, les PRNG peuvent créer des nombres dont il est extrêmement improbable qu'ils ne soient pas aléatoires (dans une fourchette donnée et acceptable).

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604111422a65fc3b152c1bbf_Entropy.png)

*"/dev/urandom" sous Linux ou "rand\_s" sous Microsoft Windows sont des sources d'entropie couramment utilisées par les PRNG pour la génération sûre de nombres aléatoires. Dans ce diagramme, le terme "range" (intervalle) est utilisé de façon libre pour désigner à la fois le concept mathématique de intervalle et la taille des octets donnés à un ordinateur pour générer un nombre aléatoire.*<br/><br/>

L'intervalle donné à un PRNG pour créer en toute sécurité une clé privée Ethereum ou Bitcoin valide est **2^256-1** (imaginez une serrure à combinaison des chiffres 0-9, laquelle compte 78 chiffres). En raison de la taille de cet intervalle, la probabilité de générer deux clés privées avec le même numéro est négligeable. L'ensemble des nombres entiers parmi lesquels votre clé est sélectionnée est un [nombre massif](https://www.wolframalpha.com/input/?i=2%5E256) — il est **quasiment identique au nombre total d'atomes visibles dans l'univers**.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113247ce66b0a06d760cc_Range.png)

*L'intervalle de 2^256-1 a été défini à la fois par Bitcoin et Ethereum, et il fonctionne grâce aux stratégies mathématiques que les deux blockchains utilisent pour créer des clés publiques. Par exemple, Ethereum utilise des courbes elliptiques (en particulier SECP-256k1) pour la génération de ses clés publiques. Dans son document original* [*yellow paper*](http://gavwood.com/paper.pdf)*, le Dr Gavin Wood a défini une clé privée comme un nombre entier positif choisi au hasard (représenté comme un tableau d'octets de longueur 32 sous la forme big-endian) dans l'intervalle [1, secp256k1n-1]. Pour toutes les définitions formelles, veuillez vous référer au document jaune actuel*.

<br/>

## Clés publiques, adresses et leur relation avec les clés privées

Puisque les clés privées sont censées rester... eh bien... privées, nous avons besoin d'un mécanisme différent pour permettre à d'autres personnes de trouver nos actifs et pour que nous trouvions les leurs. Par conséquent, toutes les blockchains utilisent le concept "d'adresses", des numéros uniques dérivés de votre clé privée. Ces adresses sont l'emplacement de vos actifs crypto et peuvent être partagées avec les personnes qui ont besoin de connaître le solde de vos actifs crypto (si vous le souhaitez). 

Une adresse blockchain est créée à l'aide de votre **clé publique** pour s'assurer que vous êtes le propriétaire de l'adresse en question. À son tour, cette clé publique est générée à partir de votre clé privée. Ce processus est **unidirectionnel**, ce qui signifie que vous pouvez utiliser une clé privée pour créer un compte, mais pas un compte pour deviner une clé privée.

> *Les clés privées peuvent dériver des clés publiques, et les clés publiques peuvent dériver des adresses blockchain. Cependant, les adresses de blockchain ne peuvent pas être utilisées pour dériver leurs clés publiques, et les clés publiques ne peuvent pas être utilisées pour dériver leurs clés privées*. 

Ce processus unidirectionnel est réalisé via des **fonctions cryptographiques "trapdoor"**. Une fonction trapdoor est une fonction unidirectionnelle qui ne peut générer sa valeur qu'à partir d'une entrée spécifique et qui ne peut pas être utilisée pour dériver l'entrée originale. C'est comme si vous saviez comment faire un gâteau et que vous aviez une idée approximative de ce qu'il contient, mais qu'il était impossible de connaître les ingrédients exacts d'un gâteau spécifique en le goûtant.

Ces fonctions à sens unique varient selon l'écosystème blockchain. Par exemple, les systèmes de blockchain les plus populaires utilisent des constructions algébriques basées sur des courbes elliptiques pour générer leurs clés publiques. Indépendamment de ces caractéristiques, le résultat est toujours **déterministe** : une clé publique est unique pour sa clé privée correspondante, et la clé privée génère toujours la même clé publique.<br/><br/>

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113a0b5a6cc67e23d3750_Public%20keys.png)

*Bien que les blockchains populaires comme Bitcoin ou Ethereum utilisent un point générateur fixe de la courbe elliptique secp256k1 sur ECDSA pour multiplier la clé privée afin d'obtenir sa clé publique, d'autres projets de blockchain utilisent des stratégies différentes. Par exemple, Monero utilise Curve25519 plutôt que EdDSA, tandis que les chaînes Polkadot et Substrate utilisent Ed25519 plutôt que sr25519. Toutes ces chaînes génèrent une clé publique basée sur une clé privée donnée avec un intervalle de 2^256-1.*

<br/>

Les adresses blockchain utilisent également des fonctions à sens unique, appelées [fonctions de hachage](https://fr.wikipedia.org/wiki/Fonction_de_hachage). Les adresses Bitcoin et Ethereum sont créées à partir d'une ou plusieurs fonctions de hachage **cryptographiquement fortes** appliquées à votre clé publique, en plus de mathématiques spécifiques dépendant de la blockchain spécifique. En raison de la façon dont ces opérations de hachage fonctionnent, vous pouvez être sûr à un degré presque absolu que votre adresse blockchain est unique par rapport à votre clé publique et donc par rapport à votre clé privée.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113ed9bbe7adeb9daed5b_Accounts.png)

*Un compte Ethereum est le hachage Keccak-256 d'une clé publique en plus de prendre les 20 octets les plus à droite d'un tel calcul. Les clés Bitcoin utilisent SHA-256 et RIPEMD-160, tandis que Polkadot et ZCash utilisent Blake2b. Tous ces hachages sont résistants aux collisions, ce qui réduit la possibilité de générer un compte unique à partir de deux clés publiques et garantit que la seule façon de régénérer un compte à partir d'une entrée est de recourir à des techniques par force brute économiquement inefficaces. Il n'y a aucune garantie que ces fonctions de hachage ne soient pas cassées, mais à ce jour aucune fonction de hachage connue utilisée dans une blockchain ne s'est avérée cassée.*<br/> <br/>

## Le langage universel des mathématiques préserve nos secrets

La cryptographie et les mathématiques qui se cachent derrière les clés privées sont la raison pour laquelle nos cryptoactifs sont en sécurité - tant que nous gardons nos clés en sécurité. À ce jour, il est impossible de trouver et de forcer une adresse de blockchain liée à vos clés privées, car cela coûterait [plus d'énergie que celle stockée par le soleil](https://support.mycrypto.com/staying-safe/ethereum-two-people-same-private-key).<br/>

Dans notre prochain billet, nous nous pencherons sur les écosystèmes de blockchain les plus populaires et sur les mathématiques qui sous-tendent la génération de clés publiques. Nous fournirons quelques exemples de code pour que vous puissiez essayer de calculer les clés à partir du processus décrit par chaque blockchain et utiliser les bibliothèques existantes qui facilitent le processus de génération. Restez attentifs !<br/>

---

> Ce document a été publié à l'origine le 2021-03-05 par Jose Aguinaga et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/unlocking-the-mysteries-of-private-keys).
{.is-success}

---

- bounty: true
- amt: 63
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}