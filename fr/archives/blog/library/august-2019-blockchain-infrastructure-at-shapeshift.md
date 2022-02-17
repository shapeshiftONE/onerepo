---
title: Infrastructure Blockchain à ShapeShift
description: Découvrez comment l'équipe d'ingénieurs de ShapeShift structure ses nœuds de blockchain. 
published: true
date: 2021-12-20T23:02:20.719Z
tags: library, bitcoin, developer, cryptocurrency, needs-review, crypto-monnaie, développeur
editor: markdown
dateCreated: 2021-12-20T23:02:20.719Z
---

# Infrastructure Blockchain à ShapeShift

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbae5efc62b1120b46150_1_F0R4y3MkSpLjbo0bRB10Yw%20(1).png)

Les nœuds de blockchain (coins daemons) sont des programmes qui valident entièrement les transactions et les blocs. Ils sont les passerelles vers les crypto-monnaies que nous prenons en charge. [**ShapeShift**](http://shapeshift.com/) s'appuie sur les nœuds de blockchain pour recevoir et relayer les données de transactions, ce qui les rend essentiels à nos opérations commerciales.

La gestion de centaines de nœuds est un problème auquel de nombreux acteurs du secteur doivent faire face. Afin de faire évoluer les opérations pour prendre en charge plus de quelques centaines de transactions, ces nœuds de blockchain doivent être exécutés en parallèle pour réduire le stress qui leur est imposé. Certains nœuds de blockchain ne sont pas fiables, présentent de graves limitations de performance et manquent souvent de documentation appropriée.

Pour couronner le tout, la plupart des nœuds de blockchain ont besoin d'une grande capacité de stockage afin de conserver l'historique des transactions. Certains de ces volumes de données peuvent atteindre une taille de plusieurs téraoctets.

Nous avons cherché à créer un cadre qui permettrait de gérer la construction, le déploiement et la surveillance des nœuds de blockchain. Ce cadre devrait répondre à plusieurs exigences :

* Builds automatisés
* Conteneurisation à 100%.
* Plusieurs versions déployées simultanément
* Haute disponibilité/résilience (multi-datacenter)
* Extensible (mise en place rapide de nouveaux nœuds)

Après avoir répété une fois de trop la phrase "Coin Daemon Container", nous avons décidé de nommer le framework "Cointainers".

## Outillage de la plateforme

Pour construire la plateforme Cointainers, nous avions besoin d'un outil qui nous permettrait d'itérer rapidement sur les builds et les déploiements. Docker a été un choix facile à cet égard, nous permettant de créer des builds reproductibles sur toutes les plateformes avec très peu de configuration.

Pour exécuter les builds Docker dans les systèmes de production, nous avons opté pour Kubernetes, qui prend en charge les [applications stateful](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) et [des plugins de stockage pour tous les principaux clouds](https://kubernetes.io/docs/concepts/storage/).<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb02efc62b44b7b47b60_1*FHxwJvmHucRhWCvEIUXfKw.png)

Nous avions également besoin que tous les builds et l'infrastructure soient reproductibles, ce qui impliquait d'incorporer une forme d'infrastructure en tant que code (IaC) dans le mélange. [Terraform](https://www.terraform.io/) est généralement la solution la plus répandue dans ce domaine, car il s'agit du framework IaC le plus important et le plus utilisé. Hashicorp (la société à l'origine de Terraform) a également annoncé récemment [une prise en charge de premier plan de Kubernetes dans Terraform](https://www.hashicorp.com/blog/first-class-kubernetes-support-for-hashicorp-products).

Cependant, Terraform nécessite l'apprentissage d'un nouveau langage, le [HCL DSL](https://github.com/hashicorp/hcl). L'utiliser augmenterait la barrière d'entrée pour nos ingénieurs pour apprendre et travailler sur Cointainers. C'est là que Pulumi entre en jeu.

Pulumi est un framework d'infrastructure en tant que code très similaire à Terraform, décrit par l'entreprise sur sa [page de comparaison](https://www.pulumi.com/docs/reference/vs/terraform/) :

*Pulumi est comme Terraform, en ce sens que vous créez, déployez et gérez une infrastructure en tant que code sur n'importe quel cloud. Contrairement à Terraform, cependant, vous utiliserez des outils et des langages généraux familiers pour le faire. Comme Terraform, Pulumi est* [*open-source sur GitHub*](https://github.com/pulumi/pulumi) *et est* [*libre d'utilisation*](https://www.pulumi.com/docs/quickstart/)*.*

En utilisant Pulumi, nous sommes en mesure de tirer profit des langages de haut niveau avec lesquels la plupart de nos ingénieurs sont déjà familiarisés. Il nous permet également d'être plus expressifs avec notre IaC en évitant les limitations du Hashicorp Configuration Language (HCL). Ceci est également souligné dans la comparaison.

*Grâce à l'utilisation de langages réels, vous obtenez des constructions familières comme les boucles for, les fonctions et les classes. Cela améliore considérablement la capacité à limiter l'emploi de modèles passe-partout et à appliquer les meilleures pratiques. Au lieu de créer un nouvel écosystème de modules et de partage, Pulumi vous permet de vous appuyer sur les outils et les techniques de gestion de paquets existants.*

## Build

Un Cointainer commence par une image Docker. À l'intérieur, nous plaçons le binaire du daemon de la monnaie (logiciel du nœud de blockchain). Nous construisons également un deuxième Container (sidecar), qui fonctionne à côté du logiciel du nœud pour le surveiller.<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03533c77038410f85b_1*z9XydSqnB12ApvEF3Gt8fw.png)

Comme nous devons prendre en charge plusieurs versions, notre processus de build ressemble à ceci :

1. Lire la liste des nœuds de monnaie que nous devons construire (par exemple Bitcoin, Dogecoin, Ethereum, etc.)
2. Télécharger les N* dernières versions du daemon de monnaie (par exemple bitcoin-0.18.0, bitcoin-1.17.1, bitcoin-0.17.0.1, etc.)
3. Construire des Cointainers Docker contenant le logiciel du daemon de la monnaie.
4. Construire le Container Docker pour les nœuds de surveillance.
5. Test d'intégration de tous les Containers
6. Publier les Containers dans le Dépôt d'Images

**Personnalisable par monnaie**

En utilisant le module [@pulumi/docker](https://github.com/pulumi/pulumi-docker), nous sommes en mesure de créer des dépôts de Containers Docker, de construire nos images Docker, et de les publier vers les dépôts, le tout en un seul flux de travail.<br/> 

    $ make deploy
    
    Previewing deploy
    
         |   Type                         | Name           | Plan
    --------------------------------------------------------------
     +   ├─ cointainer:Deploys             ethereum         create
     +   │  ├─ container:Deploy            ethereum:2.4.5   create
     +   │  |  ├─ container:StatefulSet    ethereum:2.4.5   create
     +   │  |  ├─ container:AutoScaler     ethereum:2.4.5   create
     +   │  |  ├─ container:IngressRule    ethereum:2.4.5   create
     +   │  |  ├─ container:MonitorAlert   ethereum:2.4.5   create
     +   │  └─ container:Deploy            ethereum:2.6.5   create
     +   │     ├─ container:StatefulSet    ethereum:2.6.5   create
     +   │     ├─ container:AutoScaler     ethereum:2.6.5   create
     +   │     ├─ container:IngressRule    ethereum:2.6.5   create
     +   │     ├─ container:MonitorAlert   ethereum:2.6.5   create
    Resources:
        + 8 resources to create
    
    Do you want to apply to changes?
      yes
    > no
      details


## Déploiement

Nous utilisons également Pulumi dans le cadre de notre processus de déploiement pour créer les ressources requises à l'intérieur de nos clusters Kubernetes. Le module [@pulumi/kubernetes](https://github.com/pulumi/pulumi-kubernetes) nous permet de créer des IngressRules, des StatefulSets et des HorizontalPodAutoscalers.

Afin que nos développeurs disposent toujours des versions les plus récentes des nœuds pour travailler, nous avons mis en place une automatisation qui vérifie les nouvelles versions et les déploie de manière périodique.

Notre flux de travail de déploiement crée nos ressources et notre surveillance en une seule fois :

1. Trouver toutes les versions des nœuds que nous avons construits précédemment.
2. Déployer les versions qui ne sont pas dans l'environnement.
3. Créer un suivi et des alertes pour chaque version déployée
 
 ____

    $ make deploy
    
    Previewing deploy   
    
         |   Type                         | Name           | Plan
    --------------------------------------------------------------
     +   ├─ cointainer:Deploys             ethereum         create
     +   │  ├─ container:Deploy            ethereum:2.4.5   create
     +   │  |  ├─ container:StatefulSet    ethereum:2.4.5   create
     +   │  |  ├─ container:AutoScaler     ethereum:2.4.5   create
     +   │  |  ├─ container:IngressRule    ethereum:2.4.5   create
     +   │  |  ├─ container:MonitorAlert   ethereum:2.4.5   create
     +   │  └─ container:Deploy            ethereum:2.6.5   create
     +   │     ├─ container:StatefulSet    ethereum:2.6.5   create
     +   │     ├─ container:AutoScaler     ethereum:2.6.5   create
     +   │     ├─ container:IngressRule    ethereum:2.6.5   create
     +   │     ├─ container:MonitorAlert   ethereum:2.6.5   create
    Resources:
        + 8 resources to create
    
    Do you want to apply to changes?
      yes
    > no
      details
 

Pour en savoir plus sur l'utilisation de Pulumi avec Kubernetes, [cliquez ici](https://www.pulumi.com/blog/pulumi-a-better-way-to-kubernetes/)

## Architecture

Lors de chaque démarrage de nœud, nous vérifions si le volume de données possède une copie de la blockchain. S'il s'agit d'une réplique d'un nouveau nœud et qu'il n'y a pas de blocs, ou si la chaîne est trop en retard, nous téléchargeons une sauvegarde pour éviter d'attendre que le nœud se synchronise manuellement (ce qui peut prendre des semaines).<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb0354b6e3785920e526_1*zbFYJNWGRzpdYp8GSPu8Qg.png)

<br/>Une fois la sauvegarde téléchargée et le logiciel du nœud lancé, nos systèmes attendent qu'il soit synchronisé à 100% avant de le rendre disponible.

Notre Container de surveillance vérifie la hauteur des blocs du nœud par rapport aux explorateurs de blocs externes, et vérifie également si le nœud signale qu'il est toujours en train de synchroniser des blocs. Une fois que le nœud est entièrement synchronisé et que sa hauteur de bloc est supérieure ou égale à celle de l'explorateur de blocs, nous le plaçons derrière le répartiteur de charge.

Si le nœud prend du retard, nous le retirons du répartiteur de charge et attendons qu'il le rattrape avant de le remettre au service des clients.

<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03efc62b63e2b47b93_1*00OwEzzfIBPJliOyj3wMjA.png)

Le trafic va uniquement aux nœuds sains/synchronisés<br/>Nous maintenons un minimum de 3 nœuds pour chaque version de monnaie dans plusieurs centres de données : Un réservé aux sauvegardes, et deux pour maintenir la fiabilité. Lorsque la charge augmente sur les nœuds de monnaie, nos systèmes en lancent automatiquement davantage pour répondre à la demande.

À un niveau supérieur, nous servons plusieurs versions des nœuds pour nos applications. Cela permet à nos équipes de développement de changer de version à tout moment, en leur donnant la possibilité de revenir en arrière immédiatement si nécessaire.<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb03df8913769e880eb2_1*3tI4eIfns6iJEmvzUO6q9Q.png)

Versions multiples de Bitcoin<br/>

Après la migration de toutes nos applications de l'ancienne version vers la nouvelle, nous la mettons hors service et conservons les autres versions dont nos applications dépendent encore.<br/> 

## Surveillance

À l'aide des superviseurs créés lors du déploiement, nos systèmes vérifient la santé des Cointainers toutes les 15 secondes pour s'assurer qu'ils sont joignables et répondent avec des données valides. Nous surveillons également le nombre de répliques de nœuds que nous exécutons pour chaque version de monnaie. Si une version de monnaie a moins de deux nœuds actifs, nos systèmes de surveillance déclenchent des alarmes qui avertissent nos ingénieurs et nos équipes de services aux membres.

Si vous souhaitez travailler sur des projets tels que les Cointainers, consultez notre page [**Carrières**](http://shapeshift.com/careers) ! Nous sommes à la recherche de : Ingénieurs logiciels, VP du marketing, et licornes 🦄 !<br/> 

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbb037e6909591b3c32e2_1*0CtbPVcRkofblk3ZXkUuXw.png)

---

> Ce document a été publié à l'origine le 2019-08-13 par Azamat Mukhiddinov et peut avoir été légèrement modifié à des fins de traduction par le groupe de travail Information and Globalization pour un projet d'archivage en cours.
>
> L'article original se trouve [ici](https://shapeshift.com/library/blockchain-infrastructure-at-shapeshift).
{.is-success}

---

- bounty: true
- amt: 61
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}