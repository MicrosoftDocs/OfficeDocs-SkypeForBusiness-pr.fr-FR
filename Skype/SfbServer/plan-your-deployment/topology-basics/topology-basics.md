---
title: Notions de base de la topologie pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Résumé: choisissez votre topologie pour Skype entreprise Server. En savoir plus sur la colocalisation du serveur pour Skype entreprise Server.'
ms.openlocfilehash: 064dc9d4f7f5d2a5ac722b3cfae928501b217822
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418010"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Notions de base de la topologie pour Skype entreprise Server

**Résumé:** Choisissez votre topologie pour Skype entreprise Server. En savoir plus sur la colocalisation du serveur pour Skype entreprise Server.

Avant de continuer, vous souhaiterez peut-être savoir que vous planifiez la topologie appropriée pour votre déploiement de Skype entreprise Server. Vous devez commencer par choisir si vous comptez un déploiement local de Skype entreprise Server ou si vous envisagez de le combiner avec un déploiement de Skype entreprise Server Online dans le cas d’un déploiement hybride. Quelle que soit la méthode que vous souhaitez, vous devrez lire davantage, car nous décrivons les topologies locales ici, mais les détails hybrides sont présentés dans leurs sections respectives.

Vous pouvez également voir des exemples de topologies dans des [topologies de référence pour Skype entreprise Server](reference-topologies.md).

## <a name="sites"></a>Sites

Dans Skype entreprise Server, vous définissez des sites sur votre réseau qui contiennent des composants Skype entreprise Server. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que les sites serveur Skype entreprise constituent un concept distinct des sites services de domaine Active Directory et de Microsoft Exchange Server. Il n’est pas nécessaire que les sites de votre serveur Skype entreprise correspondent à vos sites Active Directory.

Skype entreprise Server prend en charge le déploiement local d’un ou de plusieurs sites qui peuvent être mis à l’échelle en fonction de vos besoins en matière de haute disponibilité et de localisation.

Votre déploiement disposera d’au moins un site central (également appelé centre de données, il s’agit d’un centre de données pour tous les serveurs qu’il contient) et chaque site central de votre déploiement dispose d’un serveur Standard Edition Server ou d’au moins un pool frontal Enterprise Edition. Leurs différences sont illustrées dans les options ci-dessous :

- Standard Edition Server inclut une base de données SQL Server Express colocalisée.

- Le pool frontal d’entreprise Edition inclut les éléments suivants:

  - Un ou plusieurs serveurs front-end (idéalement au moins trois pour l’évolutivité), avec un maximum de 12. L’équilibrage de charge sera requis dans le cas de plusieurs serveurs.

  - Serveur principal principal.

Vous obtiendrez plus d’informations sur les rôles serveur plus loin dans cette rubrique.

Outre vos sites centraux, il est possible que vous ayez besoin d’un ou plusieurs sites de succursale associés à votre site central. Ils dépendent du site central pour presque toutes leurs fonctionnalités, donc qu’est-ce que c’est bien?

- Appareil de branchement Survivable qui combine une passerelle de réseau téléphonique commuté (PSTN) et une fonctionnalité de Skype entreprise Server.

- Serveur de succursales survivant, il s’agit d’un serveur exécutant Windows Server sur lequel Skype entreprise Server Registrar et le logiciel serveur de médiation sont installés.

- Passerelle RTC autonome (qui ne fait pas partie de l’appareil de branchement survivant).

- Serveur de médiation autonome ou pool de serveurs de médiation autonomes (si vous ne voulez pas collocate ce rôle avec l’appareil de branchement survivant).

## <a name="whats-in-a-skype-for-business-server-site"></a>Qu’est-ce qu’un site Skype entreprise Server?

Pour plus d’informations, un site central peut également disposer des éléments suivants:

- Plusieurs listes frontales, au sein d’un même domaine ou dans des domaines différents (n’oubliez pas de planifier que tous les serveurs frontaux d’une liste frontale, ainsi que les serveurs dorsaux du pool, doivent se trouver dans le même domaine).

