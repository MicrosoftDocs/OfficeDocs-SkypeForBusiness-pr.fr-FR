---
title: Topologies de référence pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologies de référence pour Skype Entreprise Server, y compris les diagrammes et les décisions à prendre pour les grandes, moyennes et petites organisations.
ms.openlocfilehash: fcc5832704e893b8b12c255cabbf66847ce9e9c1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394906"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologies de référence pour Skype Entreprise Server

Topologies de référence pour Skype Entreprise Server, y compris les diagrammes et les décisions à prendre pour les grandes, moyennes et petites organisations.

La meilleure Skype Entreprise Server topologie dépend de la taille de votre organisation, des charges de travail que vous souhaitez déployer et de vos préférences en matière de haute disponibilité et de coût d’investissement.

Cette section décrit trois exemples de topologies de référence, y compris le raisonnement à l’origine de nombreuses décisions prises en compte dans chaque topologie.

## <a name="reference-topology-for-a-small-organization"></a>Topologie de référence pour une petite organisation

La topologie de référence pour les petites organisations montre comment déployer une solution robuste et hautement disponible en déployant uniquement trois serveurs exécutant Skype Entreprise Server.

**Topologie de référence pour les petites organisations**

![Diagramme de topologie de référence déployant trois serveurs.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Deux serveurs Édition Standard déployés** cette organisation compte 4 000 utilisateurs sur leur site central. Ils ont déployé deux serveurs Édition Standard et les ont associés pour activer la haute disponibilité et la récupération d’urgence. Chaque serveur centrale 2 000 utilisateurs, mais les informations sur tous les utilisateurs sont synchronisées entre les deux serveurs. En cas de panne, un administrateur peut faire échouer ces utilisateurs pour qu’ils soient servis par l’autre serveur, avec un minimum de perturbation pour les utilisateurs. Pour plus d’informations sur les fonctionnalités de haute disponibilité et de récupération d’urgence dans Skype Entreprise Server, voir [Plan for high availability and disaster recovery in Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Le déploiement d’un serveur Edge est recommandé.** Bien qu’il ne soit pas nécessaire de déployer un serveur Edge pour la messagerie instantanée interne ainsi que pour les fonctionnalités de présence et de conférence, nous recommandons de le faire même pour des petits déploiements. Vous pouvez optimiser votre investissement Skype Entreprise Server en déployant un serveur Edge pour fournir un service aux utilisateurs actuellement en dehors des pare-feu de votre organisation. Les avantages sont les suivants :

  - Les utilisateurs de votre organisation peuvent utiliser les fonctionnalités Skype Entreprise Server, s’ils travaillent à domicile ou sont en déplacement.

  - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.

  - Si vous avez un partenaire, un fournisseur ou une organisation cliente qui utilise également Skype Entreprise Server, vous pouvez créer une relation fédérée avec cette organisation. Votre Skype Entreprise Server déploiement reconnaîtra ensuite les utilisateurs de cette organisation fédérée, ce qui améliorerait la collaboration.

  - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de certains services de messagerie instantanée publics.

- **Survivabilité du site de succursale.** Cette organisation exécute un programme pilote de la fonctionnalité Voix Entreprise de Skype Entreprise Server. Certains utilisateurs utilisent Skype Entreprise Server comme seule solution vocale. Certains de ces utilisateurs Voix Entreprise pilotes se trouvent sur le site de succursale. Le site de succursale n’ayant pas de liaison réseau large (WAN) fiable au site central, un Survivable Branch Appliance y est déployé. Avec ce déploiement, si la liaison wan est en panne, les utilisateurs du site de succursale peuvent toujours effectuer et recevoir des appels (appels au sein de l’organisation et appels PSTN), avoir des fonctionnalités de messagerie vocale et communiquer avec la messagerie instantanée à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison WAN n’est plus disponible. Pour plus d’informations, [voir Plan for Voix Entreprise resiliency in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Déploiement de la messagerie unifiée Exchange** Cette topologie de référence inclut un Exchange de messagerie unifiée, qui s’exécute Microsoft Exchange Server, et non Skype Entreprise Server.

- **Office Web Apps Server.** Nous vous recommandons de déployer une batterie Office Web Apps Server ou Office Web Apps Server dans chaque organisation qui utilise la conférence web. Office Web Apps Server permet de présenter PowerPoint diapositives dans des conférences web.

## <a name="reference-topology-for-a-medium-organization"></a>Topologie de référence pour une organisation de taille moyenne

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte dans le diagramme suivant est pour une organisation de 20 000 utilisateurs.

**Topologie de référence pour les organisations de taille moyenne**

![Topologie de référence pour un diagramme de centre de données unique.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Augmentez le nombre d’utilisateurs pris en charge en ajoutant des serveurs frontaux supplémentaires.** La topologie exacte de ce diagramme dispose de trois serveurs frontaux pour prendre en charge 20 000 utilisateurs. Si vous avez un site central unique et plus d’utilisateurs, vous pouvez simplement ajouter d’autres serveurs frontaux au pool. Le nombre maximal d’utilisateurs par pool est de 80 000, avec douze serveurs frontaux.

    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site.

- **La récupération d’urgence peut être ajoutée.** Pour cette organisation, la haute disponibilité de ses services Skype Entreprise Server est une fonctionnalité nécessaire, mais pas la récupération d’urgence. Le pool de serveurs frontux qu’ils ont déployé fournit une haute disponibilité.

    S’ils souhaitent ajouter une capacité de récupération d’urgence, ils peuvent envisager d’établir un autre centre de données et d’y ajouter un autre pool frontal et de l’jumeler avec le pool frontal dans leur centre de données actuel. Ensuite, en cas d’urgence affectant leur pool principal, les administrateurs peuvent faire échouer les utilisateurs vers le pool de sauvegarde.

- **Les serveurs back end sont en miroir** Pour fournir une plus grande disponibilité pour les fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs frontux en miroir pour chaque pool frontal.

- **Options de base de données du serveur de surveillance.** Cette organisation a déployé la surveillance pour garantir la qualité des appels Voix Entreprise et des conférences A/V. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est coquetée avec les serveurs frontux. Nous  prise en charge également les topologies dans lesquelles la base de données de surveillance se trouve sur un serveur distinct.

- **Haute disponibilité du serveur Edge** Dans cet exemple d’organisation avec 20 000 utilisateurs, un seul serveur Edge est suffisant pour les performances. Toutefois, ils ont déployé un pool de deux serveurs Edge déployés pour fournir une haute disponibilité.

- **Options de déploiement de site de succursale.** L’organisation dans cette topologie Voix Entreprise déployée en tant que solution vocale. Le site de succursale 1 ne dispose pas d’une liaison de réseau large (WAN) résiliente au site central. Il dispose donc d’un Survivable Branch Appliance déployé pour gérer de nombreuses fonctionnalités Skype Entreprise Server au cas où la liaison wan vers le site central serait en panne. Toutefois, le site de succursale 2 dispose d’une liaison wan résiliente, de sorte que seule une passerelle PSTN (réseau téléphonique commuté) est nécessaire. La passerelle PSTN déployée ici prend en charge le contournement de média, de sorte qu’aucun serveur de médiation n’est nécessaire sur le site de succursale 2. Pour plus d’informations, [voir Plan for Voix Entreprise resiliency in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Équilibrage de la charge DNS.** Le pool frontal et le pool de serveurs Edge ont un équilibrage de charge DNS pour le trafic SIP déployé. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des programmes d’équilibrage de la charge pour les autres pools, étant donné que les programmes d’équilibrage de la charge sont uniquement requis pour le trafic HTTP. Pour plus d’informations, voir [équilibrage de charge DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Déploiement de la messagerie unifiée Exchange** Cette topologie de référence inclut un Exchange de messagerie unifiée, qui s’exécute Microsoft Exchange Server, et non Skype Entreprise Server.

- **Office Web Apps Server.** Nous vous recommandons de déployer une batterie Office Web Apps Server ou Office Web Apps Server dans chaque organisation qui utilise la conférence web. Office Web Apps Server permet aux diapositives Powerpoint d’être présentées dans des conférences web.

- **Les directeurs peuvent être ajoutés.** Si cette organisation souhaitait renforcer la sécurité contre les attaques par déni de service, elle pourrait également déployer un pool de directeurs. Un directeur est un rôle serveur distinct et facultatif dans Skype Entreprise Server qui n’a pas de comptes d’utilisateurs, ni de services de présence ou de conférence. Il sert de serveur de saut suivant interne vers lequel un serveur Edge approvisionnement le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifier préalablement les demandes entrantes et les redirige vers le pool ou le serveur d’accueil de l’utilisateur. La pré-authentification auprès du directeur permet d’abandonner les demandes provenant de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant tel que les attaques par déni de service. Si le réseau est submergé par du trafic externe non valide dans une telle attaque, le trafic se termine au niveau du directeur.

- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller l’état de votre déploiement Skype Entreprise Server pour garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez utiliser le pack d System Center Operations Manager pour Skype Entreprise disponible en téléchargement gratuit à partir de Microsoft. Avec le pack d’administration Skype Entreprise, vous pouvez obtenir de manière proactive des alertes en temps réel lorsque des problèmes se produisent, exécuter des transactions synthétiques pour tester la fonctionnalité Skype Entreprise de bout en bout, obtenir des rapports sur la disponibilité du service, etc. Cela vous permet de répondre de manière proactive aux problèmes de votre déploiement avant que les utilisateurs finaux ne les utilisent.

## <a name="reference-topology-for-a-large-organization"></a>Topologie de référence pour une grande organisation

La topologie de référence pour une grande organisation avec plusieurs centres de données est prise en charge pour n’importe quelle taille d’organisation avec plusieurs sites centraux. La topologie exacte dans le diagramme suivant est pour une organisation de 50 000 utilisateurs, avec 20 000 utilisateurs sur le site central A, 20 000 sur le site central B et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie présenté dans ce diagramme peut prendre en charge les organisations avec n’importe quel nombre d’utilisateurs.

Outre la haute disponibilité fournie par les pools de serveurs frontux, cette topologie ajoute la prise en charge de la récupération d’urgence. Les pools frontux des sites centraux A et B sont associés. Si l’un de ces pools est en panne, l’administrateur peut déplacer les services des utilisateurs affectés vers le pool couplé sur le site non affecté.

Cette topologie est présentée dans plusieurs diagrammes, avec une vue d’ensemble tout d’abord suivie d’affichages détaillés des sites centraux.

**Vue d’ensemble de la topologie de référence pour les grandes organisations avec plusieurs centres de données**

![Topologie de référence pour plusieurs centres de données.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologie de référence pour les grandes organisations : vue détaillée du site central A**

![Topologie 3-2.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologie de référence pour les grandes organisations : vue détaillée du site central B**

![Topologie 3-3.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologie de référence pour les grandes organisations : vue détaillée du site central C**

![Topologie 3-4.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Les pools frontux sont associés pour activer la récupération d’urgence.** Les pools frontux du site A et du site B sont associés les uns aux autres, pour assurer la prise en charge de la récupération d’urgence. Si le pool d’un site tombe en panne, l’administrateur peut faire échouer les utilisateurs de ce site vers le pool frontal couplé sur l’autre site, avec un minimum d’interruption de service pour les utilisateurs. Chacun de ces deux pools frontaux dispose de six serveurs, ce qui est suffisant pour les 40 000 utilisateurs des deux pools en cas de failover. Pour plus d’informations, voir [Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Les serveurs back end sont en miroir** Pour fournir une plus grande disponibilité pour les fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs frontux en miroir pour chaque pool frontal. Il s’agit d’une topologie facultative, et vous pouvez choisir de déployer un serveur principal unique à la place. SQL clustering et les groupes de disponibilité AlwaysOn sont également pris en charge. Pour plus d’informations, [voir la haute disponibilité du serveur principal dans Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Utilisation Édition Standard serveur de succursale sur un site de succursale.** Cette organisation considère le site C comme un site de succursale, car il ne compte que 600 employés. Toutefois, les utilisateurs ont de nombreuses conférences A/V entre eux. S’il a été déployé dans Skype Entreprise Server en tant que site de succursale, le média de ces conférences s’exécute sur le réseau wan (wan) à partir d’un site central où un serveur frontal est déployé. Pour éviter cette charge potentielle de bande passante, ils ont installé deux serveurs Édition Standard sur ce site, qui hébergeront ces conférences. Et comme Édition Standard serveurs sont installés à cet emplacement, Skype Entreprise Server considère par définition qu’il s’agit d’un site central et qu’il est traité comme tel dans le Générateur de topologie et l’outil de planification.

    Un seul serveur Édition Standard serait suffisant pour les performances ici, mais l’organisation en a déployé deux et les a associés pour fournir une haute disponibilité en cas de panne d’un serveur.

    Bien que le site C soit considéré comme un site central, vous n’avez pas besoin d’y déployer des serveurs Edge. Dans cet exemple, le site C utilise les serveurs Edge déployés sur le site A.

- **Surveillance et archivage** Cette organisation a déployé la surveillance et l’archivage. Lorsque vous déployez la surveillance ou l’archivage, il s’exécute sur chaque serveur frontal. Les bases de données de ces fonctionnalités peuvent être coclaquées avec la base de données principale ou situées sur un serveur distinct. Cette organisation a localisé ces bases de données sur un serveur distinct des serveurs centraux, sur le site central B. Les bases de données reçoivent ici des données de surveillance et d’archivage des serveurs frontaux de tous les sites.

- **Options de déploiement de site de succursale.** En fait, cette organisation possède plus de 50 sites de succursale, dont deux seulement sont affichés dans les diagrammes détaillés. Le site de succursale 1 n’a pas de liaison de réseau wan résilient vers le site central, de sorte que les Survivable Branch Appliances sont déployés pour fournir un service téléphonique en cas de panne de la liaison wan vers le site central. Toutefois, le site de succursale 2 dispose d’une liaison réseau wan résiliente, de sorte qu’il n’a besoin que d’une passerelle de réseau téléphonique commuté (PSTN). La passerelle PSTN déployée ici prend en charge le contournement de média, de sorte qu’aucun serveur de médiation n’est nécessaire sur le site de succursale 2. Pour plus d’informations sur les choix d’installation sur un site de succursale, voir [Plan for Voix Entreprise resiliency in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Une trunking SIP et un serveur de médiation.** Notez que sur le site central B, le serveur de médiation n’est pas coqueté avec les serveurs frontux. Cela est dû au fait que le serveur de médiation autonome est recommandé pour les sites qui utilisent une trunking SIP. Dans la plupart des autres cas, nous vous recommandons de cocérer le serveur de médiation avec le serveur frontal. Pour plus d’informations sur les topologies de serveur de médiation, voir [Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server) dans la documentation de planification.

- **La conversation permanente est déployée.** Cette organisation a déployé les serveurs nécessaires pour activer la conversation permanente. Il a déployé plusieurs serveurs frontaux de conversation permanente pour gérer la charge pour le nombre d’utilisateurs dans le pool et fournir la haute disponibilité. Il a également déployé la conformité pour la conversation permanente et a localisé le magasin de conversation permanente et le magasin de conformité de conversation permanente sur des serveurs distincts. Ces magasins peuvent être cocifiés et peuvent même être cocérés avec le serveur principal, mais cette organisation a choisi de les séparer pour fournir de meilleures performances.

    > [!NOTE]
    > La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.

- **Équilibrage de la charge DNS.** Le pool frontal et le pool de serveurs Edge utilisent l’équilibrage de charge DNS. Cela élimine le besoin d’équilibreurs de la charge matérielle pour l’interface interne des serveurs Edge et réduit considérablement le temps que vous devez consacrer à la configuration et à la maintenance des équilibreurs de la charge matérielle pour les autres pools, car les équilibreurs de la charge matérielle sont nécessaires uniquement pour le trafic HTTP. Pour plus d’informations, voir (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Déploiement de la messagerie unifiée Exchange** Skype Entreprise Server fonctionne avec les déploiements locaux de la messagerie unifiée Exchange et de la messagerie unifiée hébergée Exchange messagerie unifiée. Le site central A inclut un Exchange de messagerie unifiée, qui s’exécute Microsoft Exchange Server, et non Skype Entreprise Server. La Exchange de la Skype Entreprise Server de la Skype Entreprise Server s’exécute sur le pool frontal.

    Le site central B utilise des Exchange, de sorte que la Exchange serveur de messagerie unie est également hébergée.

    Pour plus d’informations sur Exchange messagerie unifiée, voir l’intégration de la messagerie [unifiée](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) Exchange locale et l’intégration de la messagerie unifiée Exchange hébergée dans la documentation de planification.[](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)

- **Office Web Apps Server.** Nous vous recommandons de déployer une batterie Office Web Apps Server ou Office Web Apps Server dans chaque organisation qui utilise la conférence web. Vous pouvez déployer une batterie Office Web Apps Server dans un site qui sert le trafic de tous les sites, ou la déployer dans chaque site. Office Web Apps Server permet aux diapositives Powerpoint d’être présentées dans des conférences web.

- **Les directeurs peuvent être ajoutés.** Si cette organisation souhaitait renforcer la sécurité contre les attaques par déni de service, elle pourrait également déployer un pool de directeurs. Un directeur est un rôle serveur distinct et facultatif dans Skype Entreprise Server qui n’a pas de comptes d’utilisateurs, ni de services de présence ou de conférence. Il sert de serveur de saut suivant interne vers lequel un serveur Edge approvisionnement le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifier préalablement les demandes entrantes et les redirige vers le pool ou le serveur d’accueil de l’utilisateur. La pré-authentification auprès du directeur permet d’abandonner les demandes provenant de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant tel que les attaques par déni de service. Si le réseau est submergé par du trafic externe non valide dans une telle attaque, le trafic se termine au niveau du directeur.

- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller l’état de votre déploiement Skype Entreprise Server pour garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez utiliser le pack d System Center Operations Manager pour Skype Entreprise disponible en téléchargement gratuit à partir de Microsoft. Avec le pack d’administration Skype Entreprise, vous pouvez obtenir de manière proactive des alertes en temps réel lorsque des problèmes se produisent, exécuter des transactions synthétiques pour tester la fonctionnalité Skype Entreprise de bout en bout, obtenir des rapports sur la disponibilité du service, etc. Cela vous permet de répondre de manière proactive aux problèmes de votre déploiement avant que les utilisateurs finaux ne les utilisent.