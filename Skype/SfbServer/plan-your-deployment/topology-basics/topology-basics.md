---
title: Concepts de base de topologie pour Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Résumé : Choisissez votre topologie pour Skype pour Business Server. Découvrez la colocalisation de serveurs pour Skype pour Business Server.'
ms.openlocfilehash: 303954cc030d2caf61528e1c5b1076b6c1ef5d0d
ms.sourcegitcommit: dba47a65b0725806c98702bb7362a1b105cc93df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2018
ms.locfileid: "21249357"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Concepts de base de topologie pour Skype pour Business Server
 
**Résumé :** Choix d’une topologie pour Skype pour Business Server. Découvrez la colocalisation de serveurs pour Skype pour Business Server.
  
Avant de préparer chose, vous voudrez savoir que vous projetez de la topologie appropriée pour votre déploiement de Skype pour Business Server. La première chose que vous devez décider s’il est si vous envisagez d’avoir un déploiement local de Skype pour Business Server, ou si vous envisagez de combiner avec un Skype pour le déploiement en ligne Business Server dans un déploiement hybride. Les deux cas, vous allez lire en outre, nous allons en détail les topologies locales ici, mais les détails hybride sont documentées dans leur propre section.
  
Vous pouvez également consulter des exemples de topologies dans les [topologies de référence pour Skype pour Business Server](reference-topologies.md).
  
## <a name="sites"></a>Sites

Dans Skype pour Business Server, vous définissez les sites de votre réseau qui contiennent Skype pour les composants Business Server. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que Skype pour les sites Business Server sont un concept différent des sites de Services de domaine Active Directory et Microsoft Exchange Server. Votre Skype pour les sites Business Server est inutile qui correspond à vos sites Active Directory.
  
Skype pour Business Server prend en charge le déploiement local d’un ou plusieurs sites qui peuvent être mis à l’échelle en fonction de votre haute disponibilité et les critères d’emplacement.
  
Votre déploiement aura au moins un site central (également appelé un centre de données, il s’agit un centre de données pour tous les serveurs situés dans cette zone), et chaque site central dans votre déploiement aura un serveur Standard Edition ou au moins un pool frontal Enterprise Edition. Leurs différences sont illustrées dans les options ci-dessous :
  
- Serveur Standard Edition server inclut une base de données SQL Server Express colocalisée.
    
- Pool frontal Enterprise Edition inclut :
    
  - Un ou plusieurs serveurs frontaux (de préférence au moins trois, évolutivité), avec un maximum de douze. L’équilibrage de charge sera requis dans le cas de plusieurs serveurs.
    
  - Un distinct serveur principal.
    
Vous obtiendrez plus d’informations sur les rôles serveur plus loin dans cette rubrique.
  
En plus de vos sites centraux, vous risquez également avoir un ou plusieurs sites de succursale associés à votre site central. Elles dépendent sur le site central presque toutes les fonctionnalités, donc ils composent, exactement quels sont les ?
  
- Survivable Branch Appliance, qui associe une passerelle téléphonique commuté (RTC), certains Skype pour la fonctionnalité Business Server.
    
- Serveur Survivable Branch Server, il est un serveur exécutant Windows Server avec Skype pour le serveur d’inscriptions de Business Server et le logiciel de serveur de médiation.
    
- Passerelle PSTN autonome (qui ne font pas partie du Survivable Branch Appliance).
    
- Serveur de médiation autonome ou le pool de serveur de médiation autonome (si vous ne souhaitez pas colocaliser ce rôle avec le Survivable Branch Appliance).
    
## <a name="whats-in-a-skype-for-business-server-site"></a>Nouveautés dans un Skype pour site Business Server ?

Pour obtenir plus de détails, un site central peut également avoir :
  
- Plusieurs pools frontaux, dans le même domaine ou des domaines différents (n’oubliez pas lors de la planification que tous les serveurs frontaux dans un pool frontal, ainsi que les serveurs principaux pour le pool, doivent se trouver dans le même domaine).
    
- Plusieurs serveurs Standard Edition Server.
    
- Office Web Apps Server, qui est utilisé avec Office Web Apps dans Skype pour Business Server pour le partage et le rendu des présentations PowerPoint.
    
