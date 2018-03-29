---
title: Notions de base de la topologie pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Résumé : Choix d’une topologie pour Skype pour Business Server 2015. Découvrez la colocalisation de serveurs pour Skype pour Business Server 2015.'
ms.openlocfilehash: 5fbb6a490f8ba35d2e16ccbab60a17d788cb92e8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="topology-basics-for-skype-for-business-server-2015"></a>Notions de base de la topologie pour Skype Entreprise Server 2015
 
**Résumé :** sélectionnez votre topologie pour Skype Entreprise Server 2015. Découvrez la colocalisation des serveurs pour Skype Entreprise Server 2015.
  
Avant de préparer quoi que ce soit d’autre, vous voudrez savoir que vous prévoyez pour la bonne topologie pour votre déploiement de Skype pour Business Server 2015. La première chose que vous devez déterminer est si vous prévoyez d’avoir un déploiement sur site de Skype pour Business Server 2015, ou si vous souhaitez combiner ceci avec un Skype pour le déploiement en ligne de Business Server dans un déploiement hybride. Dans les deux cas, vous allez lire, que nous allons en détail les topologies sur site ici, mais les détails hybrides sont documentées dans leur propre section.
  
Vous pouvez également voir quelques exemples de topologie dans les [topologies de référence pour Skype pour Business Server 2015](reference-topologies.md).
  
## <a name="sites"></a>Sites

Dans Skype pour Business Server, vous définissez des sites sur votre réseau qui contiennent Skype pour les composants serveur de l’entreprise. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que Skype pour les sites du serveur de l’entreprise sont un concept différent des sites de Services de domaine Active Directory et de Microsoft Exchange Server. Votre Skype pour les sites de Business Server n’avez pas besoin de correspondre à vos sites Active Directory.
  
Skype pour Business Server 2015 prend en charge le déploiement sur site d’un ou plusieurs sites qui peuvent être mis à l’échelle en fonction de vos exigences d’emplacement et de haute disponibilité.
  
Votre déploiement aura au moins un site central (également appelé un centre de données, c’est un centre de données pour tous les serveurs situés dans cette zone), et chaque site central dans votre déploiement dispose d’un serveur Standard Edition server ou au moins un pool Enterprise Edition Front-End. Leurs différences sont illustrées dans les options ci-dessous :
  
- Serveur Standard Edition server inclut une base de données de SQL Server Express concurrentes.
    
- Pool frontal de Enterprise Edition inclut :
    
  - Un ou plusieurs serveurs frontaux (idéalement au moins trois, de l’évolutivité), avec un maximum de douze. L’équilibrage de charge sera requis dans le cas de plusieurs serveurs.
    
  - Un autre serveur principal.
    
Vous obtiendrez plus d’informations sur les rôles serveur plus loin dans cette rubrique.
  
En plus de vos sites centraux, vous risquez également un ou plusieurs sites de succursale associé à votre site central. Ils dépendent du site central, presque toutes les fonctionnalités, donc ils constitués, exactement quels sont les ?
  
- Survivable Branch Appliance, qui associe une passerelle téléphonique public commuté (RTPC), certains Skype pour les fonctionnalités de Business Server 2015.
    
- Serveur Survivable Branch Server, il est un serveur qui exécute Windows Server a Skype pour du logiciel Business Server 2015 greffier et serveur de médiation.
    
- Passerelle RTPC autonome (qui ne fait pas partie de la Survivable Branch Appliance).
    
- Serveur de médiation autonome ou d’un pool de serveur de médiation autonome (si vous ne souhaitez pas colocaliser ce rôle avec les Survivable Branch Appliance).
    
## <a name="whats-in-a-skype-for-business-server-site"></a>Nouveautés dans un Skype pour site Business Server ?

Pour obtenir plus de détails, un site central peut également avoir :
  
- Plusieurs pools de Front-End, dans le même domaine ou de domaines différents (n’oubliez pas que lors de la planification que tous les serveurs frontaux dans un pool frontal, ainsi que les serveurs principaux de retour pour le pool, ne doivent pas être dans le même domaine).
    
- Plusieurs serveurs Standard Edition Server.
    
- Office Web Apps serveur qui est utilisé par Office Web Apps dans Skype pour Business Server 2015 pour le partage et le rendu des présentations PowerPoint.
    
