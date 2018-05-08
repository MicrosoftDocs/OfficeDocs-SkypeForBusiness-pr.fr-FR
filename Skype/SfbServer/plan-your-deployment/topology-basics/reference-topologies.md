---
title: Topologies de référence pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologies de référence pour Skype pour Business Server, notamment des diagrammes et des décisions à prendre grandes et moyennes et les petites entreprises.
ms.openlocfilehash: 006f83b51eed18e008badc00fba88e4d4c3d436a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="reference-topologies-for-skype-for-business-server-2015"></a>Topologies de référence pour Skype Entreprise Server 2015
 
Topologies de référence pour Skype pour Business Server, notamment des diagrammes et des décisions à prendre grandes et moyennes et les petites entreprises.
  
La meilleure Skype pour la topologie de serveur d’entreprise pour vous dépend de la taille de votre organisation, les charges de travail que vous souhaitez déployer et vos préférences pour une haute disponibilité et coût d’investissement. 
  
Cette section décrit les trois exemples de topologie de référence, ainsi que les raisons conduisant généralement à choisir une topologie plutôt qu’une autre.
  
## <a name="reference-topology-for-a-small-organization"></a>Topologie de référence pour une petite organisation

La topologie de référence pour les petites organisations montre comment vous pouvez déployer une solution fiable, hautement disponible en déployant uniquement trois serveurs exécutant Skype pour Business Server.
  
**Topologie de référence pour les petites organisations**

![Diagramme de topologie de référence déployant trois serveurs](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)
  
- **Paire de serveurs Standard Edition Server déployé** Cette organisation a 4 000 utilisateurs sur leur site central. Ils ont déployé deux serveurs Standard Edition Server et d'entre eux pour permettre une haute disponibilité et récupération d’urgence. Chaque serveur héberge 2 000 utilisateurs, mais les informations concernant tous les utilisateurs sont synchronisées entre les deux serveurs. Si l’un des serveurs ne fonctionne pas, un administrateur peut faire basculer les utilisateurs sur l’autre serveur, avec une perturbation minime. Pour plus d’informations sur la haute disponibilité et de fonctionnalités de récupération d’urgence dans Skype pour Business Server, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
- **Le déploiement d’un serveur Edge est recommandé.** Même si n’est pas nécessaire de déployer un serveur Edge pour la messagerie instantanée interne ainsi que pour les fonctionnalités de présence et de conférence, nous recommandons de le faire même pour des petits déploiements. Vous pouvez optimiser votre Skype pour investissement Business Server en déployant un serveur de périphérie pour fournir un service aux utilisateurs actuellement à l’extérieur des pare-feu de votre organisation. Les avantages sont les suivants :
    
  - Vos utilisateurs de l’organisation peuvent utiliser Skype pour la fonctionnalité Business Server, qu’ils travaillent depuis leur domicile ou qui sont en déplacement.
    
  - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
  - Si vous avez un partenaire, le fournisseur ou l’organisation du client qui utilise également Skype pour Business Server, vous pouvez de former une relation fédérée avec cette organisation. Votre Skype pour le déploiement de Business Server serait puis reconnaît les utilisateurs de cette organisation fédérée, conduisant à une meilleure collaboration.
    
  - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics.
    