- Pool de serveur Edge ou Edge (dans un réseau de périmètre). Nécessaire si vous voulez que votre déploiement prenne en charge des partenaires fédérés, la connectivité PIC (Public IM Connectivity), la passerelle XMPP, et l’accès pour un utilisateur distant. Vous trouverez plus de détails dans la documentation de planification de serveur Edge.
    
- Serveur de conversation permanente. Utile si vous souhaitez que les utilisateurs participent à des conversations thématiques durables à plusieurs. Il existe plus d’informations sur la planification de la rubrique Persistent Chat Server.
    
- Surveillance. Utilisé pour prendre en charge la collecte de données pour l’audio/vidéo (A / V) d’enregistrement de détails de qualité de l’expérience (QoE) et d’appel pour Enterprise Voice et A / vidéoconférences dans votre déploiement. Cela est expliqué en détail dans la rubrique sur la planification de la surveillance.
    
- Directeur ou pool directeur. Pas obligatoire, mais utile si vous voulez améliorer la souplesse et activer la redirection de Skype pour les requêtes d’utilisateur d’entreprise pour le pool d’accueil de l’utilisateur. Si vous souhaitez déployer les directeurs, un maximum de 10 par pool est pris en charge. S’il s’agit de quelque chose dont vous avez besoin, sans aucun doute continuer votre lecture à la planification pour les directeurs rubrique.
    
- Proxy inverse. Ce n’est pas un Skype pour le composant serveur d’entreprise, mais si vous souhaitez prendre en charge le partage de contenu web pour les utilisateurs fédérés, si vous souhaitez prendre en charge le trafic de mobilité, si vous souhaitent que vos utilisateurs distants utiliser le carnet d’adresses, participation aux réunions et ainsi de suite, il s’agit d’un élément vous allez vous souhaitez disposer dans votre environnement. Il existe un paramètre rubrique de serveur proxy inverse que vous pouvez extraire pour plus d’informations, lorsque vous êtes prêt.
    
Vous trouverez plus d’informations sur la colocalisation de ces serveurs plus bas.
  
Tous les pools frontaux et les serveurs Standard Edition Server déployé sur votre site central partage la suivante, en supposant que vous avez déployé les :
  
||||
|:-----|:-----|:-----|
|Directeur ou pool directeur  <br/> |Serveur de médiation autonome ou un pool de serveur de médiation  <br/> |Office Web Apps Server  <br/> |
|Pool de serveur Edge ou Edge  <br/> |Pool de serveur de conversation ou Persistent Chat Server permanent  <br/> |Surveillance  <br/> |
   
Où se trouve le serveur de messagerie unifiée Exchange (MU) dans cette liste ? Eh bien, vous pouvez certainement utiliser il avec Skype pour Business Server si vous voulez intégrer à la messagerie unifiée Exchange, mais il n’est pas un composant de la Skype pour site Business Server, afin que nous n'avons pas il mentionné ici.
  
Vous pouvez être envisagez d’avoir plusieurs site central, et si c’est ainsi, ils peuvent partager les serveurs et rôles suivants si elles sont déployées sur votre site central :
  
|||
|:-----|:-----|
|Serveur de médiation autonome ou un pool de serveur de médiation  <br/> |Pool de serveur Edge ou Edge  <br/> |
|Pool de serveur de conversation ou Persistent Chat Server permanent  <br/> |Surveillance  <br/> |
   
Tout comme la dernière liste, nous ne, notamment le Exchange UM serveur ici car ne fait pas partie de la Skype pour le déploiement de serveur d’entreprise, mais elle se trouve dans la même catégorie ici, trop.
  
Certains autres composants et options font partie du déploiement.
  
|||||
|:-----|:-----|:-----|:-----|
|Pare-feu  <br/> |Passerelles PSTN (si Voix en Entreprise est déployé)  <br/> |Exchange serveur de messagerie unifiée (si vous voulez intégrer avec la messagerie unifiée Exchange)  <br/> |Équilibrage de charge DNS  <br/> |
|Programmes d’équilibrage de la charge matérielle  <br/> |Bases de données SQL Server  <br/> |Partages de fichiers  <br/> ||
   
## <a name="server-roles"></a>Rôles serveur

