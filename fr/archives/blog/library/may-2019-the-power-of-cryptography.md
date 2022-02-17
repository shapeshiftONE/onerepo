---
title: Le pouvoir de la cryptographie
description: Un guide pour les débutants sur les clés publiques et privées.
published: true
date: 2021-12-20T23:03:17.065Z
tags: library, security, bitcoin, needs-review, sécurité
editor: markdown
dateCreated: 2021-12-20T23:03:17.065Z
---

# Le pouvoir de la cryptographie

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fe664f01b87e59121323b_1_3VBrEt6tEGGLUrte9icrbQ.jpeg)

<br/>

Que vous soyez un nouveau venu dans le domaine de la crypto ou un vétéran de longue date, il existe certaines notions que toute personne impliquée dans cet espace doit comprendre. Aujourd'hui, nous allons aborder l'une d'entre elles : les clés publiques et privées.

Dans notre précédent article sur le [Stockage de Crypto](https://bit.ly/2UtogzI), nous avons largement utilisé ces deux termes pour expliquer les avantages des porte-monnaie matériels. Nous allons maintenant les décomposer pour montrer comment ils s'intègrent dans l'écosystème plus large qui nous entoure.

Pour ce faire, nous devons commencer par les bases de la cryptographie, l'idée fondamentale sur laquelle reposent les clés publiques et privées.<br/> 

## **Qu'est-ce que la cryptographie?**

Le mot cryptographie, comme de nombreux autres mots de la langue anglaise, trouve ses racines dans le grec. En résumé, le mot se traduit grossièrement par "écriture cachée". Dans un environnement comme Internet où la vie privée peut sembler rare, les clés publiques et privées permettent aux gens de communiquer par la cryptographie.

En quoi cela vous concerne-t-il ? Imaginons que vous envoyiez un document important à un ami par Internet. Il s'agit peut-être d'une note secrète que vous voulez qu'il soit le seul à voir ou de votre contrat de location. Vous voulez envoyer ce document à votre ami et vous voulez vous assurer que personne d'autre que lui ne pourra le lire. C'est là que les clés publiques et privées entrent en jeu sous la forme de la cryptographie asymétrique.<br/> 

## **Cryptographie asymétrique et symétrique**.

La cryptographie asymétrique est une méthode qui utilise une clé pour chiffrer des données (la clé publique) et une clé pour déchiffrer des données (la clé privée). À l'inverse, la cryptographie symétrique utilise la même clé pour crypter et décrypter le même élément de données.

Par conséquent, la cryptographie asymétrique est plus sûre que la cryptographie symétrique, mais le processus peut prendre *légèrement* plus de temps car vous avez affaire à deux clés au lieu d'une.

Comme la cryptographie asymétrique est utilisée dans le protocole Bitcoin, c'est sur elle que nous allons nous concentrer.

Ok, restons-en à l'exemple de l'envoi de votre contrat de location à un ami. Si vous voulez vous assurer, grâce à la cryptographie, qu'il est le seul à pouvoir lire le contrat, voici les étapes à suivre :

1. Obtenir la clé publique de votre ami
2. Crypter le contrat avec cette clé publique
3. Envoyez l'accord crypté à votre ami
4. Votre ami reçoit le contrat crypté et le décrypte avec sa clé privée.

De cette façon, n'importe qui peut envoyer à votre ami des données cryptées en utilisant la clé publique de cet ami, tandis que votre ami est le seul à pouvoir les décrypter et lire les messages cryptés. Cela fonctionne de la même manière que n'importe qui peut vous envoyer un courriel, mais vous seul pouvez ouvrir votre boîte aux lettres et lire les messages.<br/> 

## **Comment cela se rapporte aux crypto-monnaies ?**

Quel est le lien avec la technologie blockchain et les crypto-monnaies ? À un niveau de base, les clés publiques et privées sont l'un des composants fondamentaux qui rendent les transactions possibles sur la blockchain.

Lorsque vos clés sont créées, votre clé publique est soumise à [une fonction de hachage](https://www.investopedia.com/terms/h/hash.asp), et la chaîne aléatoire de lettres et de chiffres qui en résulte est utilisée comme adresse de votre porte-monnaie. Les transactions fonctionneront comme notre exemple de contrat de location ci-dessus.

Prenons l'exemple du Bitcoin. Tout d'abord, quelqu'un envoie des bitcoins à l'adresse de votre porte-monnaie. Ce faisant, il vous donne le droit de dépenser ces bitcoins, *pour autant que vous puissiez prouver que vous êtes le propriétaire de l'adresse*. En signant la transaction à l'aide de la clé privée correspondante, vous devenez propriétaire de ce droit de dépenser ([Pour en savoir plus sur les UTXO, cliquez ici](https://www.investopedia.com/terms/u/utxo.asp)).

Connaître les bases des clés publiques et privées est fondamental pour comprendre le protocole Bitcoin, et impressionner vos amis.

---

> Ce document a été publié à l'origine le 2019-05-12 par Ari Chernoff et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/the-power-of-cryptography).
{.is-success}

---

- bounty: true
- amt: 29
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}