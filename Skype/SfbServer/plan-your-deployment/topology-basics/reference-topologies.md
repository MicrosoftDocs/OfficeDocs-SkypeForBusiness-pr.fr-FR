---
title: Topologies de référence pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologies de référence pour Skype pour Business Server, y compris les diagrammes et les décisions à prendre pour les grandes, moyennes et les petites entreprises.
ms.openlocfilehash: 5019e292344dfe20ee086ff6ceb86c11aeeee944
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="reference-topologies-for-skype-for-business-server-2015"></a>Topologies de référence pour Skype Entreprise Server 2015
 
Topologies de référence pour Skype pour Business Server, y compris les diagrammes et les décisions à prendre pour les grandes, moyennes et les petites entreprises.
  
La meilleure Skype pour la topologie de serveur d’entreprise pour vous dépend de la taille de votre entreprise, les charges de travail que vous souhaitez déployer et vos préférences pour la haute disponibilité par rapport au coût de l’investissement. 
  
Cette section décrit les trois exemples de topologie de référence, ainsi que les raisons conduisant généralement à choisir une topologie plutôt qu’une autre.
  
## <a name="reference-topology-for-a-small-organization"></a>Topologie de référence pour une petite organisation

La topologie de référence pour les petites organisations montre comment déployer une solution robuste et hautement disponible en déployant uniquement trois serveurs exécutant Skype pour Business Server.
  
**Topologie de référence pour les petites entreprises**

![Diagramme de topologie de référence déployant trois serveurs](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)
  