Chaque serveur exécutant Skype pour Business Server exécute un ou plusieurs rôles de serveur. Un rôle de serveur est un ensemble défini de Skype pour les fonctionnalités de Business Server fournis par ce serveur. Il n’est pas nécessaire de déployer tous les rôles serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.
  
Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des pools de plusieurs serveurs exécutant tous le même rôle serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. La plupart des types de pools dans Skype pour Business Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs du pool. Skype pour Business Server prend en charge à la fois l’équilibrage de charge de nom de domaine DNS (Domain Name System) et les équilibreurs de charge matérielle.
  
### <a name="front-end-server-and-back-end-server"></a>Serveur frontal et serveur principal

Dans Skype pour Business Server Enterprise Edition, le serveur frontal est le rôle de serveur principal et exécute des nombreux Skype de base pour les fonctions Business Server. Le serveur frontal, ainsi que les serveurs principaux, sont les seuls rôles de serveur doit être dans n’importe quel Skype pour le déploiement de Business Server Enterprise Edition. 
  
Un pool frontal est un ensemble de serveurs frontaux, configurés à l’identique, qui fonctionnent ensemble pour fournir des services à un groupe commun d’utilisateurs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.
  
Le serveur frontal inclut les éléments suivants :
  
- Enregistrement et authentification des utilisateurs.
    
- Informations de présence et échange de cartes de visite.
    
- Services de carnet d’adresses et développement de listes de distribution.
    
- Fonctionnalités de messagerie instantanée, dont les conférences de messagerie instantanée à plusieurs.
    
- Conférence web, conférence rendez-vous PSTN et conférence A/V (si déployée).
    
- Hébergement d’applications, pour les applications incluses avec Skype pour Business Server (par exemple, les applications intendant Conférence et Response Group) et les applications tierces.
    
- Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournit des mesures relatives à la qualité du média (audio et vidéo) parcourir votre réseau pour les appels Enterprise Voice et A / vidéoconférences.
    
- Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.
    
- Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, voir [Planning for Archiving](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) dans la documentation de planification.
    
    Dans Lync Server 2010 et les versions antérieures, surveillance et archivage étaient des rôles serveur distincts, non colocalisés sur le serveur frontal.
    
- Services web de conversation permanente, si celle-ci est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.
    
Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.
  
En outre, un serveur frontal dans le déploiement s’exécute également le serveur de gestion centralisée, qui gère et déploie des données de configuration de base pour tous les serveurs exécutant Skype pour Business Server. Le serveur de gestion centralisée fournit également Lync Server Management Shell et les capacités de transfert de fichier.
  
Les serveurs principaux sont les serveurs de base de données exécutant Microsoft SQL Server qui fournissent les services de base de données pour le pool frontal. Les serveurs principaux servir de magasins de sauvegarde pour un utilisateur du pool et les données de conférence et sont le stockage principal des autres bases de données telles que la base de données Response Group. Vous pouvez avoir un seul serveur principal, mais le [serveur principal de haute disponibilité dans Skype pour Business Server](../high-availability-and-disaster-recovery/back-end-server.md) est recommandée pour le basculement. Les serveurs frontaux arrière n’exécutez pas n’importe quel Skype pour le logiciel de serveur d’entreprise.
  
> [!IMPORTANT]
> Nous ne recommandons pas Skype la colocalisation des bases de données Business Server avec les autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées. 

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype pour Business Server 2015 mais n’est plus pris en charge dans Skype pour Business Server 2019. Les méthodes de clustering avec basculement SQL, les Instances de Cluster de basculement AlwaysOn (FCI) et les groupes de disponibilité AlwaysOn sont préférés avec Skype pour Business Server 2019.
  
Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.
  
### <a name="edge-server"></a>Serveur Edge

Serveur de transport Edge permet aux utilisateurs de communiquer et collaborer avec les utilisateurs en dehors du pare-feu de l’organisation. Ces utilisateurs externes peuvent inclure les utilisateurs de l’organisation qui sont actuellement hors site de travail, les utilisateurs d’organisations partenaires fédérés et les utilisateurs externes qui ont été invités à participer à des conférences hébergées sur votre Skype pour le déploiement de serveur d’entreprise.
  
