---
title: Topologie de référence de Lync Server 2013 utilisée dans les grandes organisations comportant plusieurs centres de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2460378d19f8edb4e845778cacaf01c7141204c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topologie de référence de Lync Server 2013 utilisée dans les grandes organisations comportant plusieurs centres de données

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

La prise en charge de la topologie de référence pour une grande organisation disposant de multiples centres de données est conçue pour toute taille d’entreprise dotée de plusieurs sites centraux. La topologie exacte du diagramme suivant est prévue pour une organisation comportant 50 000 utilisateurs, dont 20 000 sur le site central A, 20 000 sur le site central B et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie illustré dans ce diagramme peut convenir à toutes les organisations, quel que soit le nombre d’utilisateurs.

Outre la haute disponibilité fournie par les pools de serveurs frontaux, cette topologie ajoute une prise en charge de la reprise après sinistre. Les pools front-end sur les sites centraux A et B sont associés ensemble. Si l’un de ces pools ne fonctionne pas, l’administrateur peut déplacer les services pour les utilisateurs affectés vers le pool associé dans le site non affecté.

Cette topologie est présentée dans de nombreux diagrammes, avec tout d’abord une vue d’ensemble, suivie de vues détaillées des sites centraux.

**Vue d’ensemble de la topologie de référence pour les grandes organisations disposant de plusieurs centres de données**