- Pool de serveur de transport Edge ou bord (dans un réseau de périmètre). Nécessaire si vous voulez que votre déploiement prenne en charge des partenaires fédérés, la connectivité PIC (Public IM Connectivity), la passerelle XMPP, et l’accès pour un utilisateur distant. Vous trouverez plus de détails dans la documentation de planification du serveur Edge.
    
- Serveur de conversation permanent. Utile si vous souhaitez que les utilisateurs participent à des conversations thématiques durables à plusieurs. Il y a davantage d’informations sur la planification de la rubrique du serveur de conversation persistant.
    
- Surveillance. Utilisé pour prendre en charge la collecte de données audio/vidéo (A / V) d’enregistrement (CDR) en détail Quality of Experience (QoE) et l’appel de Voix Entreprise et A / vidéoconférences dans votre déploiement. Cela est expliqué en détail dans la rubrique sur la planification de la surveillance.
    
- Pool de directeur ou de directeur. Pas obligatoire, mais utile si vous souhaitez améliorer la souplesse et activer la redirection de Skype pour les demandes d’utilisateur Business 2015 au pool de domicile de l’utilisateur. Si vous souhaitez déployer les directeurs, un maximum de 10 par pool est pris en charge. Si c’est quelque chose dont vous avez besoin, sans aucun doute continuer la lecture au niveau de la planification de la rubrique de directeurs.
    
- Proxy inverse. Ce n’est pas un Skype pour composant de Business Server 2015, mais si vous souhaitez prendre en charge le partage de contenu web pour fédéré les utilisateurs si vous avez l’intention de prendre en charge le trafic de mobilité, après que les utilisateurs distants à utiliser le carnet d’adresses, participer à des conférences et ainsi de suite, il s’agit d’un élément Vous souhaiterez disposer dans votre environnement. Il existe un configuration de rubrique de serveur proxy inverse que vous pouvez extraire pour plus de détails, lorsque vous êtes prêt.
    
Vous trouverez plus d’informations sur la colocalisation de ces serveurs plus bas.
  
Tous les pools du Front-End et les serveurs Standard Edition Server déployés sur votre site central partagent les éléments suivants, si vous avez déployé les :
  
||||
|:-----|:-----|:-----|
|Pool de directeur ou de directeur  <br/> |Serveur de médiation autonome ou d’un pool de serveur de médiation  <br/> |Office Web Apps Server  <br/> |
|Pool de serveur de transport Edge ou une arête  <br/> |Pool de serveur Chat ou serveur de Chat persistant permanent  <br/> |Surveillance  <br/> |
   
Où se trouve le serveur de messagerie unifiée Exchange (MU) dans cette liste ? Vous pouvez certainement l’utiliser avec Skype pour Business Server 2015 si vous souhaitez intégrer avec la messagerie unifiée d’Exchange, mais il n’est pas un composant de la Skype pour le site du serveur de l’entreprise, afin que nous ne sommes pas très loin ici.
  
Peut prévoir d’avoir plusieurs site central, et si tel est le cas, ils peuvent partager les serveurs suivants et les rôles, si elles sont déployées sur votre site central :
  
|||
|:-----|:-----|
|Serveur de médiation autonome ou d’un pool de serveur de médiation  <br/> |Pool de serveur de transport Edge ou une arête  <br/> |
|Pool de serveur Chat ou serveur de Chat persistant permanent  <br/> |Surveillance  <br/> |
   
Tout comme la dernière liste, nous n’y compris Exchange UM Server ici, car il ne fait pas partie de la Skype pour le déploiement de Business Server 2015, mais elle se situe dans la même catégorie, trop.
  
Certains autres composants et options font partie du déploiement.
  
|||||
|:-----|:-----|:-----|:-----|
|Pare-feu  <br/> |Passerelles PSTN (si Voix en Entreprise est déployé)  <br/> |Exchange serveur de messagerie unifiée (si vous souhaitez intégrer avec la messagerie unifiée d’Exchange)  <br/> |Équilibrage de charge DNS  <br/> |
|Programmes d’équilibrage de la charge matérielle  <br/> |Bases de données SQL Server  <br/> |Partages de fichiers  <br/> ||
   
## <a name="server-roles"></a>Rôles serveur

