---
title: Topologie de référence Lync Server 2013 pour les grandes organisations disposant de plusieurs centres de données
description: Topologie de référence Lync Server 2013 pour les grandes organisations disposant de plusieurs centres de données.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb88bd59e4bc27aefbdc94fdf53f094a09998f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567600"
---
# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topologie de référence pour Lync Server 2013 dans les grandes organisations disposant de plusieurs centres de données

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

La topologie de référence pour une grande organisation disposant de plusieurs centres de données est prise en charge pour n’importe quelle taille d’organisation avec plusieurs sites centraux. La topologie exacte dans le diagramme suivant est pour une organisation de 50 000 utilisateurs, avec 20 000 utilisateurs sur le site central A, 20 000 sur le site central B. et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie indiqué dans ce diagramme peut s’appliquer à des organisations avec n’importe quel nombre d’utilisateurs.

En plus de la haute disponibilité offerte par les pools de serveurs frontaux, cette topologie ajoute la prise en charge de la récupération d’urgence. Les pools frontaux sur les sites centraux A et B sont associés ensemble. Si l’un de ces pools tombe en panne, l’administrateur peut décaler les services des utilisateurs concernés vers le pool couplé sur le site non affecté.

Cette topologie est illustrée dans plusieurs diagrammes, avec une vue d’ensemble, suivie de vues détaillées des sites centraux.

**Vue d’ensemble de la topologie de référence pour les grandes organisations disposant de plusieurs centres de données**