![Topologie de référence pour plusieurs centres de données] (images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologie de référence pour plusieurs centres de données")

**Topologie de référence pour les grandes organisations : vue détaillée du site central A**

![dab33f19-e77b-42da-9047-858fb9851264] (images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topologie de référence pour les grandes organisations : vue détaillée du site central B**

![5ccaf1d4-BD53-4cb7-96fe-723147334e7f] (images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-BD53-4cb7-96fe-723147334e7f")

**Topologie de référence pour les grandes organisations : vue détaillée du site central C**

![7238ca40-340c-491f-B497-ddc2665dadb6] (images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-B497-ddc2665dadb6")

  - **Les pools front-end sont couplés pour permettre une reprise après sinistre.**    Les pools front-end sur le site A et le site B sont associés entre eux pour fournir une prise en charge de la reprise après sinistre. Si le pool au niveau d’un site est en échec, l’administrateur peut basculer sur les utilisateurs de ce site vers le pool frontal associé sur l’autre site, avec un minimum d’interruption de service pour les utilisateurs. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Pour plus d’informations, reportez-vous à [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Les serveurs dorsaux sont mis en miroir**   pour offrir une plus grande disponibilité aux fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs dorsaux en miroir pour chaque pool frontal. Il s’agit d’une topologie facultative, et vous pouvez choisir de déployer un serveur principal unique à la place.

  - **Utiliser Standard Edition Server sur un site de succursale.**    Cette organisation considère le site C comme un site de succursale, car il est uniquement doté de 600 employés. However, the users there have many A/V conferences among themselves. S’il a été déployé dans Lync Server en tant que site de succursale, le média de ces conférences sera exécuté sur le réseau étendu (WAN) vers et à partir d’un site central sur lequel un serveur frontal est déployé. Pour éviter ce risque de charge de bande passante, une paire de serveurs Standard Edition Server est installée sur ce site, ce qui permet d’héberger ces conférences. Étant donné que les serveurs Standard Edition y sont installés, Lync Server by Definition le considère comme un site central et est considéré comme tel dans le générateur de topologie et dans l’outil de planification.
    
    Seul un serveur Standard Edition Server sera suffisant pour les performances, mais l’organisation a déployé deux et couplés pour fournir une disponibilité élevée en cas de panne d’un serveur.
    
    Même si le site C est considéré comme un site central, vous n’avez pas besoin d’y déployer des serveurs Edge. Dans cet exemple, le site C utilisera les serveurs Edge déployés sur le site A.

  - **Le fait de surveiller et d’archiver**cette organisation a déployé la surveillance et l’archivage.    Lorsque vous déployez ces deux fonctionnalités, elles s’exécutent sur chaque serveur frontal. Les bases de données pour ces fonctionnalités peuvent être colocalisées avec la base de données principale ou se trouver sur un serveur distinct. Cette organisation a disposé ces bases de données sur un serveur distinct des serveurs principaux, dans le site central B. Ces bases de données reçoivent les données de surveillance et d’archivage en provenance des serveurs frontaux dans tous les sites.

  - **Options de déploiement d’un site de succursale.**    Cette organisation a réellement plus de 50 branches, dont trois uniquement sont affichées dans les diagrammes détaillés. Les sites de succursale 1 et 3 ne disposent pas d’une liaison WAN fiable vers le site central, de sorte qu’ils disposent de périphériques succursales Survivables déployés pour fournir les services téléphoniques en cas de panne du lien WAN vers le site central. Le site de succursale 2 possède toutefois une liaison WAN résiliente, de sorte que vous n’avez besoin que d’une passerelle réseau téléphonique commuté (RTC). La passerelle RTC déployée prend en charge la fonctionnalité de contournement du contenu multimédia; donc aucun serveur d’intermédiation n’est requis pour la succursale. Pour plus d’informations sur la sélection des éléments à installer sur un site de succursale, voir [planification de la résilience vocale d’entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.

  - **Serveur de médiation et de trunking SIP.**    Notez que sur le site central B, le serveur de médiation n’est pas colocalisé avec les serveurs frontaux. En effet, un serveur de médiation autonome est préférable sur les sites qui utilisent une jonction SIP. Dans la plupart des autres cas, nous recommandons de colocaliser le serveur de médiation avec le serveur frontal. Pour plus d’informations sur les topologies du serveur de médiation, voir [composants et topologies du serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

  - **La conversation permanente est déployée.**    Cette organisation a déployé les serveurs nécessaires pour activer la conversation permanente. Elle a déployé plusieurs serveurs frontaux de conversation permanente afin de gérer la charge pour le nombre d’utilisateurs dans le pool et afin de procurer une haute disponibilité. Elle a également déployé la conformité pour la conversation permanente et colocalisé le magasin de conversation permanente et le magasin de conformité de conversation permanente sur des serveurs distincts. Ces magasins pourraient être colocalisés (et peuvent même être colocalisés avec le serveur principal), mais cette organisation a choisi de les séparer pour des raisons de performances.

  - **Équilibrage de charge DNS.**    Pool frontal et pool de serveurs Edge. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge matérielle pour l’interface interne des serveurs Edge et cela réduit significativement le temps consacré à leur configuration et maintenance pour les autres pools, étant donné que ces programmes sont requis uniquement pour le trafic HTTP. Pour plus d’informations sur l’équilibrage de charge DNS, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

  - **Déploiement d’Exchange UM.**   Lync Server fonctionne avec les déploiements *locaux* d’Exchange Unified Messaging (um) et la messagerie unifiée Exchange *hébergée* . Le site central A inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Lync Server. La fonctionnalité de messagerie unifiée Exchange pour Lync Server s’exécute sur le pool frontal.
    
    Le site central B utilise la version Exchange hébergée, de sorte que la fonctionnalité du serveur de messagerie unifiée Exchange l’est également.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, voir [planification d’une intégration de messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Serveur Office Web Apps.**   Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Vous pouvez déployer une seule batterie de serveurs Office Web Apps sur un seul site qui dessert le trafic de tous les sites, ou la déployer dans chaque site. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Les directeurs peuvent être ajoutés.**   Si cette organisation voulait renforcer la sécurité contre les attaques par déni de service, elle peut également déployer un pool de directeurs. Un directeur est un rôle de serveur distinct facultatif dans Lync Server qui n’utilise pas de compte d’utilisateur familial ou fournit des services de présence et de conférence. Il sert de serveur interne de tronçons de tronçon sur lequel un serveur de périphérie route le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le groupe de destination de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, le trafic se termine au directeur.

  - **System Center Operations Manager est déployé.**   Nous vous recommandons de surveiller l’état de votre déploiement de Lync Server pour garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez surveiller Lync avec le pack d’administration System Center Operations Manager pour Lync disponible en téléchargement gratuit depuis Microsoft. Le pack d’administration de Lync vous permet d’obtenir des alertes en temps réel en temps réel en cas de problème, d’exécuter des transactions synthétiques pour tester la fonctionnalité Lync de bout en bout, d’obtenir des rapports sur la disponibilité du service, etc. This helps you to proactively respond to issues with your deployment before end-users experience them.
    
    Cette organisation a déployé un serveur System Center Operations Manager dans chaque site central.

</div>

<span> </span>

</div>

</div>

</div>