Chaque serveur exécutant Skype pour Business Server exécute un ou plusieurs rôles de serveur. Un rôle de serveur est un ensemble défini de Skype pour les fonctionnalités de Business Server fournis par ce serveur. Il n’est pas nécessaire de déployer tous les rôles serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.
  
Pour la plupart des rôles de serveur, d’évolutivité et de disponibilité vous pouvez déployer des pools de serveurs multiples tous exécutant le même rôle de serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Pour la plupart des types de pools dans Skype pour Business Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs dans le pool. Skype pour Business Server prend en charge à la fois l’équilibrage de charge de système de nom de domaine (DNS) et les équilibreurs de charge matériels.
  
### <a name="front-end-server-and-back-end-server"></a>Serveur frontal et serveur principal

Dans Skype pour Business Server Enterprise Edition, le serveur frontal est le rôle de serveur principal et s’exécute de nombreuses Skype de base pour les fonctions de serveur de l’entreprise. Le serveur frontal, ainsi que les serveurs principaux de retour, sont les seuls rôles de serveur doit être dans n’importe quel Skype pour le déploiement de Business Server Enterprise Edition. 
  
Un pool frontal est un ensemble de serveurs frontaux, configurés de manière identique, qui fonctionnent ensemble pour fournir des services pour un groupe d’utilisateurs communs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.
  
Le serveur frontal inclut les éléments suivants :
  
- Enregistrement et authentification des utilisateurs.
    
- Informations de présence et échange de cartes de visite.
    
- Services de carnet d’adresses et développement de listes de distribution.
    
- Fonctionnalités de messagerie instantanée, dont les conférences de messagerie instantanée à plusieurs.
    
- Conférence web, conférence rendez-vous PSTN et conférence A/V (si déployée).
    
- Hébergement d’applications, pour les applications incluses avec Skype pour serveur d’entreprise (par exemple, application intendant Conférence et groupe de réponse) et les applications tierces.
    
- Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournissent des mesures relatives à la qualité du média (audio et vidéo) Parcourir le réseau pour les appels de Voix Entreprise et A / vidéoconférences.
    
- Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.
    
- Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, consultez [planification d’archivage](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) dans la documentation de planification.
    
    Dans Lync Server 2010 et les versions précédentes, de suivi et d’archivage ont des rôles serveur, ne pas colocalisés sur le serveur frontal.
    
- Services web de conversation permanente, si celle-ci est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.
    
Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.
  
En outre, un serveur frontal dans le déploiement s’exécute également le serveur d’administration centrale qui gère et déploie des données de configuration de base pour tous les serveurs exécutant Skype pour Business Server. Le serveur d’administration centrale fournit également des capacités de transfert de fichiers et de Communications Server Management Shell.
  
Les serveurs principaux en sont des serveurs de base de données Microsoft SQL Server en cours d’exécution qui fournissent les services de base de données pour le pool de Front-End. Les serveurs principaux en servir en tant que sauvegarde magasins pour l’utilisateur et les données de conférence du pool et sont le stockage principal des autres bases de données comme la base de données du groupe de réponse. Vous pouvez avoir un seul serveur principal, mais une solution qui utilise la mise en miroir de SQL Server est recommandée pour le basculement. Serveurs d’arrière-plan ne s’exécutent pas tout Skype pour le logiciel de serveur d’entreprise.
  
> [!IMPORTANT]
> Nous ne recommandons pas de cohabitation Skype pour bases de données de serveur de l’entreprise avec d’autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées. 
  
Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.
  
### <a name="edge-server"></a>Serveur Edge

Serveur de transport Edge permet aux utilisateurs de communiquer et de collaborer avec les utilisateurs en dehors du pare-feu de l’entreprise. Ces utilisateurs externes peuvent inclure les utilisateurs de l’organisation qui sont actuellement hors site de travail, les utilisateurs d’organisations partenaires fédérés et les utilisateurs externes qui ont été invitées à participer à des conférences hébergées sur votre Skype pour le déploiement du serveur de l’entreprise.
  
Déploiement de serveur Edge également Active les services de mobilité, qui prend en charge les fonctionnalités de Lync sur les périphériques mobiles. Les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les périphériques mobiles prennent en charge certaines fonctionnalités de Voix Entreprise, par exemple pour joindre une conférence, les appels via le travail, portée de numéro unique, la messagerie vocale et les appels manqués. La fonctionnalité de mobilité prend également en charge les notifications de type Pousser pour les périphériques mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.
  
Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour activer votre Skype pour les utilisateurs de Business Server ajouter des contacts à partir des partenaires de XMPP pour la messagerie instantanée et de présence.
  