- **Paire de serveurs Standard Edition Server déployé** Cette organisation compte 4000 utilisateurs sur leur site central. Ils ont déployé des deux serveurs Standard Edition et associé les regrouper ensemble pour activer la haute disponibilité et reprise après sinistre. Chaque serveur héberge 2 000 utilisateurs, mais les informations concernant tous les utilisateurs sont synchronisées entre les deux serveurs. Si l’un des serveurs ne fonctionne pas, un administrateur peut faire basculer les utilisateurs sur l’autre serveur, avec une perturbation minime. Pour plus d’informations sur la disponibilité élevée et des fonctions de reprise après sinistre dans Skype pour Business Server, reportez-vous à [planification pour haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
- **Le déploiement d’un serveur Edge est recommandé.** Même si n’est pas nécessaire de déployer un serveur Edge pour la messagerie instantanée interne ainsi que pour les fonctionnalités de présence et de conférence, nous recommandons de le faire même pour des petits déploiements. Vous pouvez optimiser votre Skype pour le placement de serveur d’entreprise en déployant un serveur de transport Edge pour fournir un service aux utilisateurs actuellement à l’extérieur des pare-feu de votre organisation. Les avantages sont les suivants :
    
  - Vos utilisateurs de l’organisation peuvent utiliser Skype pour la fonctionnalité de serveur de l’entreprise, s’ils travaillent à leur domicile ou qui sont en déplacement.
    
  - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
  - Si vous avez un partenaire, le fournisseur ou l’organisation du client qui utilise également Skype pour Business Server, vous pouvez créer une relation fédérée à cette organisation. Votre Skype pour le déploiement du serveur de l’entreprise serait ainsi reconnaître les utilisateurs de cette organisation fédérée, conduisant à une meilleure collaboration.
    
  - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics.
    
- **Survivabilité du site de succursale.** Cette organisation exécute un programme pilote de la fonctionnalité Voix Entreprise de Skype pour Business Server. Certains utilisateurs sont à l’aide de Skype pour Business Server en tant que leur solution vocale unique. Certains de ces utilisateurs pilotes Voix Entreprise se trouvent sur le site de la succursale. Le site de la succursale n’a pas une liaison réseau (étendu WAN) fiable vers le site central, un programme Survivable Branch Appliance est déployée il. Ainsi, si la liaison de réseau étendu ne fonctionne pas, les utilisateurs sur le site de la succursale peuvent continuer à passer et à recevoir des appels (au sein de l’organisation et des appels RTC), à utiliser leur messagerie vocale et à communiquer par le biais de la messagerie instantanée à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison de réseau étendu n’est plus disponible. Pour plus d’informations, consultez [planification de résilience de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur de messagerie unifiée Exchange (MU), qui exécute Microsoft Exchange Server, pas Skype pour Business Server.
    
- **Office Web Apps Server.**  Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.
    
## <a name="reference-topology-for-a-medium-organization"></a>Topologie de référence pour une organisation de taille moyenne

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte présentée dans le diagramme suivant est destinée à une organisation de 20 000 utilisateurs. 
  
**Topologie de référence pour les entreprises de taille moyennes**

![Diagramme de topologie de référence pour un seul centre de données](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)
  
- **Augmentez le nombre d’utilisateurs pris en charge en ajoutant des serveurs frontaux supplémentaires.** La topologie exacte présentée dans ce diagramme inclut trois serveurs frontaux pour prendre en charge jusqu’à 20 000 utilisateurs. Si vous avez un seul site central et des utilisateurs supplémentaires, vous pouvez simplement ajouter davantage de serveurs frontaux dans le pool. Le nombre maximal d’utilisateurs par pool est 80 000, avec douze serveurs frontaux.
    
    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site. 
    
- **La récupération d’urgence peut être ajoutée.** Pour cette organisation, haute disponibilité pour leur Skype pour les services de serveur d’entreprise est nécessaire, mais n’est pas reprise après sinistre. Le pool des serveurs frontaux qu’ils ont déployés fournit une disponibilité élevée.
    
    Pour disposer d’une fonctionnalité de récupération d’urgence, cette organisation peut établir un autre centre de données et ajouter un autre pool frontal, en le couplant au pool frontal du centre de données actuel. Si une catastrophe devait affecter le pool principal, les administrateurs pourraient effectuer un basculement des utilisateurs vers le pool de sauvegarde.
    
- **Sauvegarder les serveurs principaux sont mis en miroir.** Pour fournir une disponibilité plus élevée pour les fonctionnalités de l’utilisateur de base, l’organisation a déployé une paire en miroir, de sauvegarder les serveurs principaux pour chaque pool frontal.
    
- **Options de base de données du serveur de surveillance.** Cette organisation a déployé de surveillance afin de garantir la qualité des appels de Voix Entreprise et A / vidéoconférences. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est colocalisée avec les serveurs principaux. Nous prenons également en charge les topologies dans lesquelles la base de données de surveillance est située sur un serveur distinct.
    
- **Haute disponibilité du serveur de transport Edge** Dans cet exemple d’entreprise avec 20 000 utilisateurs, un serveur de transport Edge serait suffisant pour les performances. Cependant, un pool de deux serveurs Edge a été déployé afin de fournir une haute disponibilité.
    
- **Options de déploiement du site de succursale.** L’organisation dans cette topologie a de Voix Entreprise déployé en tant que leur solution vocale. 1 Site de la succursale n’a pas une liaison de réseau (étendu WAN) résilient étendu vers le site central, elle a un Survivable Branch Appliance déployés pour mettre à jour les que nombreux Skype pour les fonctionnalités de serveur d’entreprise dans le cas où la liaison WAN vers le site central tombe en panne. Site de la succursale 2 a cependant une liaison WAN robuste, donc uniquement un public commuté switched telephone network (PSTN) passerelle est requise. La passerelle RTC déployée il prend en charge le contournement de média, aucun serveur de médiation n’est nécessaire au niveau de la succursale Site 2. Pour plus d’informations, consultez [planification de résilience de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Équilibrage de charge DNS.** Le pool frontal et le pool de serveurs Edge disposent d’un équilibrage de charge DNS pour le trafic SIP. Cela vous évite de devoir recourir à un appareil d’équilibrage de charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des appareils d’équilibrage de charge pour les autres pools, car les appareils d’équilibrage de charge sont uniquement nécessaires pour le trafic HTTP. Pour plus d’informations, consultez (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).
    
- **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur de messagerie unifiée Exchange (MU), qui exécute Microsoft Exchange Server, pas Skype pour Business Server.
    
- **Office Web Apps Server.**   Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web.
    
- **Des directeurs peuvent être ajoutés.** Si cette organisation veut accroître la sécurité face aux attaques par déni de service, elle peut également déployer un pool directeur. Un directeur est un rôle de serveur distinct, facultatif dans Skype pour Business Server qui ne pas les comptes d’utilisateurs à domicile, ou fournir des services de présence ou de conférence. Il sert un serveur interne du tronçon suivant vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur des authentifie les requêtes entrantes et les redirige vers le serveur ou le pool de domicile de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant comme les attaques de déni de service (DoS). Si le réseau est inondé de trafic d’externe non valide dans ce type d’attaque, le trafic se termine sur le directeur.
    
- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller la santé de votre Skype pour le déploiement du serveur de l’entreprise afin de garantir la disponibilité de service pour les utilisateurs finaux. Vous pouvez utiliser le Management Pack System Center Operations Manager pour Skype pour entreprise qui est disponible en téléchargement gratuit à partir de Microsoft. Avec le Skype pour le Pack de gestion d’entreprise, vous pouvez par anticipation obtenir des alertes en temps réel lorsque des problèmes se produisent, exécuter les transactions synthétiques pour tester Skype de bout en bout pour les fonctionnalités d’entreprise, obtenir des rapports de disponibilité des services et ainsi de suite. Cela vous aide à répondre de manière proactive aux problèmes de votre déploiement avant de rencontrer les utilisateurs finaux.
    
## <a name="reference-topology-for-a-large-organization"></a>Topologie de référence pour une grande organisation

La prise en charge de la topologie de référence pour une grande organisation disposant de multiples centres de données est conçue pour toute taille d’entreprise dotée de plusieurs sites centraux. La topologie exacte du diagramme suivant est prévue pour une organisation comportant 50 000 utilisateurs, dont 20 000 sur le site central A, 20 000 sur le site central B et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie illustré dans ce diagramme peut convenir à toutes les organisations, quel que soit le nombre d’utilisateurs.
  
En plus de la disponibilité élevée fournie par les pools de serveurs frontaux, cette topologie ajoute la prise en charge de la récupération après sinistre. Les pools de Front-End sur les Sites centraux, A et B sont associés entre eux. Si l’un de ces pools ne fonctionne pas, l’administrateur peut déplacer les services pour les utilisateurs affectés vers le pool associé dans le site non affecté.
  
Cette topologie est présentée dans de nombreux diagrammes, avec tout d’abord une vue d’ensemble, suivie de vues détaillées des sites centraux.
  
**Vue d’ensemble de la topologie de référence pour les grandes entreprises avec des données de plusieurs postes de charge**

![Topologie de référence pour différents centres de données](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)
  
**Topologie de référence pour les grandes entreprises : détaillées de Site Central A**

![Topologie 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)
  
**Topologie de référence pour les grandes entreprises : détaillées de B de Site Central**

![Topologie 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)
  
**Topologie de référence pour les grandes entreprises : détaillées de Site Central, C**

![Topologie 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)
  
- **Les pools de fin avant sont associés à l’activation de la récupération après sinistre.** Les pools de Front-End au Site A et Site B sont associés entre eux, afin de fournir la prise en charge de la récupération après sinistre. En cas d’échec de la réserve à un seul site, l’administrateur peut échouer sur les utilisateurs de ce site vers le pool de Front-End apparié à l’autre site, avec un minimum d’interruption de service pour les utilisateurs. Chacun de ces deux pools frontaux possède six serveurs, ce qui suffit pour les 40 000 utilisateurs des deux pools en cas de basculement. Pour plus d’informations, consultez [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
    
- **Sauvegarder les serveurs principaux sont mis en miroir.** Pour fournir une disponibilité plus élevée pour les fonctionnalités de l’utilisateur de base, l’organisation a déployé une paire en miroir, de sauvegarder les serveurs principaux pour chaque pool frontal. Il s’agit d’une topologie facultative, et vous pouvez choisir de déployer un seul serveur principal à la place. Les groupes de mise en cluster SQL et de disponibilité AlwaysOn sont également pris en charge. Pour plus d’informations, reportez-vous à la section [haute disponibilité de serveur principal dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
    
- **À l’aide de serveur Standard Edition server à un site de la succursale.** Cette organisation considère le site C comme un site de succursale car il ne dispose que de 600 employés. Cependant, les utilisateurs y organisent beaucoup de conférences A/V entre eux. Si elle a été déployée dans Skype pour Business Server sous la forme d’un site de la succursale, le support de ces conférences s’exécute via le réseau étendu (WAN) vers et à partir d’un site central qui possède un serveur frontal déployé. Pour éviter cette charge potentielle de la bande passante, qu’ils ont installé une paire de serveurs Standard Edition Server sur ce site, ce qui va héberger ces conférences. Dans la mesure où les serveurs Standard Edition Server sont installés, Skype pour Business Server par définition le juge un site central et il est traité en tant que tel dans le Générateur de topologies et de l’outil de planification.
    
    Un serveur Standard Edition server serait suffisante pour performances ici, mais l’organisation a déployé deux et associé les regrouper ensemble pour fournir une haute disponibilité au cas où un serveur tombe en panne.
    
    Même si le site C est considéré comme un site central, vous n’avez pas besoin d’y déployer des serveurs Edge. Dans cet exemple, le site C utilisera les serveurs Edge déployés sur le site A.
    
- **Surveillance et d’archivage** Cette organisation a déployé de surveillance et l’archivage. Lorsque vous déployez ces deux fonctionnalités, elles s’exécutent sur chaque serveur frontal. Les bases de données pour ces fonctionnalités peuvent être colocalisées avec la base de données principale ou se trouver sur un serveur distinct. Cette organisation a disposé ces bases de données sur un serveur distinct des serveurs principaux, dans le site central B. Ces bases de données reçoivent les données de surveillance et d’archivage en provenance des serveurs frontaux dans tous les sites.
    
- **Options de déploiement du site de succursale.** Cette organisation est constitué de plus de 50 sites des succursales, seuls deux sont affichés dans les schémas détaillés. 1 Site de la succursale n’a pas de lien vers le site central, afin qu’ils puissent Survivable Branch Appliances déployés pour fournir le service téléphonique dans le cas où la liaison WAN vers le site central tombe en panne un WAN résilient. Site de la succursale 2 a cependant une liaison WAN robuste, donc il a besoin d’une passerelle réseau téléphonique public commuté. La passerelle RTC déployée il prend en charge le contournement de média, aucun serveur de médiation n’est nécessaire au niveau de la succursale Site 2. Pour plus d’informations sur le choix des éléments à installer sur un site de la succursale, consultez [planification de résilience de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Jonction SIP et serveur de médiation.** Notez que sur le site central B, le serveur de médiation n’est pas colocalisé avec les serveurs frontaux. En effet, un serveur de médiation autonome est préférable sur les sites qui utilisent une jonction SIP. Dans la plupart des autres cas, nous recommandons de colocaliser le serveur de médiation avec le serveur frontal. Pour plus d’informations sur les topologies de serveur de médiation, consultez [composants et les Topologies de serveur de médiation](http://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) dans la documentation de planification.
    
- **La conversation permanente est déployée.** Cette organisation a déployé les serveurs nécessaires pour activer la conversation permanente. Elle a déployé plusieurs serveurs frontaux de conversation permanente afin de gérer la charge pour le nombre d’utilisateurs dans le pool et afin de procurer une haute disponibilité. Elle a également déployé la conformité pour la conversation permanente et colocalisé le magasin de conversation permanente et le magasin de conformité de conversation permanente sur des serveurs distincts. Ces magasins pourraient être colocalisés (et peuvent même être colocalisés avec le serveur principal), mais cette organisation a choisi de les séparer pour des raisons de performances.
    
- **Équilibrage de la charge DNS.** Le pool frontal et le pool de serveur Edge ont un équilibrage de la charge DNS. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge matérielle pour l’interface interne des serveurs Edge et cela réduit significativement le temps consacré à leur configuration et maintenance pour les autres pools, étant donné que ces programmes sont requis uniquement pour le trafic HTTP. Pour plus d’informations, consultez (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).
    
- **Déploiement de la messagerie unifiée Exchange.** Skype pour Business Server fonctionne avec déploiement-bothon d’andhosted de messagerie unifiée Exchange (MU) de messagerie unifiée Exchange. Site Central A inclut un serveur de messagerie unifiée Exchange (MU), qui exécute Microsoft Exchange Server, pas Skype pour Business Server. La fonctionnalité de messagerie unifiée Exchange pour Skype pour Business Server s’exécute sur le pool frontal.
    
    Le site central B utilise la version Exchange hébergée, de sorte que la fonctionnalité du serveur de messagerie unifiée Exchange l’est également. 
    
    Pour plus d’informations sur la messagerie unifiée Exchange, consultez [Local Exchange Unified Messaging intégration](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) et [Hébergé Exchange Unified Messaging intégration](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) dans la documentation de planification.
    
- **Office Web Apps Server.** Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Peut déployer une batterie de serveurs Office Web Apps serveur unique dans un site qui dessert le trafic à partir de tous les sites, ou de déployer dans chaque site. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web. 
    
- **Des directeurs pourraient être ajoutés.** Si cette organisation souhaitait augmenter la sécurité contre les attaques par déni de service, elle pourrait également déployer un pool directeur. Un directeur est un rôle de serveur distinct, facultatif dans Skype pour Business Server qui ne pas les comptes d’utilisateurs à domicile, ou fournir des services de présence ou de conférence. Il sert un serveur interne du tronçon suivant vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur des authentifie les requêtes entrantes et les redirige vers le serveur ou le pool de domicile de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant comme les attaques de déni de service (DoS). Si le réseau est inondé de trafic d’externe non valide dans ce type d’attaque, le trafic se termine sur le directeur.
    
- **System Center Operations Manager est recommandé.** Nous vous recommandons de surveiller la santé de votre Skype pour le déploiement du serveur de l’entreprise afin de garantir la disponibilité de service pour les utilisateurs finaux. Vous pouvez utiliser le Management Pack System Center Operations Manager pour Skype pour entreprise qui est disponible en téléchargement gratuit à partir de Microsoft. Avec le Skype pour le Pack de gestion d’entreprise, vous pouvez par anticipation obtenir des alertes en temps réel lorsque des problèmes se produisent, exécuter les transactions synthétiques pour tester Skype de bout en bout pour les fonctionnalités d’entreprise, obtenir des rapports de disponibilité des services et ainsi de suite. Cela vous aide à répondre de manière proactive aux problèmes de votre déploiement avant de rencontrer les utilisateurs finaux.
    

