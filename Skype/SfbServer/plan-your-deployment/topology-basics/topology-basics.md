---
title: Informations de base sur la topologie pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Résumé : Choisissez votre topologie pour Skype Entreprise Server. En savoir plus sur la cocation de serveur pour Skype Entreprise Server.'
ms.openlocfilehash: 3fae86501dfc0952bfb3fcf43347a1f0c9641536
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012528"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Informations de base sur la topologie pour Skype Entreprise Server

**Résumé :** Choisissez votre topologie pour Skype Entreprise Server. En savoir plus sur la cocation de serveur pour Skype Entreprise Server.

Avant de préparer quoi que ce soit d’autre, vous devez savoir que vous planifiez la topologie la plus à même de déployer Skype Entreprise Server. La première chose que vous devez décider est si vous allez avoir un déploiement local de Skype Entreprise Server, ou si vous comptez combiner cela avec un déploiement Skype Entreprise Server Online dans un déploiement hybride. Dans les deux cas, vous voudrez en savoir plus, car nous allons détailler les topologies sur site ici, mais les détails hybrides sont documentés dans leur propre section.

Vous pouvez également voir des exemples de topologies dans les [topologies](reference-topologies.md)de référence pour Skype Entreprise Server.

## <a name="sites"></a>Sites

Dans Skype Entreprise Server, vous définissez des sites sur votre réseau qui contiennent des composants Skype Entreprise Server. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que les sites Skype Entreprise Server sont un concept distinct des sites des services de domaine Active Directory Microsoft Exchange Server sites. Vos sites Skype Entreprise Server n’ont pas besoin de correspondre à vos sites Active Directory.

Skype Entreprise Server prend en charge le déploiement local d’un ou plusieurs sites qui peuvent être dimensionnés en fonction de vos besoins en matière de haute disponibilité et d’emplacement.

Votre déploiement aura au moins un site central (également appelé centre de données, il s’agit d’un centre de données pour tous les serveurs qu’il contient) et chaque site central de votre déploiement aura un serveur Standard Edition ou au moins un pool frontal Enterprise Edition. Vous pouvez voir les différences dans chaque option ci-dessous :

- Le serveur Standard Edition inclut une base de données SQL Server Express c colloquée.

- Le pool frontal Enterprise Edition inclut :

  - Un ou plusieurs serveurs frontux (idéalement au moins trois, pour l’évolutivité), avec un maximum de douze. L’équilibrage de charge serait requis pour plusieurs serveurs.

  - Un serveur principal distinct.

Vous pourrez en savoir plus sur les différents rôles serveur un peu plus loin dans cette section.

En plus de vos sites centraux, vous pouvez également avoir un ou plusieurs sites de succursale associés à votre site central. Ils dépendent du site central pour presque toutes leurs fonctionnalités. De quoi sont-ils composés exactement ?

- Survivable Branch Appliance, qui combine une passerelle PSTN (réseau téléphonique commuté) avec certaines fonctionnalités de Skype Entreprise Server.

- Survivable Branch Server, il s’agit d’un serveur exécutant Windows Server sur qui le serveur d’inscriptions Skype Entreprise et le logiciel serveur de médiation sont installés.

- Passerelle PSTN autonome (qui ne fait pas partie du Survivable Branch Appliance).

- Serveur de médiation autonome ou pool de serveurs de médiation autonomes (si vous ne souhaitez pas ciser ce rôle avec le Survivable Branch Appliance).

## <a name="whats-in-a-skype-for-business-server-site"></a>Qu’y a-t-il dans un site Skype Entreprise Server ?

Pour en savoir plus, un site central peut également avoir :

- Plusieurs pools frontaux, dans le même domaine ou dans des domaines différents (n’oubliez pas que tous les serveurs frontaux d’un pool frontal, ainsi que les serveurs frontaux du pool, doivent se trouver dans le même domaine).

- Plusieurs serveurs Standard Edition Server.

- Office Web Apps Server, utilisé avec Office Web Apps dans Skype Entreprise Server pour le partage et le rendu de présentations PowerPoint.