![Topologie de référence pour plusieurs centres de données](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologie de référence pour plusieurs centres de données")

**Topologie de référence pour les grandes organisations : vue détaillée du site central A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topologie de référence pour les grandes organisations : vue détaillée du site central B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topologie de référence pour les grandes organisations : vue détaillée du site central C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **Les pools frontaux sont associés pour activer la récupération d’urgence.**     Les pools frontaux sur le site A et le site B sont couplés les uns avec les autres pour fournir la prise en charge de la récupération d’urgence. Si le pool d’un site échoue, l’administrateur peut faire basculer les utilisateurs de ce site vers le pool frontal couplé au niveau de l’autre site, avec un minimum d’interruption de service pour les utilisateurs. Chacun de ces deux pools frontaux comporte six serveurs, ce qui est suffisant pour tous les utilisateurs de 40 000 dans les deux pools en cas de basculement. Pour plus d’informations, reportez-vous à la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Les serveurs principaux sont mis en miroir**     Afin de fournir une haute disponibilité pour les fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs principaux en miroir pour chaque pool frontal. Il s’agit d’une topologie facultative et vous pouvez choisir de déployer un seul serveur principal à la place.

  - **À l’aide du serveur Standard Edition sur un site de succursale.**     Cette organisation considère le site C comme un site de succursale, car il compte seulement 600 employés. Toutefois, les utilisateurs comportent de nombreuses conférences A/V entre eux. Si elle a été déployée dans Lync Server en tant que site de succursale, le support de ces conférences s’exécutera sur le réseau étendu (WAN) vers et à partir d’un site central sur lequel un serveur frontal est déployé. Pour éviter cette charge de bande passante potentielle, ils ont installé une paire de serveurs Standard Edition Server sur ce site, qui hébergeront ces conférences. Étant donné que les serveurs Standard Edition sont installés ici, Lync Server par définition considère qu’il s’agit d’un site central et est traité comme tel dans le générateur de topologie et l’outil de planification.
    
    Un seul serveur Standard Edition suffisait pour les performances ici, mais l’organisation a déployé deux et l’ont couplés ensemble pour fournir une haute disponibilité en cas de panne d’un serveur.
    
    Bien que le site C soit considéré comme un site central, il n’est pas nécessaire de déployer des serveurs Edge. Dans cet exemple, le site C utilise les serveurs Edge déployés sur le site A.

  - **Surveillance et archivage**     Cette organisation a déployé la surveillance et l’archivage. Lorsque vous déployez la surveillance ou l’archivage, elle s’exécute sur chaque serveur frontal. Les bases de données de ces fonctionnalités peuvent être colocalisées avec la base de données principale ou se trouver sur un serveur distinct. Cette organisation a localisé ces bases de données sur un serveur distinct des serveurs principaux, dans le site central B. Les bases de données reçoivent des données de surveillance et d’archivage à partir des serveurs frontaux de tous les sites.

  - **Options de déploiement de site de succursale.**     Cette organisation dispose en fait de plus de 50 sites de succursale, dont trois seulement sont affichés dans les diagrammes détaillés. Les sites de succursale 1 et 3 n’ont pas de liaison de réseau étendu résiliente au site central, de sorte qu’ils disposent d’un Survivable Branch Appliances déployés pour fournir un service téléphonique en cas de panne de la liaison de réseau étendu vers le site central. Le site de succursale 2 possède toutefois une liaison de réseau étendu résilient, de sorte que vous n’avez besoin que d’une passerelle de réseau téléphonique commuté (PSTN). La passerelle PSTN déployée prend en charge la déviation du trafic multimédia, de sorte qu’aucun serveur de médiation n’est nécessaire sur le site de succursale B. Pour plus d’informations sur les éléments à installer sur un site de succursale, voir [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.

  - **Serveur de médiation et jonction SIP.**     Notez que sur le site central B, le serveur de médiation n’est pas colocalisé avec les serveurs frontaux. Cela est dû au fait que le serveur de médiation autonome est recommandé pour les sites qui utilisent la jonction SIP. Dans la plupart des autres cas, nous vous recommandons d’utiliser le serveur de médiation colocaliser avec un serveur frontal. Pour plus d’informations sur les topologies de serveur de médiation, voir [composants et topologies pour le serveur de médiation dans Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

  - La **conversation permanente est déployée.**     Cette organisation a déployé les serveurs nécessaires à l’activation de la conversation permanente. Il a déployé plusieurs serveurs frontaux de conversation permanente afin de gérer la charge pour le nombre d’utilisateurs dans le pool et de fournir une haute disponibilité. Elle a également déployé la conformité pour la conversation permanente et a localisé le magasin de conversation permanente et le magasin de conformité de la conversation permanente sur des serveurs distincts. Ces magasins peuvent être colocalisés, et peuvent même être colocalisés avec le serveur principal, mais cette organisation a choisi de les séparer afin d’offrir de meilleures performances.

  - **Équilibrage de la charge DNS.**     Le pool frontal et le pool de serveurs Edge,. Cela élimine le besoin d’équilibreurs de charge matérielle pour l’interface interne des serveurs Edge et réduit considérablement le temps que vous devez consacrer à la configuration et à la maintenance des programmes d’équilibrage de la charge matérielle pour les autres pools, car les programmes d’équilibrage de la charge matérielle sont nécessaires uniquement pour le trafic HTTP. Pour plus d’informations sur l’équilibrage de la charge DNS, voir [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

  - **Déploiement de la messagerie unifiée Exchange.**    Lync Server fonctionne avec les déploiements *locaux* de la messagerie unifiée Exchange et de la messagerie unifiée Exchange *hébergée* . Le site central A comprend un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server, et non Lync Server. La fonctionnalité de messagerie unifiée Exchange pour Lync Server s’exécute sur le pool frontal.
    
    Le site central B utilise Exchange hébergé, de sorte que la fonctionnalité de serveur de messagerie unifiée Exchange est également hébergée.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, consultez la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et l' [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.**   Nous vous recommandons de déployer une batterie de serveurs Office Web Apps Server ou Office Web Apps Server dans toutes les organisations qui utilisent la conférence Web. Vous pouvez déployer une seule batterie Office Web Apps Server dans un site qui sert le trafic à partir de tous les sites, ou le déployer dans chaque site. Office Web Apps Server permet de présenter des diapositives PowerPoint dans des conférences Web. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Des **directeurs peuvent être ajoutés.**    Si cette organisation souhaitait renforcer la sécurité contre les attaques par déni de service, elle peut également déployer un pool de directeurs. Un directeur est un rôle de serveur distinct et facultatif dans Lync Server qui n’utilise pas de comptes d’utilisateurs personnels, ou fournit des services de présence ou de conférence. Il sert de serveur de tronçon suivant interne vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les requêtes entrantes et les redirige vers le serveur ou le pool d’accueil de l’utilisateur. La pré-authentification au niveau du directeur permet de supprimer les demandes des comptes d’utilisateur inconnus du déploiement. Un directeur aide à isoler les serveurs frontaux du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé avec du trafic externe non valide lors d’une attaque de ce type, le trafic se termine au niveau du directeur.

  - **System Center Operations Manager est déployé.**    Nous vous recommandons de surveiller l’état de votre déploiement Lync Server afin de garantir la disponibilité des services pour les utilisateurs finaux. Vous pouvez surveiller Lync avec le pack d’administration System Center Operations Manager pour Lync, disponible gratuitement auprès de Microsoft. Avec le pack d’administration Lync, vous pouvez activer de manière proactive des alertes en temps réel lorsque des problèmes surviennent, exécuter des transactions synthétiques pour tester les fonctionnalités Lync de bout en bout, obtenir des rapports sur la disponibilité des services, etc. Cela vous permet de répondre de manière proactive aux problèmes de votre déploiement avant que les utilisateurs finaux ne les connaissent.
    
    Cette organisation a déployé un serveur System Center Operations Manager dans chaque site central.

</div>

<span> </span>

</div>

</div>

</div>

