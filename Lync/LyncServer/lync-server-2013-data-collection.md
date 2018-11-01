---
title: 'Lync Server 2013 : Collecte des données'
TOCTitle: Collecte des données
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399008(v=OCS.15)
ms:contentKeyID: 49299146
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Collecte des données dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Dans le Microsoft Lync Server 2013  logiciels de communication, vous pouvez exécuter l’outil de planification Microsoft Lync Server 2013 sans documenter vos adresses IP existantes et proposées ni les noms de domaine complets (FQDN) de serveur Edge, mais il est bien plus difficile d’effectuer cette opération sans provoquer d’erreur de configuration. Par exemple, si la coexistence est requise pour une certaine période, une erreur commune consiste à réutiliser les FQDN d’un déploiement Edge existant pour votre déploiement Edge Lync Server 2013. Inscrire les adresses IP existantes et proposées ainsi que les FQDN dans une feuille de calcul, un tableau ou un autre formulaire visuel peut vous aider à prévenir les problèmes de configuration lors de l’installation.

> [!WARNING]  
> Si vous avez utilisé des versions précédentes de l’outil de planification, vous avez peut-être utilisé l’outil pour créer votre topologie et exporté le document de topologie pour l’utiliser dans le Générateur de topologie pour publier votre topologie. La possibilité d’exporter la topologie a été supprimée de l’outil de planification. Il est fortement déconseillé d’utiliser une version précédente de l’outil de planification pour créer un document de topologie pour Lync Server 2013. Cela peut avoir des conséquences inattendues.

Par conséquent, la méthode recommandée consiste à utiliser le modèle de collecte des données suivant, qui correspond à votre topologie Edge afin de réunir les FQDN et adresses IP que vous devrez saisir dans l’outil de planification. En documentant la configuration actuelle et proposée, vous pouvez saisir les valeurs dans le contexte approprié pour votre environnement de production. Et vous devez réfléchir à la façon dont vous configurerez la coexistence et les fonctionnalités comme les URL simples, les partages de fichiers et l’équilibrage de charge.

Pour déployer correctement Microsoft Lync Server 2013, il faut comprendre l’interaction avec et la dépendance vis-à-vis des composants individuels. En recueillant des données à partir de votre infrastructure de réseau et de serveur existante, et en appliquant les instructions de planification contenues dans ces sections, vous pouvez intégrer des composants serveur EdgeLync Server 2013 à votre infrastructure.

Il existe trois architectures principales, présentées dans [Sélection d’une topologie dans Lync Server 2013](lync-server-2013-choosing-a-topology.md), comprenant deux variations, ce qui produit un total de cinq scénarios de déploiement possibles. L’un de ces scénarios sera le point de départ de votre collection de données. Les adresses IP, noms de serveurs et noms de domaines sont des exemples qui coïncident avec les certificat, pare-feu et diagrammes DNS correspondants qui détaillent les informations requises pour une solution de planification complète. Les diagrammes et le remplissage des valeurs requises de votre certificat, DNS et pare-feu sont particulièrement importants dans les communications inter-équipes, où la gestion de l’autorité de certification, de la configuration du pare-feu et du DNS est assurée par d’autres équipes que celle qui planifie le déploiement. Les diagrammes fournissent des informations sur les composants requis qui peuvent être utilisées pour communiquer ces exigences pour la collaboration inter-équipes.

Les diagrammes fournis sont volontairement génériques, mais prennent en compte la collection de toutes les données pertinentes nécessaires à la communication des exigences dans un scénario entre équipes où la gestion du réseau, du pare-feu, la création et la gestion de certificats, le déploiement de serveur et la gestion de serveur sont assurés par différents groupes. Les informations requises concernant la configuration de la gestion du réseau, des pare-feu, des ports et protocoles, des certificats et des serveurs sont précieuses lorsque le déploiement de Lync Server est en cours.

**serveur Edge et pool de serveurs Edge**

![Serveur Edge et pool Edge](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "Serveur Edge et pool Edge")

**Proxy inverse**

![Proxy inverse](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "Proxy inverse")

**directeur or pool de directeurs**

![Directeur et pool directeur](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "Directeur et pool directeur")

