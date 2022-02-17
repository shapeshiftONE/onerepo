---
title: Clés privées - Création d'adresses Ethereum
description: Apprenez à obtenir un porte-monnaie Ethereum à partir d'une adresse crypto.
published: true
date: 2021-12-20T23:02:55.629Z
tags: library, cryptocurrency, defi, dex, ethereum, needs-review, crypto-monnaie
editor: markdown
dateCreated: 2021-12-20T23:02:55.629Z
---

# Clés privées - Création d'adresses Ethereum

## ***Deuxième partie d'une série de trois***

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d4a7d055404d1ebb9cf4_PK2%20header%20image.png)

*Avertissement : Veuillez noter que toutes les clés privées générées et utilisées dans ce blog sont uniquement destinées à des fins éducatives. N'utilisez pas le code, les clés ou les adresses partagées dans cet article pour détenir des actifs crypto de quelque nature ou quantité que ce soit.*

## Les clés privées sont des blocs de construction.

Comme nous l'avons vu dans la [première partie](https://shapeshift.com/library/unlocking-the-mysteries-of-private-keys) de notre mini-série "Percer les mystères des clés privées", la procédure de génération des clés privées repose sur des générateurs de nombres pseudo-aléatoires (PRNG) dotés d'une entropie suffisante. La chose la plus importante à retenir au sujet d'une clé privée est qu'elle doit être choisie **aléatoirement** dans l'espace des nombres entiers 2^256-1. N'importe quel nombre peut être une clé privée tant qu'il est compris entre 1 et 2^256 - 1.

Maintenant que nous comprenons un peu les mathématiques derrière les clés privées, nous pouvons aller de l'avant et générer notre propre clé privée valide. Une bonne façon de visualiser ce processus de génération est de penser à une serrure à combinaison horizontale de 78 chiffres (le nombre total de chiffres dans 2^256-1) et de la diviser en trois rangées de 26 chiffres chacune. Vous pouvez considérer une fonction PRNG comme quelque chose qui "mélangerait" tous les chiffres de ce cadenas de combinaison de façon aléatoire : en les commençant tous à 0, et en générant ensuite un nombre sans motif distinctif. Supposons que nous exécutions une fonction PRNG sur notre serrure et que nous obtenions les chiffres suivants dans chaque rangée : 

(1)04406941321102621719184878,(2)43014596507006094171646853, (3)06780198554267270848908554.

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d54295b0e5f2121d4126_PK2%20Browsers.png)

*Les navigateurs utilisent l'*[*API Web Crypto*](https://developer.mozilla.org/fr/docs/Web/API/Web_Crypto_API)*, une API moderne qui nous fournit des primitifs cryptographiques tels que Crypto.getRandomValues(32) (ou l'équivalent de la création d'un tampon de 32 octets) comme un PRNG, qui est ensemencé avec la source d'entropie de votre ordinateur pour générer des nombres aléatoires. Vous devriez toujours utiliser une source numérique pour la génération de nombres aléatoires, car les humains sont très mauvais pour choisir des nombres aléatoires, comme l'indiquent quelques* [*études*](https://www.thebalanceeveryday.com/random-number-generators-more-complicated-than-you-think-4177342). *Vous venez de générer la clé privée 44069413211026217191848784301459650700609417164685306780198554267270848908554. Nous pouvons maintenant l'utiliser pour générer une adresse Bitcoin ou Ethereum ou une adresse pour presque toutes les blockchains qui prennent en charge les clés privées dans la plage 2^256-1.