- Serveur Edge ou pool edge (dans un réseau de périmètre). Nécessaire si vous souhaitez que votre déploiement prendre en charge les partenaires fédérés, la connectivité DE MESSAGERIE INSTANTANÉE publique, la passerelle XMPP (Extensible Messaging and Presence Protocol) et l’accès des utilisateurs distants. Pour plus d’informations, voir la documentation de planification du serveur Edge.

- Serveur de conversation permanente. Utile si vous souhaitez que les utilisateurs puissent participer à des conversations à plusieurs, basées sur des sujets, qui persistent au fil du temps. Pour plus d’informations, ez dans la rubrique Planification du serveur de conversation permanente.

- Surveillance. Utilisé pour prendre en charge la collecte de données pour la qualité de l’expérience (QoE) audio/vidéo (A/V) et l’enregistrement des détails des appels (CDR) pour les conférences Voix Entreprise et A/V dans votre déploiement. Nous en parlerons en détail dans la rubrique Planification de la surveillance.

- Directeur ou pool directeur. Non obligatoire, mais utile si vous souhaitez améliorer la résilience et activer la redirection des demandes des utilisateurs Skype Entreprise vers le pool d’accueil de l’utilisateur. Si vous souhaitez déployer des directeurs, un maximum de 10 par pool est pris en charge. Si vous en avez besoin, poursuivez la lecture de la rubrique Planification des directeurs.

- Proxy inverse. Il ne s’agit pas d’un composant Skype Entreprise Server, mais si vous souhaitez prendre en charge le partage de contenu web pour les utilisateurs fédérés, si vous avez l’intention de prendre en charge le trafic de mobilité, si vos utilisateurs distants souhaitent utiliser le carnet d’adresses, participer à des réunions, etc., il s’agit d’un élément que vous souhaiterez avoir dans votre environnement. Il existe une rubrique configuration du serveur proxy inverse que vous pouvez consulter pour plus d’informations, lorsque vous êtes prêt.

Vous trouverez ci-dessous des informations supplémentaires sur la cocation de ces serveurs.

Tous les pools frontux et les serveurs Standard Edition Servers déployés sur votre site central partagent les informations suivantes, en supposant que vous les avez déployés :

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|Directeur ou pool directeur   |Serveur de médiation autonome ou pool de serveurs de médiation   |Office Web Apps Server   |
|Serveur ou pool de serveurs Edge   |Serveur de conversation permanente ou pool de serveurs de conversation permanente   |Analyse   |

Où se trouve le serveur de messagerie unifiée Exchange dans cette liste ? Vous pouvez certainement l’utiliser avec Skype Entreprise Server si vous souhaitez l’intégrer à la messagerie un utilisateur Exchange, mais il ne s’agit pas d’un composant du site Skype Entreprise Server, c’est pourquoi nous ne le mentionnons pas ici.

Vous prévoyez peut-être d’avoir plusieurs sites centraux, et si c’est le cas, ils peuvent partager les serveurs et rôles suivants, s’ils sont déployés sur votre site central :

|&nbsp;|&nbsp;|
|:-----|:-----|
|Serveur de médiation autonome ou pool de serveurs de médiation   |Serveur ou pool de serveurs Edge   |
|Serveur de conversation permanente ou pool de serveurs de conversation permanente   |Analyse   |

Tout comme pour la dernière liste, nous n’insérons pas le serveur de messagerie un jour Exchange, car il ne fait pas partie du déploiement de Skype Entreprise Server, mais il se situe également dans la même catégorie ici.