- Plusieurs serveurs Standard Edition.

- Office Web Apps Server, qui est utilisé avec Office Web Apps dans Skype entreprise Server pour partager et afficher des présentations PowerPoint.

- Serveur Edge ou pool de bords (dans un réseau de périmètre). Nécessaire si vous voulez que votre déploiement prenne en charge des partenaires fédérés, la connectivité PIC (Public IM Connectivity), la passerelle XMPP, et l’accès pour un utilisateur distant. Pour plus d’informations, consultez la documentation de planification du serveur Edge.

- Serveur de chat permanent. Utile si vous souhaitez que les utilisateurs participent à des conversations thématiques durables à plusieurs. Pour en savoir plus, voir la rubrique planification du serveur Chat permanent.

- Surveillance. Utilisé pour la prise en charge de la collecte de données pour les conférences audio/vidéo (qualité A/V) et l’enregistrement des détails des appels (CDR) pour les conférences voix et audiovisuelles dans votre déploiement. Cela est expliqué en détail dans la rubrique sur la planification de la surveillance.

- Le réalisateur ou le pool de réalisateurs. Ce n’est pas obligatoire, mais utile si vous souhaitez améliorer la résilience et la redirection des requêtes de l’utilisateur Skype entreprise vers la liste de démarrage de l’utilisateur. Si vous voulez déployer des directeurs, un maximum de 10 par liste est pris en charge. S’il s’agit d’une solution dont vous avez besoin, poursuivez la lecture de la rubrique planification pour les directeurs.

- Proxy inverse. Il ne s’agit pas d’un composant Skype entreprise Server, mais si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés, si vous envisagez de prendre en charge le trafic de mobilité, si vos utilisateurs distants souhaitent utiliser le carnet d’adresses, participer à des réunions, etc., il s’agit d’une information dont vous avez besoin. souhaitez avoir dans votre environnement. Le sujet du serveur proxy inverse vous permet d’extraire des informations supplémentaires lorsque vous êtes prêt.

Vous trouverez plus d’informations sur la colocalisation de ces serveurs plus bas.

Toutes les plages frontales et les serveurs Standard Edition déployés dans votre site central partagent ce qui suit, en supposant que vous les avez déployés:

||||
|:-----|:-----|:-----|
|Pool de directeurs ou de réalisateurs  <br/> |Serveur de médiation autonome ou pool de serveurs de médiation  <br/> |Office Web Apps Server  <br/> |
|Serveur Edge ou pool de bords  <br/> |Serveur de chat permanent ou pool de serveurs de chat permanent  <br/> |Surveillance  <br/> |

Où se trouve le serveur Exchange Unified Messaging (UM) de cette liste? De plus, vous pouvez l’utiliser avec Skype entreprise Server si vous voulez l’intégrer à la messagerie unifiée Exchange, mais qu’il ne s’agit pas d’un composant du site Skype entreprise Server.

Il est possible que vous envisagez de disposer de plusieurs sites centraux et que, si tel est le cas, ils puissent partager les serveurs et rôles suivants, s’ils sont déployés sur votre site central:

|||
|:-----|:-----|
|Serveur de médiation autonome ou pool de serveurs de médiation  <br/> |Serveur Edge ou pool de bords  <br/> |
|Serveur de chat permanent ou pool de serveurs de chat permanent  <br/> |Surveillance  <br/> |

À l’instar de la dernière liste, il n’y a pas de serveur de messagerie unifiée Exchange dans la mesure où il ne fait pas partie du déploiement de Skype entreprise Server, mais il est également dans la même catégorie.

Certains autres composants et options font partie du déploiement.

|||||
|:-----|:-----|:-----|:-----|
|Pare-feu  <br/> |Passerelles PSTN (si Voix en Entreprise est déployé)  <br/> |Serveur de messagerie unifiée Exchange (si vous voulez être intégré à la messagerie unifiée Exchange)  <br/> |Équilibrage de charge DNS  <br/> |
|Programmes d’équilibrage de la charge matérielle  <br/> |Bases de données SQL Server  <br/> |Partages de fichiers  <br/> ||