### <a name="mediation-server"></a>Serveur de médiation

Serveur de médiation est un composant nécessaire pour l’implémentation de Voix Entreprise appeler Via le travail, conférence et accès à distance. Serveur de médiation se traduit par la signalisation et, dans certaines configurations, les médias entre votre Skype interne pour l’infrastructure de serveur d’entreprise et un public commuté passerelle réseau (RTPC) de téléphone IP-PBX ou un tronc de Session Initiation Protocol (SIP). Vous pouvez exécuter le serveur de médiation colocalisés sur le même serveur comme serveur frontal, ou séparé dans un pool de serveur de médiation autonome.
  
Pour plus d’informations, reportez-vous à la section [composant de serveur de médiation dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).
  
### <a name="video-interop-server"></a>Serveur VIS (Video Interop Server)

Serveur d’interopérabilité vidéo est un nouveau rôle dans Skype pour Business Server 2015. Il vous permet d’intégrer votre Skype pour le déploiement du serveur de l’entreprise avec certaines solutions VTC (système de téléconférence vidéo) tiers. Une VIS joue le rôle d’intermédiaire entre un système de téléconférence 3ème partie et un Skype pour le déploiement du serveur de l’entreprise. Pour cette version, le VIS se concentre sur l’interopérabilité avec les systèmes vidéo Cisco/Tandberg.
  
Pour plus d’informations, reportez-vous à [planification pour serveur d’interopérabilité vidéo dans Skype pour Business Server 2015](../../plan-your-deployment/video-interop-server.md).
  
### <a name="director"></a>directeur

Les directeurs peuvent s’authentifier Skype pour les demandes d’utilisateur de serveur de l’entreprise, mais pas les comptes d’utilisateurs à domicile ou fournir des services de conférence ou de la présence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux.
  
### <a name="persistent-chat-server-roles"></a>Rôles de serveur de conversation permanent

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques durables à plusieurs. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.
  
Les serveurs en cours d’exécution Skype Business Server Standard Edition peut également exécuter de conversation permanente colocalisés sur le même serveur. Vous ne pouvez pas colocaliser le persistant Chat serveur frontal avec un serveur Enterprise Edition frontal.
  
Pour plus d’informations, consultez [planification de serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).
  
## <a name="high-availability-and-disaster-recovery-support"></a>Prise en charge de la haute disponibilité et de la récupération d’urgence

Skype pour Business Server assure une disponibilité élevée par la redondance des serveurs via un regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.
  
Skype pour Business Server fournit également après sinistre des mesures de récupération en activant l’appariement de pool. Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte. Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.
  
Skype pour Business Server prend également en charge plusieurs options pour la haute disponibilité du serveur principal. Ce sont les suivants :
  
- Mise en miroir de bases de données
    
- Groupes de disponibilité AlwaysOn
    
- Les Instances de Cluster de basculement AlwaysOn (FCI)
    
- Clustering SQL avec basculement
    