D’autres composants et options sont évidemment disponibles dans les déploiements.

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|
|Pare-feu   |Passerelles PSTN (si vous déployez Voix Entreprise   |Exchange UM Server (si vous souhaitez l’intégrer à la messagerie un peu plus facilement)   |Équilibrage de charge DNS   |
|Programmes d’équilibrage de la charge matérielle   |Bases de données SQL Server   |Partages de fichiers   ||

## <a name="server-roles"></a>Rôles de serveur

Chaque serveur exécutant Skype Entreprise Server exécute un ou plusieurs rôles serveur. Un rôle serveur est un ensemble défini de fonctionnalités Skype Entreprise Server fournies par ce serveur. Vous n’avez pas besoin de déployer tous les rôles serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.

Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des pools de plusieurs serveurs exécutant tous le même rôle serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Pour la plupart des types de pools dans Skype Entreprise Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs du pool. Skype Entreprise Server prend en charge l’équilibrage de la charge DNS (Domain Name System) et les programmes d’équilibrage de la charge matérielle.

### <a name="front-end-server-and-back-end-server"></a>Serveur frontal et serveur principal

Dans Skype Entreprise Server Enterprise Edition, le serveur frontal est le rôle serveur principal et exécute de nombreuses fonctions Skype Entreprise Server de base. Le serveur frontal, ainsi que les serveurs principaux, sont les seuls rôles serveur requis dans un déploiement Skype Entreprise Server Enterprise Edition.

Un pool frontal est un ensemble de serveurs frontaux, configurés à l’identique, qui fonctionnent de pair pour proposer des services à un groupe commun d’utilisateurs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.

Le serveur frontal inclut les fonctionnalités suivantes :

- Authentification et inscription des utilisateurs.

- Informations de présence et échange de carte de visite.

- Services de carnet d’adresses et développement de listes de distribution.

- Fonctionnalité de messagerie instantanée, y compris les conférences de messagerie instantanée à plusieurs.

- Conférence web, conférence RSTN et conférence A/V (si déployée).

- Hébergement d’applications, pour les applications incluses avec Skype Entreprise Server (par exemple, l’application Service de conférence et l’application Response Group) et les applications tierces.

- Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournissent des mesures sur la qualité des médias (audio et vidéo) qui traversent votre réseau pour les appels Voix Entreprise et les conférences A/V.

- Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.

- Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, voir [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) dans la documentation de planification.

    Dans Lync Server 2010 et les versions précédentes, la surveillance et l’archivage étaient des rôles serveur distincts, non cocifiés sur le serveur frontal.

- Services web de conversation permanente, si cette dernière est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.

Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.

En outre, un serveur frontal dans le déploiement exécute également le serveur central de gestion, qui gère et déploie les données de configuration de base sur tous les serveurs exécutant Skype Entreprise Server. Le serveur central de gestion fournit également Lync Server Management Shell et des fonctionnalités de transfert de fichiers.

Les serveurs frontaux sont des serveurs de base de données Microsoft SQL Server qui fournissent les services de base de données pour le pool frontal. Les serveurs principaux servent de magasins de sauvegarde pour les données utilisateur et de conférence du pool, et sont les principaux magasins pour d’autres bases de données telles que la base de données Response Group. Vous pouvez avoir un serveur principal unique, mais la haute disponibilité du serveur principal dans [Skype Entreprise Server](../high-availability-and-disaster-recovery/back-end-server.md) est recommandée pour leover. Les serveurs back end n’exécutent aucun logiciel Skype Entreprise Server serveur.

> [!IMPORTANT]
> Nous vous déconseillons de c Skype Entreprise Server bases de données avec d’autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées.

> [!NOTE]
> SQL La mise en miroir est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.

Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.

### <a name="edge-server"></a>Serveur Edge

Le serveur Edge permet à vos utilisateurs de communiquer et de collaborer avec des utilisateurs en dehors des pare-feu de l’organisation. Ces utilisateurs externes peuvent inclure les utilisateurs de l’organisation qui travaillent actuellement hors site, les utilisateurs d’organisations partenaires fédérées et les utilisateurs externes qui ont été invités à participer à des conférences hébergées sur votre déploiement Skype Entreprise Server.

Le déploiement d’un serveur Edge active également des services de mobilité, lesquels permettent de prendre en charge des fonctionnalités Lync sur des appareils mobiles. Les utilisateurs peuvent employer les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour s’adonner à des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués. La fonctionnalité de mobilité prend également en charge les notifications push pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification qui est envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.

Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour permettre à vos utilisateurs Skype Entreprise Server d’ajouter des contacts de partenaires XMPP pour la messagerie instantanée et la présence.

> [!NOTE]
> Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.

### <a name="mediation-server"></a>Serveur de médiation

Le serveur de médiation est un composant nécessaire pour l’Voix Entreprise, l’appel via le travail et la conférence téléphonique. Le serveur de médiation traduit la signalisation et, dans certaines configurations, les médias entre votre infrastructure Skype Entreprise Server interne et une passerelle de réseau téléphonique commuté (PSTN), ip-PBX ou une session SIP (Session Initiation Protocol). Vous pouvez exécuter le serveur de médiation s’il est colocalisé sur le même serveur que le serveur frontal ou s’il est séparé dans un pool de serveurs de médiation autonome.

Pour plus d’informations, [voir composant serveur de médiation dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Serveur VIS (serveur d’interopérabilité vidéo)

Video Interop Server est un nouveau rôle depuis Skype Entreprise Server 2015. Il vous permet d’intégrer votre déploiement Skype Entreprise Server avec certaines solutions VTC (Video Teleconferencing System) tierces. Un VIS joue le rôle d’intermédiaire entre un système de téléconférence tiers et un Skype Entreprise Server déploiement. Pour cette version, le VIS se concentre sur l’interopérabilité avec les systèmes vidéo Cisco/Tandberg.

Pour plus d’informations, voir [Plan for Video Interop Server in Skype Entreprise Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Directeur

Les directeurs peuvent authentifier Skype Entreprise Server les demandes des utilisateurs, mais ils n’ont pas de comptes d’utilisateur à la maison ou ne fournissent pas de services de présence ou de conférence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux.

### <a name="persistent-chat-server-roles"></a>Rôles serveur de conversation permanente

> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques à plusieurs qui persistent dans le temps. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.

Les serveurs exécutant Skype Entreprise Server Édition Standard peuvent également exécuter la conversation permanente coquetée sur le même serveur. Vous ne pouvez pas cocérer le serveur frontal de conversation permanente Êdition Entreprise serveur frontal.

Pour plus d’informations, voir [Plan for Persistent Chat Server in Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Prise en charge de la haute disponibilité et de la récupération d’urgence

Skype Entreprise Server offre une haute disponibilité par redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Skype Entreprise Server fournit également des mesures de récupération d’urgence en activant le jumelage de pool. Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte. Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.

Skype Entreprise Server prend également en charge plusieurs options pour la haute disponibilité du serveur principal. Elles incluent notamment les éléments suivants :

- Mise en miroir de bases de données

- Groupes de disponibilité AlwaysOn

- Instances de cluster de failover AlwaysOn (FCI)

- SQL clustering deover

Pour plus d’informations sur le jumelage de pool et la haute disponibilité du serveur [principal,](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)voir Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server .

## <a name="server-collocation-in-skype-for-business-server"></a>Cocation de serveur dans Skype Entreprise Server

Nous avons déjà utilisé le terme cocate, mais qu’est-ce que cela signifie ? Skype Entreprise Server vous permet de localiser certains rôles serveur et fonctionnalités sur le même serveur, c’est-à-dire sur des serveurs différents, mais cela peut prêter à confusion lorsque vous démarrez et si vous faites un déploiement de serveur Édition Standard ou Êdition Entreprise (ils sont chacun dotés de leurs propres règles). Pour vous aider dans votre planification, nous allons inclure la cocation de serveur dans les déploiements de serveurs Édition Standard et les déploiements de pool frontal Êdition Entreprise (dans la plupart des cas, ces informations sont identiques et, lorsqu’elles sont différentes, elles sont appelées spécifiquement).

### <a name="collocation-of-server-roles"></a>Cocation des rôles serveur

Le serveur Édition Standard a le rôle suivant céloqueté (une configuration supplémentaire est toutefois requise), alors que dans le pool frontal Êdition Entreprise, ce rôle peut être cocisé ou déployé sur un serveur distinct :

- Médiation

Ces rôles serveur doivent chacun être déployés sur un serveur distinct :

- Directeur

- Microsoft Edge

- Serveur VIS (serveur d’interopérabilité vidéo)

- Office Web Apps

### <a name="databases"></a>Bases de données

Il s’agit du domaine qui présente des différences réelles entre les déploiements de serveurs Édition Standard et les déploiements de pool de serveurs Êdition Entreprise. Nous allons donc avoir deux sections ci-dessous, suivies de règles supplémentaires pour les deux.

#### <a name="standard"></a>Standard

Étant donné SQL Server Express est coqueté sur le serveur Édition Standard et ne peut pas être déplacé, cela est assez simple. En outre, si vous déployez un serveur de conversation permanente sur un serveur Édition Standard, vous pouvez également cérer la conversation permanente et la base de données de conformité de conversation permanente sur le serveur Édition Standard, mais vous n’avez pas besoin de le faire.

> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.

Ceux-ci ne peuvent pas être cocifiés sur le serveur Édition Standard, mais peuvent se trouver sur un seul serveur de base de données :

- Base de données de surveillance

- Base de données d’archivage

- N’importe quelle base de données principale pour Êdition Entreprise pool frontal

#### <a name="enterprise"></a>Entreprise

Les bases de données suivantes peuvent être coclaquées sur le même SQL Server :

- Base de données principale

- Base de données de surveillance

- Base de données d’archivage

- Base de données de conversation permanente

- Base de données de conformité de conversation permanente

#### <a name="both"></a>Les deux

Il existe maintenant des règles supplémentaires à suivre lors de la cocation de bases de données Skype Entreprise Server dans une instance SQL unique ou dans plusieurs instances SQL dans la même base de données SQL Server base de données :

- Chaque instance SQL ne peut contenir qu’une seule base de données principale pour un pool frontal Êdition Entreprise, une seule base de données de surveillance, une seule base de données d’archivage, une seule base de données de conversation permanente et une seule base de données de conformité de conversation permanente.

- Le serveur de base de données ne peut pas prendre en charge plus d’un pool frontal Êdition Entreprise, un serveur exécutant l’archivage, un serveur exécutant la surveillance, une seule base de données de conversation permanente et une base de données de conformité de conversation permanente, mais il peut prendre en charge chacun d’eux, que les bases de données utilisent la même instance de SQL Server ou des instances distinctes de SQL Server.

    > [!NOTE]
    > La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.

### <a name="file-shares"></a>Partages de fichiers

Le partage de fichiers peut se trouver sur un serveur distinct, ou vous pouvez le cocérer sur le même serveur que tout ou partie des fichiers suivants :

- Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition

- Base de données de surveillance

- Base de données d’archivage

- Base de données de conversation permanente

- Base de données de conformité de conversation permanente

> [!CAUTION]
> Notez que bien que vous pouvez céquequer le partage de fichiers sur ces serveurs, il est essentiel de noter que nous ne le recommandons pas. Si vous coloquez le partage de fichiers avec un autre rôle serveur, assurez-vous que vous surveillez régulièrement les problèmes d’espace disque et de performances.

### <a name="keep-in-mind"></a>Gardez à l’esprit

- Vous ne pouvez pas c céquener un serveur proxy inverse, qui n’est pas un composant Skype Entreprise Server, et peut même ne pas se trouver dans votre topologie. Vous aurez besoin d’un proxy inverse si vous souhaitez prendre en charge le partage de contenu web pour les utilisateurs fédérés, entre autres choses. Si nécessaire, allez de l’avant et implémentez la prise en charge du proxy inverse pour Skype Entreprise Server en configurant un serveur proxy inverse existant déjà utilisé par d’autres applications dans votre organisation.

- Vous ne pouvez céquerer aucun Exchange de messagerie un SharePoint serveur avec Skype Entreprise Server rôle.

## <a name="see-also"></a>Voir aussi

[Topologies de référence pour Skype Entreprise Server](reference-topologies.md)