## <a name="server-roles"></a>Rôles serveur

Chaque serveur exécutant Skype entreprise Server exécute un ou plusieurs rôles serveur. Un rôle serveur est un ensemble défini de fonctionnalités de Skype entreprise Server fournies par ce serveur. Il n’est pas nécessaire de déployer tous les rôles serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.

Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des pools de plusieurs serveurs exécutant tous le même rôle serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Pour la plupart des types de pools dans Skype entreprise Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs du pool. Skype entreprise Server prend en charge à la fois l’équilibrage de charge DNS (Domain Name System) et les équilibreurs de charge matérielle.

### <a name="front-end-server-and-back-end-server"></a>Serveur frontal et serveur principal

Dans Skype entreprise Server Enterprise Edition, le serveur frontal est le rôle serveur principal et exécute plusieurs fonctions de base de Skype entreprise Server. Le serveur frontal, ainsi que les serveurs dorsaux, sont les seuls rôles de serveur requis pour le déploiement de Skype entreprise Server Enterprise Edition.

Un pool frontal est un ensemble de serveurs frontaux configurés de façon identique, ce qui collabore pour fournir des services à un groupe d’utilisateurs communs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.

Le serveur frontal inclut les éléments suivants:

- Enregistrement et authentification des utilisateurs.

- Informations de présence et échange de cartes de visite.

- Services de carnet d’adresses et développement de listes de distribution.

- Fonctionnalités de messagerie instantanée, dont les conférences de messagerie instantanée à plusieurs.

- Conférence web, conférence rendez-vous PSTN et conférence A/V (si déployée).

- L’hébergement d’applications pour les deux applications incluses dans Skype entreprise Server (par exemple, l’application de surveillance des conférences et de Response Group) et les applications tierces.

- Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournissent des métriques relatives à la qualité du contenu multimédia (audio et vidéo) qui traverse votre réseau pour les appels vocaux d’entreprise et les conférences A/V.

- Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.

- Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, reportez-vous à la rubrique [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) dans la documentation de planification.

    Dans Lync Server 2010 et les versions antérieures, la surveillance et l’archivage étaient des rôles serveur distincts, non localisés sur le serveur frontal.

- Services web de conversation permanente, si celle-ci est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.

Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.

Par ailleurs, un serveur frontal du déploiement exécute également le serveur de gestion central, qui gère et déploie les données de configuration de base pour tous les serveurs exécutant Skype entreprise Server. Le serveur de gestion central fournit également Lync Server Management Shell et les fonctionnalités de transfert de fichiers.

Le serveur principal est un serveur de base de données exécutant Microsoft SQL Server qui fournit les services de base de données pour le pool frontal. Les serveurs dorsaux servent de magasins de sauvegarde pour les données d’utilisateur et de conférence du pool, et constituent les principaux magasins pour d’autres bases de données telles que la base de données du groupe de réponse. Vous pouvez utiliser un serveur principal unique, mais la [haute disponibilité du serveur principal dans Skype entreprise Server](../high-availability-and-disaster-recovery/back-end-server.md) est recommandée pour le basculement. Les serveurs dorsaux n’exécutent pas le logiciel Skype entreprise Server.

> [!IMPORTANT]
> Nous déconseillons de collocating bases de données Skype entreprise Server avec d’autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées.

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.

Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.

### <a name="edge-server"></a>Serveur Edge

Edge Server permet à vos utilisateurs de communiquer et de collaborer avec des utilisateurs en dehors des pare-feux de l’organisation. Les utilisateurs externes peuvent inclure les propres utilisateurs de l’organisation qui travaillent actuellement sur le site, les utilisateurs d’organisations de partenaires fédérés et les utilisateurs externes qui ont été invités à participer à des conférences hébergées sur votre déploiement Skype entreprise Server.

