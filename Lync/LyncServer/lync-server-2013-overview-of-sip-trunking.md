---
title: 'Lync Server 2013 : Vue d’ensemble d’une jonction SIP'
TOCTitle: Vue d’ensemble d’une jonction SIP
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398285(v=OCS.15)
ms:contentKeyID: 49296463
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble d’une jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Le déploiement d’une jonction SIP peut contribuer grandement à simplifier les télécommunications de votre organisation et à préparer celle-ci en vue des dernières améliorations apportées aux communications en temps réel. L’un des principaux avantages qu’offre le déploiement d’une jonction SIP est que vous pouvez consolider les connexions de votre organisation vers le réseau téléphonique commuté (RTC) sur le site central, contrairement à la jonction TDM, qui nécessite une jonction distincte pour chaque site de succursale vers le site central.

## Jonction SIP dans Lync Server

Les fonctionnalités de jonction SIP de Lync Server 2013 offrent les avantages suivants :

  - Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou un appel longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de service correspondant.

  - Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing \[DID\]) associé à cet utilisateur.

## Économies

Les économies associées à la jonction SIP peuvent être substantielles :

  - Les appels longue distance coûtent en général moins cher via une jonction SIP.

  - Vous pouvez réduire les coûts de gestion et la complexité du déploiement.

  - Les coûts d’accès de base (Basic rate interface, BRI) et d’accès primaire (Primary Rate Interface, PRI) sont éliminés si vous connectez une jonction SIP directement à votre fournisseur de services de téléphonie Internet pour un coût nettement plus bas. Avec une jonction TDM, les fournisseurs de service facturent les appels à la minute. Le coût d’une jonction SIP peut être basé sur l’utilisation de la bande passante, que vous pouvez acheter en plus petites tranches plus économiques. (Le coût réel dépend du modèle de service du fournisseur de services de téléphonie Internet que vous choisissez.)

## Jonction SIP comparée à l’hébergement d’une passerelle RTC ou d’un PBX IP

Étant donné que les jonctions SIP se connectent directement à votre fournisseur de service, vous pouvez éliminer les passerelles RTC et éviter le coût et la complexité de leur gestion. L’utilisation d’une jonction SIP peut se traduire par des économies substantielles, car les tâches de maintenance et d’administration sont réduites.

## Services VoIP étendus

Bénéficier de fonctionnalités vocales est souvent la principale motivation pour déployer une jonction SIP, mais la prise en charge de fonctionnalités vocales n’est que la première étape. Avec une jonction SIP, vous pouvez étendre les fonctionnalités VoIP et permettre à Lync Server 2013 d’offrir des services plus sophistiqués. Par exemple :

  - La détection de la présence pour les périphériques qui n’exécutent pas Lync Server 2013 peut permettre une meilleure intégration des téléphones mobiles, ce qui vous permet de savoir quand un utilisateur est occupé sur un téléphone mobile.

  - Le service d’appels d’urgence E9-1-1 permet aux services de secours qui répondent aux appels d’urgence de déterminer l’emplacement de la personne qui appelle à partir de son numéro de téléphone.

> [!NOTE]  
> Contactez votre fournisseur de services de téléphonie Internet pour savoir quels services il prend en charge et peut activer pour votre organisation.