Pour plus d’informations sur l’appariement de pool et de haute disponibilité du serveur principal, voir [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
## <a name="server-collocation-in-skype-for-business-server-2015"></a>Colocalisation de serveurs dans Skype pour Business Server 2015

Nous avons utilisé le terme colocaliser déjà, mais que cela signifie-t-il ? Skype pour Business Server 2015 vous permet de localiser certains rôles et fonctionnalités serveur sur le même serveur, ce qui est de colocalisation, ou sur des serveurs différents, mais il peut prêter à confusion lorsque vous commencez, et si vous faites un Standard Edition Server ou Enterprise Edition déploiement de serveur (ils sont fournis avec leurs propres règles). Pour vous aider dans votre planification, nous allons y compris colocalisation de serveurs dans les déploiements sur un serveur Standard Edition et les déploiements du pool Enterprise Edition Front-End (dans la plupart des cas, ces informations sont identiques, et dans le cas où il est différent, il est appelé en particulier).
  
### <a name="collocation-of-server-roles"></a>Colocalisation des rôles serveur

Le serveur Standard Edition server a suivantes rôle colocalisés (configuration supplémentaire n’est nécessaire bien que), tandis que dans le pool Enterprise Edition Front-End, ce rôle peut être colocalisé ou déployé sur un serveur distinct :
  
- Serveur(s)
    
Ces rôles serveur doivent être individuellement déployés sur un serveur distinct :
  
- directeur
    
- Edge
    
- Serveur VIS (Video Interop Server)
    
- Office Web Apps
    
### <a name="databases"></a>Bases de données

Il s’agit de la zone de différence entre les déploiements de serveurs Standard Edition et les déploiements de pool de serveurs Enterprise Edition, et nous devrons donc deux sections ci-dessous, suivi par d’autres règles pour les deux.
  
#### <a name="standard"></a>Standard

Express de SQL Server se trouve sur le serveur Standard Edition et ne peut pas être déplacé, c’est assez simple. En outre, si vous déployez un serveur de Chat persistant sur un serveur Standard Edition, vous pourrez également colocaliser trop du Chat persistant et la base de données du respect de la réglementation Chat persistant sur le serveur Standard Edition, mais vous n’êtes pas obligé.
  
Ces ne peut pas être colocalisés sur le serveur Standard Edition, mais peuvent être placé sur un serveur de base de données unique qui leur sont propres :
  
- base de données de surveillance
    
- base de données d’archivage
    
- Toute base de données back-end pour un pool Enterprise Edition Front-End
    
#### <a name="enterprise"></a>Enterprise

Bases de données suivantes peuvent être colocalisés sur le même serveur principal de SQL Server :
  
- Base de données principale
    
- base de données de surveillance
    
- base de données d’archivage
    
- Base de données persistante de conversation
    
- Base de données de conformité Chat permanente
    
#### <a name="both"></a>Les deux

Maintenant, voici quelques règles supplémentaires à suivre pour COLLOCATION Skype pour bases de données Business Server 2015 dans une instance unique de SQL ou dans plusieurs instances SQL dans la même base de données SQL Server :
  
- Chaque instance SQL ne peut contenir qu’une base de données back-end unique pour un pool Enterprise Edition Front-End, une seule base de données d’analyse, une base de données d’archivage unique, une seule base de données Chat persistant et une base de conformité de conversation permanent unique.
    
- Le serveur de base de données ne peut pas prendre en charge plus d’un pool Enterprise Edition Front-End, un serveur d’archivage, un serveur qui exécute l’analyse, une base de données unique de conversation permanents et un seul Chat persistant conformité de base de données, mais il peut prendre en charge un des deux, indépendamment de si les bases de données utilisent la même instance de SQL Server ou à des instances distinctes de SQL Server.
    
### <a name="file-shares"></a>Partages de fichiers

Le partage de fichier peut être sur un serveur distinct ou colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :
  
- Serveur de base de données, y compris le serveur principal d’un pool Enterprise Edition Front-End
    
- base de données de surveillance
    
- base de données d’archivage
    
- Base de données persistante de conversation
    
- Base de données de conformité Chat permanente
    
> [!CAUTION]
> Notez que même si vous pouvez colocaliser le partage de fichiers sur ces serveurs, il est primordial de comprendre que cela n’est pas recommandé. Si vous souhaitez colocaliser le partage de fichiers avec un autre rôle de serveur, veillez à surveiller régulièrement l’espace disque ou les problèmes de performances. 
  
### <a name="keep-in-mind"></a>À retenir :

- Vous ne pouvez pas colocaliser un serveur proxy inverse, ce qui n’est pas d’un Skype pour composant de Business Server 2015 et même parfois pas dans votre topologie. Vous aurez besoin de proxy inverse si vous souhaitez prendre en charge le partage de contenu web pour les utilisateurs fédérés, parmi beaucoup d’autres choses. Si vous le souhaitez, continuez et mettre en œuvre la prise en charge de proxy inverse pour Skype pour 2015 de serveur d’entreprise en configurant un serveur proxy inverse existant qui est déjà dans votre organisation qui est utilisée par d’autres applications.
    
- Vous ne pouvez pas colocaliser n’importe quel composant de messagerie unifiée Exchange ou SharePoint Server avec n’importe quel Skype pour le rôle de Business Server 2015.
    
## <a name="see-also"></a>Voir aussi

#### 

[Topologies de référence pour Skype pour Business Server 2015](reference-topologies.md)

