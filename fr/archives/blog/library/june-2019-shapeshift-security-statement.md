---
title: Déclaration de sécurité de ShapeShift
description: Notre réponse à la clarification des récentes revendications de Ledger à #BreakingBitcoin.
published: true
date: 2021-12-20T23:03:03.761Z
tags: library, security, keepkey, bitcoin, needs-review, sécurité
editor: markdown
dateCreated: 2021-12-20T23:03:03.761Z
---

# Déclaration de sécurité de ShapeShift

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fdf3cce036369ec8de731_1_R53l5-JzGtTc0ZTNCs9HfQ.png)

Le week-end dernier, lors de la [Breaking Bitcoin Conference](https://twitter.com/breakingbitcoin), Charles Guillemet, responsable de la sécurité pour Ledger, a présenté *Extraction des graines des porte-monnaie (matériels)*. La présentation a exposé les vulnérabilités des porte-monnaie matériels ouverts — y compris [KeepKey](https://www.keepkey.com/). Cette vulnérabilité a entraîné l'extraction de la clé privée.

**Nous considérons cette catégorie de vulnérabilité — celle qui peut révéler des clés privées — comme le type de bogue le plus critique.**

Nous avons donc creusé davantage pour comprendre le problème.

Bien que Guillemet n'ait pas été en mesure de préciser comment Ledger a récupéré la clé privée, ShapeShift est au courant d'une attaque qui donne la clé privée *depuis* avant que nous ayons acquis KeepKey en 2017.<br/> 

## Comment fonctionne cette attaque

Un attaquant **vole** votre appareil KeepKey, l'ouvre et utilise des appareils électroniques spécialisés pour lire les données cryptées de la mémoire flash. Ensuite, il utilise un logiciel pour deviner votre code NIP en essayant toutes les combinaisons possibles. Pour réussir cette attaque, il faut :

* Des connaissances, des compétences et de l'expérience spécialisées en ingénierie matérielle.
* Des connaissances, des compétences et une expérience spécialisées en ingénierie logicielle.
* Un logiciel spécialisé conçu pour deviner tous les codes NIP possibles.
* La possession physique de votre KeepKey.

Les porte-monnaie matériels (comme KeepKey) sont conçus pour vous protéger contre les vecteurs d'attaque les plus courants, notamment les logiciels malveillants, les virus et les pirates à distance qui cherchent à voler des clés privées. Mais la vulnérabilité à laquelle Guillemet et Ledger font référence n'attaque pas les clés de cette manière.

**Il s'agit plutôt d'une vulnérabilité pour laquelle un attaquant doit être en possession physique de votre clé KeepKey.** Le rôle de KeepKey est de protéger vos clés contre les attaques à distance.

Si quelqu'un d'autre a un accès physique à votre appareil — ainsi que le temps, les compétences et les outils nécessaires — il sera **toujours** en mesure d'ordonner à l'appareil de faire ce qu'il veut, en contournant tout verrou numérique existant.

**Ceci est également vrai pour tout porte-monnaie matériel.**

Bien sûr, ce n'est pas nouveau. Les entreprises luttent en vain contre ce problème dans l'informatique depuis des décennies, car il se pose dans de nombreux secteurs.

Par exemple, les systèmes d'exploitation, les applications et les médias numériques utilisent des verrous numériques pour s'assurer que les utilisateurs finaux ont payé les licences. Les pirates modifient le code sur leurs machines locales pour faire croire au système qu'il a bien payé.

Les jeux utilisent une variété de verrous numériques pour empêcher la tricherie, mais les tricheurs modifient les jeux pour jouer comme ils le souhaitent.

Et chaque fois qu'un ingénieur brillant pense à un nouveau type de verrou numérique, un pirate tout aussi brillant analyse le verrou sur sa propre machine pour comprendre comment il fonctionne — et utilise ensuite ces connaissances pour le contourner.

**C'est comme un labyrinthe dont on peut voir tous les tours et détours — le tout avec une vue d'ensemble.**

Le fait est qu'il n'y a aucun moyen d'empêcher un attaquant très sophistiqué, en possession physique de l'appareil et disposant de beaucoup de temps, de technologie et de ressources, de pirater complètement cet appareil — à terme.

ShapeShift vous recommande de sécuriser votre appareil avec la même prudence que pour d'autres investissements ou objets de valeur. Protégez votre clé KeepKey comme si elle pouvait être volée demain.

**C'est comme un labyrinthe dont on peut voir tous les tours et détours — le tout avec une vue d'ensemble.**

Alors que les codes NIP ajoutent 4 à 9 chiffres simples pour créer une barrière entre les pirates et votre ou vos clés privées, 9 chiffres ne suffisent pas. Dans sa présentation, Guillemet a démontré que vous pouvez deviner un code PIN à 9 chiffres en une minute environ.

Avec KeepKey, vous êtes en mesure de définir une phrase de passe qui fournit une couche supplémentaire de protection.

Guillemet recommande d'utiliser des phrases de passe composées d'au moins 32 chiffres et d'une combinaison unique de chiffres, de symboles, ainsi que de lettres majuscules et minuscules.

Avec une [phrase de passe suffisamment longue](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-), si un pirate extrait les données de votre appareil, il ne sera jamais en mesure de le déverrouiller. Votre code NIP et votre phrase de passe protègent vos fonds.<br/> 

## Activer votre phrase de passe BIP39 avec le [Client KeepKey](https://chrome.google.com/webstore/detail/keepkey-client/idgiipeogajjpkgheijapngmlbohdhjg)

1. Branchez et déverrouillez votre KeepKey
2. Cliquez sur l'icône d'engrenage **⚙️** située en haut à gauche du client KeepKey.
3. Cliquez sur "Activer la phrase de passe BIP39".
4. Saisissez une phrase de passe longue (vous serez invité à la saisir/confirmer à nouveau).
5. Copiez/écrivez vos nouvelles adresses de Bitcoin/Litecoin/etc. à partir de votre compte protégé par une phrase de passe.
6. Débranchez votre clé KeepKey et rebranchez-la.
7. Ne saisissez pas de phrase de passe. Cliquez sur "OK" avec une phrase de passe vide pour accéder à vos comptes originaux non protégés.
8. Envoyez vos bitcoins/litecoins/etc. aux adresses que vous avez copiées au point 5 (ci-dessus). Vérifiez que les adresses n'ont pas été modifiées par un logiciel malveillant de détournement de presse-papiers.
9. Débranchez votre clé KeepKey et rebranchez-la.
10. Entrez votre phrase de passe et cliquez sur "OK".
11. Vous pouvez maintenant voir toutes vos monnaies sur vos adresses cryptées par votre phrase de passe.<br/> 

## Conclusions

Si vous êtes intéressé par une sécurité supplémentaire pour vous protéger contre ce cas limite extrêmement improbable, consultez la page [*Comment puis-je accéder à mon compte de Membre ShapeShift avec une phrase de passe?*](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-).

Si vous êtes un chercheur en sécurité qui a identifié ce que vous croyez être un bogue ou une vulnérabilité dans l'un des produits ou services de ShapeShift, nous aimerions avoir de vos nouvelles.

Et nous sommes toujours prêts à vous aider. [Contactez notre équipe de soutien](https://shapeshift.zendesk.com/hc/en-us/requests/new) — à tout moment.

---

> Ce document a été publié à l'origine le 2019-06-13 par ShapeShift Team et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/shapeshift-security-statement).
{.is-success}

---

- bounty: true
- amt: 40
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}