- **Survivabilité du site de succursale.** Cette organisation exécute un programme pilote de la fonctionnalité voix entreprise de Skype pour Business Server. Certains utilisateurs utilisent Skype pour Business Server en tant que leur solution vocale unique. Certains de ces utilisateurs pilotes Enterprise Voice sont situés sur le site de succursale. Le site de succursale ne dispose pas une liaison réseau (étendu WAN) fiable vers le site central, un Survivable Branch Appliance est déployé il. Ainsi, si la liaison de réseau étendu ne fonctionne pas, les utilisateurs sur le site de la succursale peuvent continuer à passer et à recevoir des appels (au sein de l’organisation et des appels RTC), à utiliser leur messagerie vocale et à communiquer par le biais de la messagerie instantanée à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison de réseau étendu n’est plus disponible. Pour plus d’informations, voir [Plan for Enterprise Voice resiliency dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur de messagerie unifiée Exchange (MU), qui exécute Microsoft Exchange Server, pas Skype pour Business Server.
    
- **Office Web Apps Server.**   Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.
    
## <a name="reference-topology-for-a-medium-organization"></a>Topologie de référence pour une organisation de taille moyenne

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte présentée dans le diagramme suivant est destinée à une organisation de 20 000 utilisateurs. 
  
**Topologie de référence pour les organisations de taille moyennes**

![Diagramme de topologie de référence pour un seul centre de données](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)
  
- **Augmentez le nombre d’utilisateurs pris en charge en ajoutant des serveurs frontaux supplémentaires.** La topologie exacte présentée dans ce diagramme inclut trois serveurs frontaux pour prendre en charge jusqu’à 20 000 utilisateurs. Si vous avez un seul site central et des utilisateurs supplémentaires, vous pouvez simplement ajouter davantage de serveurs frontaux dans le pool. Le nombre maximal d’utilisateurs par pool est 80 000, avec douze serveurs frontaux.
    
    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site. 
    
- **La récupération d’urgence peut être ajoutée.** Pour cette organisation, une haute disponibilité pour leur Skype pour les services Business Server est une fonctionnalité nécessaire, mais n’est pas la récupération d’urgence. Le pool de serveurs frontaux qu’ils ont déployés fournit une haute disponibilité.
    
    Pour disposer d’une fonctionnalité de récupération d’urgence, cette organisation peut établir un autre centre de données et ajouter un autre pool frontal, en le couplant au pool frontal du centre de données actuel. Si une catastrophe devait affecter le pool principal, les administrateurs pourraient effectuer un basculement des utilisateurs vers le pool de sauvegarde.
    
- **Serveurs principaux sont mis en miroir** Pour fournir la plus haute disponibilité pour les fonctionnalités de l’utilisateur de base, l’organisation a déployé une paire en miroir des serveurs principaux pour chaque pool frontal.
    
- **Options de base de données du serveur de surveillance.** Cette organisation a déployé surveillance pour garantir la qualité des appels Enterprise Voice et A / vidéoconférences. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est colocalisée avec les serveurs principaux. Nous prenons également en charge les topologies dans lesquelles la base de données de surveillance est située sur un serveur distinct.
    
- **Haute disponibilité des serveurs Edge** Dans cet exemple d’entreprise avec 20 000 utilisateurs, un serveur de périphérie serait suffisant pour les performances. Cependant, un pool de deux serveurs Edge a été déployé afin de fournir une haute disponibilité.
    
- **Options de déploiement de site de succursale.** L’organisation dans cette topologie est déployé en tant que leur solution voix Enterprise Voice. Site de succursale 1 ne dispose pas d’une liaison réseau (étendu WAN) résistantes vers le site central, elle a un Survivable Branch Appliance est déployé pour gérer de que nombreuses Skype pour les fonctionnalités de Business Server au cas où la liaison WAN vers le site central tombe en panne. Site de succursale 2 a toutefois une liaison réseau étendu résistante, donc uniquement un téléphone réseau commuté (RTC) passerelle est nécessaire. La passerelle PSTN déployée il prend en charge le contournement de média est donc aucun serveur de médiation sur Site de succursale 2. Pour plus d’informations, voir [Plan for Enterprise Voice resiliency dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Équilibrage de charge DNS.** Le pool frontal et le pool de serveurs Edge disposent d’un équilibrage de charge DNS pour le trafic SIP. Cela vous évite de devoir recourir à un appareil d’équilibrage de charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des appareils d’équilibrage de charge pour les autres pools, car les appareils d’équilibrage de charge sont uniquement nécessaires pour le trafic HTTP. Pour plus d’informations, consultez la rubrique (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).
    
- **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur de messagerie unifiée Exchange (MU), qui exécute Microsoft Exchange Server, pas Skype pour Business Server.
    
- **Office Web Apps Server.**    Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.
    
- **Des directeurs peuvent être ajoutés.** Si cette organisation veut accroître la sécurité face aux attaques par déni de service, elle peut également déployer un pool directeur. Un directeur est un rôle de serveur facultatif distinct dans Skype pour Business Server qui n’héberge des comptes d’utilisateurs, ou fournir des services de présence et de conférence. Il constitue un serveur interne du tronçon suivant vers lequel un serveur de périphérie achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie au préalable les demandes entrantes et les redirige vers le pool d’accueil ou le serveur de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur, vous aide à isoler les serveurs frontaux du trafic malveillant, telles que les attaques par déni de service (DoS). Si le réseau est réparti avec le trafic externe non valide dans ce type d’attaque, le trafic se termine sur le directeur.
    
- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller l’intégrité de votre Skype pour le déploiement de serveur d’entreprise afin de garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez utiliser le Pack de gestion de System Center Operations Manager pour Skype pour les entreprises qui est disponible en téléchargement gratuit de Microsoft. Avec Skype pour le Pack d’administration Business, vous obtiendrez proactive des alertes en temps réel lorsque des problèmes se produisent, exécution des transactions synthétiques pour tester Skype de bout en bout pour les fonctionnalités d’entreprise, obtenir des rapports de disponibilité du service et ainsi de suite. Cela vous aide à répondre de manière proactive aux problèmes rencontrés avec votre déploiement avant de les rencontrent des utilisateurs finaux.
    
## <a name="reference-topology-for-a-large-organization"></a>Topologie de référence pour une grande organisation

La prise en charge de la topologie de référence pour une grande organisation disposant de multiples centres de données est conçue pour toute taille d’entreprise dotée de plusieurs sites centraux. La topologie exacte du diagramme suivant est prévue pour une organisation comportant 50 000 utilisateurs, dont 20 000 sur le site central A, 20 000 sur le site central B et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie illustré dans ce diagramme peut convenir à toutes les organisations, quel que soit le nombre d’utilisateurs.
  
En plus de la haute disponibilité fournie par les pools de serveurs frontaux, cette topologie ajoute la prise en charge de la récupération d’urgence. Les pools frontaux sur les Sites centraux A et B sont associées. Si l’un de ces pools ne fonctionne pas, l’administrateur peut déplacer les services pour les utilisateurs affectés vers le pool associé dans le site non affecté.
  
Cette topologie est présentée dans de nombreux diagrammes, avec tout d’abord une vue d’ensemble, suivie de vues détaillées des sites centraux.
  
**Vue d’ensemble de la topologie de référence pour les grandes organisations avec les données de plusieurs centres**

![Topologie de référence pour différents centres de données](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)
  
**Topologie de référence pour les grandes organisations : vue détaillée du Site Central A**

![Topologie 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)
  
**Topologie de référence pour les grandes organisations : vue détaillée du Site Central B**

![Topologie 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)
  
**Topologie de référence pour les grandes organisations : vue détaillée du Site Central C**

![Topologie 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)
  
- **Pools frontaux sont associés à l’activation de la récupération d’urgence.** Les pools frontaux sur le Site A et B du Site sont associés à l’autre, à prendre en charge de la récupération d’urgence. Si le pool sur un seul site échoue, l’administrateur peut basculer les utilisateurs de ce site vers le pool frontal couplé au niveau du site avec un minimum d’interruption de service pour les utilisateurs. Chacun de ces deux pools frontaux possède six serveurs, ce qui suffit pour les 40 000 utilisateurs des deux pools en cas de basculement. Pour plus d’informations, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
    
- **Serveurs principaux sont mis en miroir** Pour fournir la plus haute disponibilité pour les fonctionnalités de l’utilisateur de base, l’organisation a déployé une paire en miroir des serveurs principaux pour chaque pool frontal. Il s’agit d’une topologie facultative, et vous pouvez choisir de déployer un seul serveur principal à la place. Les groupes de mise en cluster SQL et de disponibilité AlwaysOn sont également pris en charge. Pour plus d’informations, voir [serveur principal de haute disponibilité dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
    
- **À l’aide d’un serveur Standard Edition server sur un site de succursale.** Cette organisation considère le site C comme un site de succursale car il ne dispose que de 600 employés. Cependant, les utilisateurs y organisent beaucoup de conférences A/V entre eux. Si elle a été déployée dans Skype pour Business Server comme un site de succursale, le support pour ces conférences serait exécuter sur le réseau étendu (WAN) vers et depuis un site central ayant un serveur frontal déployé. Pour éviter cette charge de bande passante potentiels, qu’ils ont installé une paire de serveurs Standard Edition de ce site, ce qui va héberger ces conférences. Et parce que les serveurs Standard Edition Server sont installés, un site central juge Skype pour Business Server par définition, il est traité en tant que telles dans le Générateur de topologie et de l’outil de planification.
    
    Un serveur Standard Edition serait suffisant ici les performances, mais l’organisation a déployé deux et d'entre eux afin de fournir une haute disponibilité en cas d’un serveur tombe en panne.
    
    Même si le site C est considéré comme un site central, vous n’avez pas besoin d’y déployer des serveurs Edge. Dans cet exemple, le site C utilisera les serveurs Edge déployés sur le site A.
    
- **Surveillance et d’archivage** Cette organisation a déployé surveillance et archivage. Lorsque vous déployez ces deux fonctionnalités, elles s’exécutent sur chaque serveur frontal. Les bases de données pour ces fonctionnalités peuvent être colocalisées avec la base de données principale ou se trouver sur un serveur distinct. Cette organisation a disposé ces bases de données sur un serveur distinct des serveurs principaux, dans le site central B. Ces bases de données reçoivent les données de surveillance et d’archivage en provenance des serveurs frontaux dans tous les sites.
    
- **Options de déploiement de site de succursale.** Cette organisation a effectivement plus de 50 sites de succursale, seuls deux d'entre eux sont indiquées dans les diagrammes détaillées. Site de succursale 1 n’a pas de lien vers le site central, afin qu’ils puissent Survivable Branch Appliances déployés pour fournir un service téléphonique au cas où la liaison WAN vers le site central tombe en panne un réseau étendu résistant. Site de succursale 2 a toutefois une liaison réseau étendu résistante, donc il a besoin d’une passerelle réseau téléphonique commuté. La passerelle PSTN déployée il prend en charge le contournement de média est donc aucun serveur de médiation sur Site de succursale 2. Pour plus d’informations sur le choix entre les éléments à installer sur un site de succursale, voir [Plan for Enterprise Voice resiliency dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Jonction SIP et serveur de médiation.** Notez que sur le site central B, le serveur de médiation n’est pas colocalisé avec les serveurs frontaux. En effet, un serveur de médiation autonome est préférable sur les sites qui utilisent une jonction SIP. Dans la plupart des autres cas, nous recommandons de colocaliser le serveur de médiation avec le serveur frontal. Pour plus d’informations sur les topologies de serveur de médiation, consultez [composants et Topologies pour le serveur de médiation](http://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) dans la documentation de planification.
    
- **La conversation permanente est déployée.** Cette organisation a déployé les serveurs nécessaires pour activer la conversation permanente. Elle a déployé plusieurs serveurs frontaux de conversation permanente afin de gérer la charge pour le nombre d’utilisateurs dans le pool et afin de procurer une haute disponibilité. Elle a également déployé la conformité pour la conversation permanente et colocalisé le magasin de conversation permanente et le magasin de conformité de conversation permanente sur des serveurs distincts. Ces magasins pourraient être colocalisés (et peuvent même être colocalisés avec le serveur principal), mais cette organisation a choisi de les séparer pour des raisons de performances.
    
- **Équilibrage de la charge DNS.** Le pool frontal et le pool de serveur Edge ont un équilibrage de la charge DNS. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge matérielle pour l’interface interne des serveurs Edge et cela réduit significativement le temps consacré à leur configuration et maintenance pour les autres pools, étant donné que ces programmes sont requis uniquement pour le trafic HTTP. Pour plus d’informations, consultez la rubrique (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).
    
- **Déploiement de la messagerie unifiée Exchange.** Skype pour Business Server fonctionne avec des déploiements de site bothon de messagerie unifiée Exchange andhosted de messagerie unifiée Exchange (MU). Site Central A inclut un serveur de messagerie unifiée Exchange (MU), qui exécute Microsoft Exchange Server, pas Skype pour Business Server. La fonctionnalité de messagerie unifiée Exchange pour Skype pour Business Server s’exécute sur le pool frontal.
    
    Le site central B utilise la version Exchange hébergée, de sorte que la fonctionnalité du serveur de messagerie unifiée Exchange l’est également. 
    
    Pour plus d’informations sur la messagerie unifiée Exchange, voir [On-Premises Exchange Unified Messaging Integration](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) et [Hosted Exchange Unified Messaging Integration](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) dans la documentation de planification.
    
- **Office Web Apps Server.** Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Vous pourriez déployer une batterie Office Web Apps Server unique dans un site qui sert le trafic en provenance de tous les sites ou le déploiement de chaque site. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web. 
    
- **Des directeurs pourraient être ajoutés.** Si cette organisation souhaitait augmenter la sécurité contre les attaques par déni de service, elle pourrait également déployer un pool directeur. Un directeur est un rôle de serveur facultatif distinct dans Skype pour Business Server qui n’héberge des comptes d’utilisateurs, ou fournir des services de présence et de conférence. Il constitue un serveur interne du tronçon suivant vers lequel un serveur de périphérie achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie au préalable les demandes entrantes et les redirige vers le pool d’accueil ou le serveur de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur, vous aide à isoler les serveurs frontaux du trafic malveillant, telles que les attaques par déni de service (DoS). Si le réseau est réparti avec le trafic externe non valide dans ce type d’attaque, le trafic se termine sur le directeur.
    
- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller l’intégrité de votre Skype pour le déploiement de serveur d’entreprise afin de garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez utiliser le Pack de gestion de System Center Operations Manager pour Skype pour les entreprises qui est disponible en téléchargement gratuit de Microsoft. Avec Skype pour le Pack d’administration Business, vous obtiendrez proactive des alertes en temps réel lorsque des problèmes se produisent, exécution des transactions synthétiques pour tester Skype de bout en bout pour les fonctionnalités d’entreprise, obtenir des rapports de disponibilité du service et ainsi de suite. Cela vous aide à répondre de manière proactive aux problèmes rencontrés avec votre déploiement avant de les rencontrent des utilisateurs finaux.
    

