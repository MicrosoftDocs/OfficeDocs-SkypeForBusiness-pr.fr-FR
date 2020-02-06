---
title: Topologies de référence pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Des topologies de référence pour Skype entreprise Server, y compris des diagrammes et des décisions à prendre pour les grandes, moyennes et petites organisations.
ms.openlocfilehash: f207e69dceea4c2959e5cf81ddcf359266ed1604
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801704"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologies de référence pour Skype entreprise Server

Des topologies de référence pour Skype entreprise Server, y compris des diagrammes et des décisions à prendre pour les grandes, moyennes et petites organisations.

La meilleure topologie de serveur Skype entreprise dépend de la taille de votre organisation, des charges de travail que vous voulez déployer et de vos préférences pour le coût de votre investissement.

Cette section décrit les trois exemples de topologie de référence, ainsi que les raisons conduisant généralement à choisir une topologie plutôt qu’une autre.

## <a name="reference-topology-for-a-small-organization"></a>Topologie de référence pour une petite organisation

La topologie de référence pour les petites organisations montre comment vous pouvez déployer une solution robuste et facilement disponible en déployant uniquement trois serveurs exécutant Skype entreprise Server.

**Topologie de référence pour les petites organisations**

![Diagramme de topologie de référence déployant trois serveurs](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Paires de serveurs Standard Edition déployés** Cette organisation a des utilisateurs 4 000 sur leur site central. Ils ont déployé deux serveurs Standard Edition et couplés entre eux pour permettre une haute disponibilité et une reprise après sinistre. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Pour plus d’informations sur les fonctionnalités de haute disponibilité et de reprise après sinistre dans Skype entreprise Server, reportez-vous à la rubrique [planification de la haute disponibilité et reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Le déploiement d’un serveur Edge est recommandé.** Même si n’est pas nécessaire de déployer un serveur Edge pour la messagerie instantanée interne ainsi que pour les fonctionnalités de présence et de conférence, nous recommandons de le faire même pour des petits déploiements. Vous pouvez optimiser votre investissement dans Skype entreprise Server en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent en dehors des pare-feu de votre organisation. Les avantages sont les suivants :

  - Les utilisateurs de votre organisation peuvent utiliser la fonctionnalité de Skype entreprise Server s’ils travaillent à la maison ou en déplacement.

  - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.

  - Si un partenaire, un fournisseur ou une organisation cliente utilise également Skype entreprise Server, vous pouvez créer une relation fédérée avec cette organisation. Le déploiement de Skype entreprise Server reconnaîtrait alors les utilisateurs de cette organisation fédérée, ce qui permettra une meilleure collaboration.

  - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics.

- **Survivabilité du site de succursale.** Cette organisation exécute un programme pilote de la fonctionnalité voix entreprise de Skype entreprise Server. Certains utilisateurs utilisent Skype entreprise Server comme solution vocale unique. Certains de ces utilisateurs du pilotage de voix entreprise sont situés sur le site de la succursale. Le site de succursale ne possède pas de lien réseau étendu (WAN) fiable vers le site central ; de sorte qu’une unité de branchement survivant y est déployée. Ainsi, si la liaison de réseau étendu ne fonctionne pas, les utilisateurs sur le site de la succursale peuvent continuer à passer et à recevoir des appels (au sein de l’organisation et des appels RTC), à utiliser leur messagerie vocale et à communiquer par le biais de la messagerie instantanée à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison de réseau étendu n’est plus disponible. Pour plus d’informations, reportez-vous à [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Skype entreprise Server.

- **Office Web Apps Server.**   Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.

## <a name="reference-topology-for-a-medium-organization"></a>Topologie de référence pour une organisation de taille moyenne

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte présentée dans le diagramme suivant est destinée à une organisation de 20 000 utilisateurs.

**Topologie de référence pour des organisations de taille moyenne**

![Diagramme de topologie de référence pour un seul centre de données](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Augmentez le nombre d’utilisateurs pris en charge en ajoutant des serveurs frontaux supplémentaires.** La topologie exacte présentée dans ce diagramme inclut trois serveurs frontaux pour prendre en charge jusqu’à 20 000 utilisateurs. Si vous avez un seul site central et des utilisateurs supplémentaires, vous pouvez simplement ajouter davantage de serveurs frontaux dans le pool. Le nombre maximal d’utilisateurs par pool est 80 000, avec douze serveurs frontaux.

    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site.

- **La récupération d’urgence peut être ajoutée.** Dans le cas présent, la haute disponibilité de ses services Skype entreprise Server est une fonctionnalité requise, mais pas la reprise après sinistre. La réserve de serveurs frontaux déployés offre une disponibilité élevée.

    Pour disposer d’une fonctionnalité de récupération d’urgence, cette organisation peut établir un autre centre de données et ajouter un autre pool frontal, en le couplant au pool frontal du centre de données actuel. Si une catastrophe devait affecter le pool principal, les administrateurs pourraient effectuer un basculement des utilisateurs vers le pool de sauvegarde.

- **Les serveurs principaux sont en miroir** Pour garantir une plus grande disponibilité aux fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs dorsaux en miroir pour chaque pool frontal.

- **Options de base de données du serveur de surveillance.** Cette organisation a déployé une analyse pour garantir la qualité des appels vocaux d’entreprise et des conférences A/V. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est colocalisée avec les serveurs principaux. Nous prenons également en charge les topologies dans lesquelles la base de données de surveillance est située sur un serveur distinct.

- **Haute disponibilité du serveur Edge** Dans cet exemple d’organisation avec des utilisateurs de 20 000, un seul serveur Edge serait suffisant pour les performances. Cependant, un pool de deux serveurs Edge a été déployé afin de fournir une haute disponibilité.

- **Options de déploiement d’un site de succursale.** L’organisation de cette topologie dispose d’Enterprise Voice déployé comme solution vocale. Le site de succursale 1 ne possède pas de lien réseau étendu (WAN) sur le site central, de sorte qu’il dispose d’une unité de branchement Survivable déployée pour gérer de nombreuses fonctionnalités de Skype entreprise Server en cas de panne du lien WAN vers le site central. Le site de succursale 2 possède toutefois une liaison WAN résiliente, de sorte qu’il n’est pas nécessaire de disposer d’une passerelle RTC (réseau téléphonique commuté). La passerelle RTC déployée prend en charge la fonctionnalité de contournement du contenu multimédia ; donc aucun serveur d’intermédiation n’est requis au niveau du site de succursale 2. Pour plus d’informations, reportez-vous à [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Équilibrage de charge DNS.** Le pool frontal et le pool de serveurs Edge disposent d’un équilibrage de charge DNS pour le trafic SIP. Cela vous évite de devoir recourir à un appareil d’équilibrage de charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des appareils d’équilibrage de charge pour les autres pools, car les appareils d’équilibrage de charge sont uniquement nécessaires pour le trafic HTTP. Pour plus d’informations, voir [équilibrage de charge DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Skype entreprise Server.

- **Office Web Apps Server.**    Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.

- **Des directeurs peuvent être ajoutés.** Si cette organisation veut accroître la sécurité face aux attaques par déni de service, elle peut également déployer un pool directeur. Un directeur est un rôle de serveur distinct et facultatif dans Skype entreprise Server qui ne prend pas en charge les comptes d’utilisateurs privés ou qui fournissent des services de présence ou de conférence. Il sert de serveur interne de tronçons de tronçon sur lequel un serveur de périphérie route le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le groupe de destination de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, le trafic se termine au directeur.

- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller l’état de votre déploiement de Skype entreprise Server afin de garantir la disponibilité des services pour les utilisateurs finaux. Vous pouvez utiliser le pack d’administration System Center Operations Manager pour Skype entreprise disponible en téléchargement gratuit depuis Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.

## <a name="reference-topology-for-a-large-organization"></a>Topologie de référence pour une grande organisation

La prise en charge de la topologie de référence pour une grande organisation disposant de multiples centres de données est conçue pour toute taille d’entreprise dotée de plusieurs sites centraux. La topologie exacte du diagramme suivant est prévue pour une organisation comportant 50 000 utilisateurs, dont 20 000 sur le site central A, 20 000 sur le site central B et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie illustré dans ce diagramme peut convenir à toutes les organisations, quel que soit le nombre d’utilisateurs.

Outre la haute disponibilité fournie par les pools de serveurs frontaux, cette topologie ajoute une prise en charge de la reprise après sinistre. Les pools front-end sur les sites centraux A et B sont associés ensemble. Si l’un de ces pools ne fonctionne pas, l’administrateur peut déplacer les services pour les utilisateurs affectés vers le pool associé dans le site non affecté.

Cette topologie est présentée dans de nombreux diagrammes, avec tout d’abord une vue d’ensemble, suivie de vues détaillées des sites centraux.

**Vue d’ensemble de la topologie de référence pour les grandes organisations disposant de plusieurs centres de données**

![Topologie de référence pour différents centres de données](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologie de référence pour les grandes organisations : vue détaillée du site central A**

![Topologie 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologie de référence pour les grandes organisations : vue détaillée du site central B**

![Topologie 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologie de référence pour les grandes organisations : vue détaillée du site central C**

![Topologie 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Les pools front-end sont couplés pour permettre une reprise après sinistre.** Les pools front-end sur le site A et le site B sont associés entre eux pour fournir une prise en charge de la reprise après sinistre. Si le pool au niveau d’un site est en échec, l’administrateur peut basculer sur les utilisateurs de ce site vers le pool frontal associé sur l’autre site, avec un minimum d’interruption de service pour les utilisateurs. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Pour plus d’informations, reportez-vous à la rubrique [planification de la haute disponibilité et reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Les serveurs principaux sont en miroir** Pour garantir une plus grande disponibilité aux fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs dorsaux en miroir pour chaque pool frontal. Il s’agit d’une topologie facultative, et vous pouvez choisir de déployer un serveur principal unique à la place. SQL clustering and AlwaysOn Availability groups are also supported. For more information, see [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Utiliser Standard Edition Server sur un site de succursale.** This organization considers Site C as a branch site because it has only 600 employees. However, the users there have many A/V conferences among themselves. S’il a été déployé dans Skype entreprise Server en tant que site de succursale, le média de ces conférences sera exécuté sur le réseau étendu (WAN) vers et à partir d’un site central sur lequel un serveur frontal est déployé. Pour éviter ce risque de charge de bande passante, une paire de serveurs Standard Edition Server est installée sur ce site, ce qui permet d’héberger ces conférences. Les serveurs Standard Edition étant installés à partir de cet emplacement, Skype entreprise Server par définition le considère comme un site central et est considéré comme tel dans le générateur de topologie et dans l’outil de planification.

    Seul un serveur Standard Edition Server sera suffisant pour les performances, mais l’organisation a déployé deux et couplés pour fournir une disponibilité élevée en cas de panne d’un serveur.

    Même si le site C est considéré comme un site central, vous n’avez pas besoin d’y déployer des serveurs Edge. Dans cet exemple, le site C utilisera les serveurs Edge déployés sur le site A.

- **Surveillance et archivage** Cette organisation a déployé la surveillance et l’archivage. Lorsque vous déployez ces deux fonctionnalités, elles s’exécutent sur chaque serveur frontal. Les bases de données pour ces fonctionnalités peuvent être colocalisées avec la base de données principale ou se trouver sur un serveur distinct. Cette organisation a disposé ces bases de données sur un serveur distinct des serveurs principaux, dans le site central B. Ces bases de données reçoivent les données de surveillance et d’archivage en provenance des serveurs frontaux dans tous les sites.

- **Options de déploiement d’un site de succursale.** Cette organisation possède en fait plus de 50 sites de succursales, dont deux seulement apparaissent dans les diagrammes détaillés. Le site de succursale 1 ne possède pas de lien réseau étendu fiable vers le site central, de sorte qu’il dispose d’appareils branches Survivables déployés pour fournir les services téléphoniques en cas de panne du lien WAN vers le site central. Le site de succursale 2 possède toutefois une liaison WAN résiliente, il n’y a donc qu’une passerelle RTC (réseau téléphonique commuté). La passerelle RTC déployée prend en charge la fonctionnalité de contournement du contenu multimédia ; donc aucun serveur d’intermédiation n’est requis au niveau du site de succursale 2. Pour plus d’informations sur la sélection des éléments à installer sur un site de succursale, voir [planifier la résilience vocale d’entreprise dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Jonction SIP et serveur de médiation.** Notez que sur le site central B, le serveur de médiation n’est pas colocalisé avec les serveurs frontaux. En effet, un serveur de médiation autonome est préférable sur les sites qui utilisent une jonction SIP. Dans la plupart des autres cas, nous recommandons de colocaliser le serveur de médiation avec le serveur frontal. Pour plus d’informations sur les topologies de serveur de médiation, reportez-vous à [Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) dans la documentation de planification.

- **La conversation permanente est déployée.** Cette organisation a déployé les serveurs nécessaires pour activer la conversation permanente. Elle a déployé plusieurs serveurs frontaux de conversation permanente afin de gérer la charge pour le nombre d’utilisateurs dans le pool et afin de procurer une haute disponibilité. Elle a également déployé la conformité pour la conversation permanente et colocalisé le magasin de conversation permanente et le magasin de conformité de conversation permanente sur des serveurs distincts. Ces magasins pourraient être colocalisés (et peuvent même être colocalisés avec le serveur principal), mais cette organisation a choisi de les séparer pour des raisons de performances.

    > [!NOTE]
    > La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.

- **Équilibrage de la charge DNS.** Le pool frontal et le pool de serveur Edge ont un équilibrage de la charge DNS. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge matérielle pour l’interface interne des serveurs Edge et cela réduit significativement le temps consacré à leur configuration et maintenance pour les autres pools, étant donné que ces programmes sont requis uniquement pour le trafic HTTP. Pour plus d’informations, voir (.. /.. /plan-Your-Deployment/Network-Requirements/Load-Balancing.MD # BKMK_DNSLoadBalancing).

- **Déploiement de la messagerie unifiée Exchange.** Skype entreprise Server fonctionne avec les déploiements locaux d’Exchange Unified Messaging (UM) et de messagerie unifiée Exchange hébergée. Le site central A inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Skype entreprise Server. La fonctionnalité de messagerie unifiée Exchange pour Skype entreprise Server s’exécute sur le pool frontal.

    Le site central B utilise la version Exchange hébergée, de sorte que la fonctionnalité du serveur de messagerie unifiée Exchange l’est également.

    Pour plus d’informations sur la messagerie unifiée Exchange, voir intégration de la [messagerie unifiée Exchange locale](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) et intégration de la [messagerie unifiée Exchange hébergée](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) dans la documentation de planification.

- **Office Web Apps Server.** Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Vous pouvez déployer une seule batterie de serveurs Office Web Apps sur un seul site qui dessert le trafic de tous les sites, ou la déployer dans chaque site. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.

- **Des directeurs pourraient être ajoutés.** Si cette organisation souhaitait augmenter la sécurité contre les attaques par déni de service, elle pourrait également déployer un pool directeur. Un directeur est un rôle de serveur distinct et facultatif dans Skype entreprise Server qui ne prend pas en charge les comptes d’utilisateurs privés ou qui fournissent des services de présence ou de conférence. Il sert de serveur interne de tronçons de tronçon sur lequel un serveur de périphérie route le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le groupe de destination de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, le trafic se termine au directeur.

- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller l’état de votre déploiement de Skype entreprise Server afin de garantir la disponibilité des services pour les utilisateurs finaux. Vous pouvez utiliser le pack d’administration System Center Operations Manager pour Skype entreprise disponible en téléchargement gratuit depuis Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.