Le déploiement de Edge Server permet également aux services de mobilité, qui prennent en charge les fonctionnalités de Lync sur les appareils mobiles. Les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler par le biais d’un numéro de téléphone, de la messagerie vocale et d’appels manqués. La fonctionnalité de mobilité prend également en charge les notifications push pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.

Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour permettre aux utilisateurs de Skype entreprise Server d’ajouter des contacts de partenaires de XMPP pour la messagerie instantanée et la présence.

> [!NOTE]
> Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>serveur de médiation

Le serveur de médiation est un composant nécessaire pour mettre en œuvre la voix entreprise, les appels via le bureau et les conférences rendez-vous. Le serveur de médiation translate les signaux et, dans certaines configurations, les contenus multimédias entre votre infrastructure Skype entreprise Server interne et une passerelle RTC (réseau téléphonique commuté), un PBX IP ou un réseau SIP (Session Initiation Protocol). Vous pouvez exécuter médiation Server en tant que serveur frontal, ou en les séparant par un pool de serveurs de médiation autonome.

Pour plus d’informations, reportez-vous à la rubrique [composant serveur de médiation dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Serveur VIS (Video Interop Server)

Le serveur Video Interop est un nouveau rôle de Skype entreprise Server 2015. Il vous permet d’intégrer votre déploiement de Skype entreprise Server à certaines solutions de VTC (Video Teleconferencing System) tierces. A fait office de intermédiaire entre un système de téléconférence tiers et un déploiement Skype entreprise Server. Pour cette version, le VIS se concentre sur l’interopérabilité avec les systèmes vidéo Cisco/Tandberg.

Pour plus d’informations, reportez-vous à la rubrique [planification du serveur Video Interop dans Skype entreprise Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>directeur

Les directeurs peuvent authentifier les demandes des utilisateurs de Skype entreprise Server, mais ne prennent pas en compte les comptes d’utilisateurs privés ou fournissent des services de présence ou de conférence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux.

### <a name="persistent-chat-server-roles"></a>Rôles de serveur Chat permanent

> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques durables à plusieurs. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.

Les serveurs exécutant Skype entreprise Server Standard Edition peuvent également exécuter une conversation permanente sur le même serveur. Vous ne pouvez pas collocate le serveur frontal de chat permanent avec un serveur frontal Enterprise Edition.

Pour plus d’informations, reportez-vous à la section [planification du serveur de conversation permanente dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Prise en charge de la haute disponibilité et de la récupération d’urgence

Skype entreprise Server offre une haute disponibilité grâce à la redondance du serveur via le regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Skype entreprise Server fournit également des mesures de reprise après sinistre en activant le jumelage de pools. Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte. Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.

Skype entreprise Server prend également en charge plusieurs options de haute disponibilité du serveur principal. Il s’agit des éléments suivants:

- Mise en miroir de bases de données

- Groupes de disponibilité AlwaysOn

- Instances AlwaysOn du cluster de basculement (ICF)

- Clustering SQL avec basculement

Pour plus d’informations sur le jumelage de pools et le serveur principal de haut niveau de disponibilité, voir [prévoir une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Colocalisation du serveur dans Skype entreprise Server

Le terme collocate est déjà utilisé, mais qu’est-ce que cela signifie? Skype entreprise Server vous permet de rechercher des rôles de serveur et des fonctionnalités sur le même serveur, qui est une coexistence ou sur des serveurs différents, mais qui peut prêter à confusion lorsque vous commencez à travailler, et si vous effectuez un serveur Standard Edition ou Enterprise Edition Server. le déploiement (chacun possède ses propres règles). Pour vous aider à planifier, nous sommes en mesure d’inclure des déploiements de serveurs Standard Edition Server et de pool frontal Enterprise Edition (dans la plupart des cas, ces informations sont identiques et dans la mesure où il est différent, il est appelé en particulier).

### <a name="collocation-of-server-roles"></a>Colocalisation des rôles serveur

Pour le moment, le serveur Standard Edition Server possède le rôle colocalisé (configuration supplémentaire est requis), dans la liste frontale Enterprise Edition, ce rôle peut être colocalisé ou déployé sur un serveur distinct:

- Serveur(s)

Ces rôles serveur doivent être individuellement déployés sur un serveur distinct :

- directeur

- Edge

- Serveur VIS (Video Interop Server)

- Office Web Apps

### <a name="databases"></a>Bases de données

Il s’agit de la zone présentant de véritables différences entre les déploiements du serveur Standard Edition et les déploiements de pools de serveurs Enterprise Edition, afin que nous ayons deux sections ci-dessous, suivies par des règles supplémentaires pour les deux.

#### <a name="standard"></a>Standard

Dans la mesure où SQL Server Express est colocalisé sur le serveur Standard Edition Server et ne peut pas être déplacé, c’est vraiment simple. Par ailleurs, si vous déployez le serveur de chat permanent sur un serveur Standard Edition Server, vous pouvez également collocate la conversation permanente et la base de données de conformité de la conversation permanente sur le serveur Standard Edition Server, mais ce n’est pas le cas.

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

Celles-ci ne peuvent pas être colocalisées sur le serveur Standard Edition Server, mais peuvent se trouver sur un serveur de base de données unique:

- base de données de surveillance

- base de données d’archivage

- Toutes les bases de données principales pour une liste frontale Enterprise Edition

#### <a name="enterprise"></a>Enterprise

Les bases de données suivantes peuvent être localisées sur le même serveur SQL principal:

- Base de données principale

- base de données de surveillance

- base de données d’archivage

- Base de données de conversation permanente

- Base de données de compatibilité des conversations permanentes

#### <a name="both"></a>Les deux

À présent, vous devez suivre d’autres règles lors de la collocating de base de données Skype entreprise Server dans une instance SQL unique ou dans plusieurs instances SQL dans la même base de données SQL Server:

- Chaque instance SQL ne peut contenir qu’une seule base de données principale pour un pool frontal Enterprise Edition, une base de données de surveillance unique, une base de données d’archivage unique, une seule base de données de chat permanent et une seule base de données de conformité à la messagerie instantanée.

- Le serveur de base de données ne peut pas prendre en charge plus d’une grappe frontale Enterprise Edition, un serveur exécutant l’archivage, un serveur exécutant la surveillance, une seule base de données de chat permanent et une seule base de données de conformité de la conversation permanente, mais elle peut prendre en charge l’une de chacune que les bases de données utilisent ou non la même instance de SQL Server, ou des instances distinctes de SQL Server.

    > [!NOTE]
    > La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.

### <a name="file-shares"></a>Partages de fichiers

Le partage de fichier peut être sur un serveur distinct ou colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :

- Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition

- base de données de surveillance

- base de données d’archivage

- Base de données de conversation permanente

- Base de données de compatibilité des conversations permanentes

> [!CAUTION]
> Notez que même si vous pouvez colocaliser le partage de fichiers sur ces serveurs, il est primordial de comprendre que cela n’est pas recommandé. Si vous souhaitez colocaliser le partage de fichiers avec un autre rôle de serveur, veillez à surveiller régulièrement l’espace disque ou les problèmes de performances.

### <a name="keep-in-mind"></a>À retenir :

- Vous ne pouvez pas collocate un serveur proxy inverse, qui n’est pas un composant Skype entreprise Server et qui n’est pas encore dans votre topologie. Vous aurez besoin d’un proxy inverse si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés, entre autres. Le cas échéant, lancez-vous et mettez en œuvre la prise en charge du proxy inverse pour Skype entreprise Server en configurant un serveur proxy inverse existant déjà utilisé par d’autres applications.

- Vous ne pouvez pas collocate les composants Exchange UM ou SharePoint Server avec des rôles Skype entreprise Server.

## <a name="see-also"></a>Voir aussi

[Topologies de référence pour Skype entreprise Server](reference-topologies.md)