Déploiement de serveur Edge également Active les services de mobilité, qui prend en charge les fonctionnalités Lync sur les appareils mobiles. Les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Enterprise Voice, tels que pour joindre une conférence, appel via le bureau, appel de numéro unique, la messagerie vocale et les appels manqués. La fonctionnalité de mobilité prend également en charge les notifications push pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.
  
Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour activer votre Skype pour les utilisateurs Business Server ajouter des contacts de partenaires basés sur XMPP pour la messagerie instantanée et la présence.

> [!NOTE]
> XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="mediation-server"></a>Serveur de médiation

Serveur de médiation est un composant indispensable pour l’implémentation d’Enterprise Voice, appel via le bureau et conférence rendez-vous. Serveur de médiation traduit la signalisation et, dans certaines configurations, les médias entre votre Skype pour l’infrastructure de serveur d’entreprise interne et un commuté passerelle de réseau (RTC) téléphonique, IP-PBX ou une jonction de protocole SIP (Session Initiation). Vous pouvez exécuter le serveur de médiation colocalisés sur le même serveur que le serveur frontal, ou séparées dans un pool de serveur de médiation autonome.
  
Pour plus d’informations, voir [composant serveur de médiation dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).
  
### <a name="video-interop-server"></a>Serveur VIS (Video Interop Server)

Serveur d’interopérabilité vidéo est un nouveau rôle de Skype pour Business Server 2015. Elle vous permet d’intégrer votre Skype pour le déploiement de serveur d’entreprise avec certaines solutions VTC (système de téléconférence vidéo) tiers. Un rapport joue le rôle d’intermédiaire entre un 3ème partie téléconférence et un Skype pour le déploiement de serveur d’entreprise. Pour cette version, le VIS se concentre sur l’interopérabilité avec les systèmes vidéo Cisco/Tandberg.
  
Pour plus d’informations, voir [planifier vidéo Interop Server dans Skype pour Business Server](../../plan-your-deployment/video-interop-server.md).
  
### <a name="director"></a>directeur

Les directeurs peuvent s’authentifier Skype pour les demandes utilisateur Business Server, mais pas les comptes d’utilisateurs à domicile ou fournir la présence ou les services de conférence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux.
  
### <a name="persistent-chat-server-roles"></a>Rôles de serveur de conversation permanente

> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques durables à plusieurs. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.
  
Serveurs exécutant Skype pour Business Server Standard Edition peut également exécuter conversation permanente colocalisés sur le même serveur. Vous ne pouvez pas colocaliser Persistent Chat serveur frontal avec Enterprise Edition serveur frontal.
  
Pour plus d’informations, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).
  
## <a name="high-availability-and-disaster-recovery-support"></a>Prise en charge de la haute disponibilité et de la récupération d’urgence

Skype pour Business Server fournit une haute disponibilité à la redondance des serveurs via un regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.
  
Skype pour Business Server fournit également reprise après sinistre des mesures de récupération en activant l’appariement. Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte. Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.
  
Skype pour Business Server prend également en charge plusieurs options pour la haute disponibilité du serveur principal. Ce sont les suivants :
  
- Mise en miroir de bases de données
    
- Groupes de disponibilité AlwaysOn
    
- Cluster de basculement AlwaysOn Instances (FCI)
    
- Clustering SQL avec basculement
    
Pour plus d’informations sur l’appariement et une haute disponibilité du serveur principal, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
## <a name="server-collocation-in-skype-for-business-server"></a>Colocalisation de serveurs dans Skype pour Business Server

Nous avons utilisé le terme colocaliser déjà, mais cela signifie ? Skype pour Business Server vous permet de localiser des rôles de serveur et les fonctionnalités sur le même serveur, qui est la colocalisation, ou sur des serveurs différents, mais il peut être difficile lorsque vous commencez, et si vous effectuez un serveur Standard Edition ou Enterprise Edition déploiement (chaque proviennent avec leurs propres règles). Pour vous aider dans votre planification, nous allons y compris colocalisation de serveurs dans un déploiement Standard Edition server et les déploiements du pool frontal Enterprise Edition (dans la plupart des cas, ces informations sont identiques, et lorsqu’il est différent, il est appelé en particulier).
  
### <a name="collocation-of-server-roles"></a>Colocalisation des rôles serveur