Pour générer une adresse Ethereum à partir de cette clé privée, nous devons effectuer une [multiplication de points par une courbe elliptique](https://en.wikipedia.org/wiki/Elliptic_curve_point_multiplication). Cela peut être compliqué, donc pour simplifier, nous allons utiliser un ordinateur pour le faire à notre place. Tout d'abord, nous devons comprendre que les ordinateurs ne traitent pas les informations au format décimal. Les ordinateurs ne comprennent que le **code binaire**, et jusqu'à présent, nous ne disposons de notre clé privée que sous forme numérique décimale. Ainsi, pour utiliser notre clé privée, nous devons d'abord la convertir en bits et en octets.<br/>

## Un petit mot sur les bits et les octets (bytes)

Que sont exactement les "bits et les octets" ? Les appareils numériques ne peuvent comprendre que les informations utilisant les chiffres 0 et 1, communément appelés **bits** (ou "chiffre binaire"). Bien que nos smartphones et nos ordinateurs puissent afficher des caractères, des images, des chansons, etc., les ordinateurs représentent et traitent finalement tout sous forme de bits. Les groupes de bits représentent des choses plus importantes, mais dans le cadre de référence d'un ordinateur, ils ne sont toujours qu'un ensemble de 0 et de 1. La représentation la plus courante des bits est celle des **octets** (ou "bytes" en anglais), qui sont composés de 8 bits. Une autre représentation populaire mais moins utilisée est celle des **nibbles**, qui sont composés de 4 bits.

Selon le contexte, plusieurs bits peuvent représenter des caractères (par exemple, la lettre "a" peut être définie comme "01100001" en utilisant le codage [ASCII](https://fr.wikipedia.org/wiki/American_Standard_Code_for_Information_Interchange) en utilisant 1 octet) ou des nombres (par exemple, 01100001 représente le nombre 97 au format décimal). Au **format binaire**, les bits et les octets peuvent représenter des **entiers** en additionnant les puissances de tous les bits utilisés, où la **base** est 2, et chaque chiffre séquentiel augmente le **exposant** utilisé. Par exemple, nous comptons habituellement au **format décimal**, où les nombres sont exprimés comme les sommes des puissances de tous les chiffres utilisés, en utilisant le nombre 10 comme base. Cependant, en utilisant une forme binaire, nous pouvons exprimer les nombres comme 2 à la **nième puissance**, où "n" est le nombre de bits nécessaires pour représenter et stocker cette information dans un ordinateur.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d5b5f4af7c4f57dc9798_PK2%208bit%20video.png)

*Les jeux vidéo 8 bits ne pouvaient exprimer que des valeurs allant jusqu'à 255, car les unités de traitement informatique (CPU) utilisées dans ces jeux ne pouvaient effectuer que des opérations allant jusqu'à 8 bits.*<br/>

Bien que nous puissions représenter n'importe quel nombre au format binaire, ce format est assez "encombrant". Pour exprimer simplement 97, il nous faut huit chiffres binaires. Les nombres binaires sont faciles à traiter pour les ordinateurs, mais incroyablement encombrants à lire pour les humains. C'est pourquoi, au lieu de représenter les données au format binaire, les ordinateurs utilisent généralement le **format hexadécimal**, un système numérique positionnel représentant les nombres en utilisant une base 16. Contrairement au format binaire, nous pouvons représenter 4 bits par une seule lettre au format hexadécimal. Nous pouvons représenter 01100001 - le nombre 97 - en utilisant 61, ce qui réduit de six chiffres notre exemple précédent. Les nombres hexadécimaux utilisent ABCDEF pour représenter 10 à 15 et sont couramment utilisés pour exprimer des données en petits morceaux.

## Compter les bits d'une clé

Pour en revenir à notre clé privée, nous savons qu'il s'agit d'un nombre compris entre 1 et 2^256-1. Comment pouvons-nous le représenter en bits, et de combien de bits avons-nous besoin ? Nous avons vu qu'au format binaire, les nombres représentent des entiers en additionnant les puissances de tous les bits utilisés, la base étant 2. Ainsi, en utilisant 8 bits, nous pouvons représenter 2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0, soit 255. Nous pouvons alors voir que dans 2^n, n est égal à la quantité totale de bits nécessaires pour représenter n'importe quel nombre en bits. Si nous corrélons ce raisonnement, nous pouvons dire que 256 bits, ou mieux encore, 32 octets (256/8), sont nécessaires pour représenter notre clé privée.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d614c80f3db79eb93f23_PK2%20Hexadecimal.png)

*La représentation hexadécimale des données a pour but de réduire le nombre de chiffres nécessaires pour représenter les nombres. Si nous pouvons convenir que nous avons besoin de 32 octets pour représenter notre clé privée [1, 2^256-1], alors en utilisant le format hexadécimal, nous pouvons convenir que nous avons besoin de 64 caractères pour représenter notre clé privée. Nous pouvons maintenant convertir notre clé privée originale 44069413211026217191848784301459650700609417164685306780198554267270848908554 en son format hexadécimal équivalent : 616E6769652E6A6A706572657A616775696E6167612E6574682E6C696E6B0D0A. Voyez l'ajout des lettres A, B, C, D, E et F dans notre nouveau nombre ; la présence de ces lettres est un moyen facile d'identifier qu'un nombre est représenté au format hexadécimal.

### De la clé privée à la clé publique

Nous pouvons maintenant indiquer à notre ordinateur notre clé privée en utilisant son format hexadécimal. En utilisant des langages de programmation comme JavaScript, nous pouvons facilement importer notre clé privée dans un format que nous pouvons utiliser pour une multiplication ultérieure. Dans le code suivant, nous avons défini notre clé privée ("sk" pour secret\_key, une notation standard utilisée en cryptographie) pour importer la valeur hexadécimale précédemment définie. Nous fournissons le format hexadécimal en nous assurant que le radix (base) est 16.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d67e84b5e361c566b221_PK2%20BigNumber.png)

*En utilisant la bibliothèque BigNumber, nous pouvons nous assurer qu'aucune décimale ne se perd dans la conversion. Ces nombres sont généralement exprimés sous forme d'exponentielles (par exemple, 4,406941321102622e+76) et, lorsqu'ils sont analysés directement en hexadécimal, ils perdent en précision. Sans BigNumber, notre conversion hexadécimale renverrait 616e6769652e6c0000000000000000000000000000000000 au lieu de notre nombre hexadécimal réel.*

<br/>

Une fois notre clé importée, l'étape suivante consiste à créer la clé publique. Comme vous vous en souvenez peut-être dans notre premier blog, nous devons dériver la clé publique de notre clé privée avant de pouvoir obtenir l'adresse Ethereum. En suivant les instructions du [document jaune original d'Ethereum](https://ethereum.github.io/yellowpaper/paper.pdf), nous avons constaté que le processus de génération de la clé suit un standard [génération de la clé publique ECDSA](https://fr.wikipedia.org/wiki/Elliptic_curve_digital_signature_algorithm), où nous multiplions le point générateur et concaténons les coordonnées en une seule valeur. Notre clé publique (maintenant définie comme pk) peut maintenant être utilisée pour générer notre adresse Ethereum.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d6c77da9ec1ea15aca07_PK2%20ValuesXY.png)

*Les valeurs x et y sont obtenues à partir de la multiplication des points de la courbe elliptique par notre clé privée (sk). Bien qu'une clé privée puisse être utilisée dans n'importe quelle blockchain comme identifiant unique d'une adresse, Ethereum est spécifique à l'utilisation de la courbe elliptique secp256k1 pour la génération de clés publiques, et donc, leurs opérations de signature équivalentes.* Hélas, la dernière étape est arrivée. Avec notre clé publique définie, nous pouvons alors exécuter la dernière instruction du papier jaune, définie comme suit :

<br/>

> *Pour une clé privée donnée, l'adresse Ethereum A est définie comme les 160 bits les plus à droite du hachage de Keccak de la clé publique ECDSA correspondante.*

<br/>

Comme nous disposons déjà de notre clé publique ECDSA, il ne nous reste plus qu'à exécuter la fonction de hachage [Keccak](https://fr.wikipedia.org/wiki/SHA-3) sur notre clé publique et à obtenir les 160 bits les plus à droite de cette opération. Comme nous stockons ces opérations dans des "tampons" (pensez à de petites boîtes où nous stockons des octets d'information), nous pouvons simplement "laisser tomber" (couper) les 24 premiers caractères, ne laissant que 40 caractères, ou plus concrètement, 20 octets - la taille d'une adresse Ethereum.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/6050d7373d4368addc733bc1_PK2%20Ethereum%20addresses.png)

*Les adresses Ethereum ont une longueur de 20 octets par conception. En supprimant certains de ses octets (12 pour être précis), on pourrait faire valoir qu'il pourrait y avoir une collision où deux clés privées finissent par générer la même adresse Ethereum. Cependant, à ce jour, cela ne s'est pas encore produit.*<br/><br/>

## Vous avez créé votre propre porte-monnaie.

Comme vous pouvez le voir, à partir d'un seul numéro (bien qu'il soit long), vous pouvez obtenir une adresse Ethereum où vous pouvez détenir toutes sortes d'actifs : des NFT représentant de la musique, des billets, etc., aux crypto-actifs qui peuvent accumuler une valeur monétaire. Votre adresse Ethereum est publique, comme votre adresse physique, et elle vous relie à cette clé privée unique.<br/>

Si vous ne souhaitez pas suivre les étapes décrites ici, vous pouvez ouvrir un compte sur [www.ShapeShift.com](http://www.shapeshift.com) pour créer votre propre clé privée, connue par vous uniquement, et tirer parti d'un certain nombre d'options de porte-monnaie logiciel et matériel.<br/>

Dans la prochaine et dernière partie de notre mini-série, nous verrons comment nous pouvons maintenant utiliser nos clés privées pour créer et diffuser des transactions à partir de notre adresse Ethereum et signer des messages, et nous apprendrons les implications que ces signatures peuvent avoir dans l'écosystème Ethereum.

---

> Ce document a été publié à l'origine le 2021-03-16 par Jose Aguinaga et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/private-keys-creating-ethereum-addresses).
{.is-success}

---

- bounty: true
- amt: 80
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}