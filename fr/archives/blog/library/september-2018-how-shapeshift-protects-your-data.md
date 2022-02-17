---
title: Comment ShapeShift protège vos données
description: ShapeShift s'engage à faire tout ce qui est en son pouvoir pour protéger les données de ses clients.
published: true
date: 2021-12-20T23:02:39.376Z
tags: library, security, shapeshift, needs-review, sécurité
editor: markdown
dateCreated: 2021-12-20T23:02:39.376Z
---

# Comment ShapeShift protège vos données

ShapeShift offre aux utilisateurs une variété d'avantages uniques et intéressants, tels que des frais réduits, des limites de trading plus élevées, des récompenses sur le volume de trading, un accès transparent aux échanges décentralisés, etc. Bien que certains services n'exigent pas que nous recueillions et conservions les données des clients (ou pratiques "Know Your Customer"), d'autres — comme l'achat de Bitcoin — le font quand même afin de répondre aux exigences réglementaires.

À ShapeShift, nous nous engageons à faire tout ce qui est possible pour assurer la sécurité des données de nos clients. Nous nous sommes posés la question suivante : "Que peuvent faire les pirates s'ils s'introduisent dans nos systèmes ?" afin d'éclairer nos décisions de conception.

Pour nos services nécessitant un contrôle KYC, la plateforme ShapeShift recueille vos informations et les crypte immédiatement avec une clé RSA de 4096 bits à l'aide du logiciel open-source GPG largement utilisé. Ces données cryptées sont stockées dans notre base de données et, dans la plupart des cas, ne sont plus jamais utilisées. Une fois qu'elles ont été collectées, nous n'avons pas besoin d'y faire référence pour quelque raison professionnelle que ce soit.

Si vous rencontrez un problème et contactez le service clientèle (par exemple pour obtenir de l'aide), celui-ci ne voit pas votre nom ou vos coordonnées par défaut, ce qui lui permet de se concentrer sur votre problème plutôt que sur votre identité.

Il n'y a que quelques cas où notre personnel a besoin d'utiliser les informations relatives à votre identité. Par exemple, si vous perdez à la fois votre mot de passe et l'authentification à deux facteurs et que vous essayez de vous reconnecter à votre compte, notre personnel aura besoin de connaître votre nom et d'autres informations afin de les comparer avec ce que vous leur avez donné. Dans ce cas, nos agents du service clientèle téléchargeront vos données cryptées sur leur machine et utiliseront un dispositif de stockage à froid contenant la clé privée pour décrypter vos informations. Cette opération est gérée au cas par cas, ce qui permet d'éviter que tout employé de l'entreprise ait accès à l'ensemble des informations relatives aux clients. Un autre exemple serait si nous étions légalement contraints de le faire par une assignation à comparaître ou un document similaire valide. Pour plus d'informations sur cet exemple, veuillez consulter notre politique de confidentialité [ici](https://shapeshift.com/privacy).

Étant donné que les serveurs de ShapeShift n'ont jamais la clé de décryptage d'aucune information personnelle (elle est conservée en stockage à froid), même si un attaquant pénètre dans les serveurs et copie toute la base de données, il ne pourra pas voir ou accéder à vos informations. Si l'un de nos dispositifs de stockage à froid est perdu ou volé, il est configuré pour s'effacer de lui-même dans certaines circonstances.

ShapeShift comprend la valeur de vos données et de votre vie privée. Nous nous engageons à assurer la sûreté et la sécurité de vos informations tout en fournissant les meilleures solutions financières décentralisées et non-dépositaires (non-custodial) de l'industrie.<br/>

---

> Ce document a été publié à l'origine le 2018-09-04 par Michael Perklin, CISO at ShapeShift et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/how-shapeshift-protects-your-data).
{.is-success}

---

- bounty: true
- amt: 21
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}