Le serveur Standard Edition server comporte les éléments suivants role colocalisé (configuration supplémentaire est requise mais), alors que dans le pool frontal Enterprise Edition, ce rôle peut être colocalisé ou déployé sur un serveur distinct :
  
- Serveur(s)
    
Ces rôles serveur doivent être individuellement déployés sur un serveur distinct :
  
- directeur
    
- Edge
    
- Serveur VIS (Video Interop Server)
    
- Office Web Apps
    
### <a name="databases"></a>Bases de données

Il s’agit de la zone de la différence entre un déploiement Standard Edition server et le déploiement de pool Enterprise Edition server, afin que nous aurons deux sections ci-dessous, suivi par d’autres règles pour les deux.
  
#### <a name="standard"></a>Standard

Étant donné que SQL Server Express est colocalisé sur le serveur Standard Edition server et ne peut pas être déplacé, il est relativement simple. En outre, si vous déployez un serveur de conversation permanente sur un serveur Standard Edition server, vous pouvez également colocaliser trop de la conversation permanente et la base de la conformité de conversation permanente sur le serveur Standard Edition, mais vous n’avez pas besoin.
  
    > [!NOTE] 
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015. 

Ces ne peut pas se trouver sur le serveur Standard Edition, mais peuvent passer sur un serveur de base de données unique de leurs propres :
  
- base de données de surveillance
    
- base de données d’archivage
    
- Toute base de données principale pour un pool frontal Enterprise Edition
    
#### <a name="enterprise"></a>Enterprise

Bases de données suivantes peuvent être colocalisés sur le même serveur principal SQL Server :
  
- Base de données principale
    
- base de données de surveillance
    
- base de données d’archivage
    
- Base de données de conversation permanente
    
- Base de données de conformité conversation permanente
    
#### <a name="both"></a>Les deux

À présent, il existe d’autres règles à suivre lors de la colocalisation Skype pour les bases de données Business Server dans une instance SQL unique ou de plusieurs instances SQL dans la même base de données SQL Server :
  
- Chaque instance SQL ne peut contenir qu’une base de données principal unique pour un pool frontal Enterprise Edition, une seule base de données d’analyse, une base de données d’archivage, une seule base de données conversation permanente et une base de conformité de conversation permanente unique.
    
- Le serveur de base de données ne peut pas prendre en charge plusieurs pools frontaux Enterprise Edition, un serveur d’archivage, un serveur de surveillance, une seule base de données conversation permanente et une seule conversation permanente conformité base de données en cours d’exécution en cours d’exécution, mais elle peut prendre en charge un des deux, quel que soit si les bases de données utilisent la même instance de SQL Server ou des instances distinctes de SQL Server.
    
    > [!NOTE] 
    > Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 

### <a name="file-shares"></a>Partages de fichiers

Le partage de fichier peut être sur un serveur distinct ou colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :
  
- Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition
    
- base de données de surveillance
    
- base de données d’archivage
    
- Base de données de conversation permanente
    
- Base de données de conformité conversation permanente
    
> [!CAUTION]
> Notez que même si vous pouvez colocaliser le partage de fichiers sur ces serveurs, il est primordial de comprendre que cela n’est pas recommandé. Si vous souhaitez colocaliser le partage de fichiers avec un autre rôle de serveur, veillez à surveiller régulièrement l’espace disque ou les problèmes de performances. 
  
### <a name="keep-in-mind"></a>À retenir :

- Vous ne pouvez pas colocaliser un serveur proxy inverse, ce qui n’est pas un Skype pour le composant serveur d’entreprise et ne peut pas être même dans votre topologie. Vous aurez besoin un proxy inverse si vous souhaitez prendre en charge le partage de contenu web pour les utilisateurs fédérés, entre autres. Si vous le souhaitez, continuez et implémenter la prise en charge de proxy inverse pour Skype pour Business Server en configurant un serveur proxy inverse existant qui se trouve déjà dans votre organisation qui est utilisée par d’autres applications.
    
- Vous ne pouvez pas colocaliser un composant de messagerie unifiée Exchange ou un composant de SharePoint Server avec n’importe quel Skype pour le rôle de serveur d’entreprise.
    
## <a name="see-also"></a>Voir aussi

[Topologies de référence pour Skype pour Business Server](reference-topologies.md)