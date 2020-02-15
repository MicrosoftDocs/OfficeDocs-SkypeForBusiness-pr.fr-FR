---
title: Rôles serveur Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Rôles serveur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

Chaque serveur exécutant Lync Server exécute un ou plusieurs *rôles serveur*. Un rôle serveur est un ensemble défini de fonctionnalités Lync Server fournies par ce serveur. Il n’est pas nécessaire de déployer tous les rôles serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.

Même si vous n’êtes pas familiarisé avec les rôles serveur dans Lync Server, l’outil de planification peut vous aider à obtenir la meilleure solution pour les serveurs que vous devez déployer, en fonction des fonctionnalités que vous souhaitez. Cette section propose une brève vue d’ensemble des rôles serveur et des fonctionnalités générales qu’ils fournissent :

  - Serveur Standard Edition

  - Serveur frontal et serveur principal

  - Serveur Edge

  - Serveur de médiation

  - 48000b

  - Serveur frontal de conversation permanente

  - Magasin de conversation permanente (serveur principal de conversation permanente)

  - Magasin de conformité de conversation permanente (serveur principal de conformité de conversation permanente)

Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des *pools* de plusieurs serveurs exécutant tous le même rôle serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Pour la plupart des types de pools dans Lync Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs du pool. Lync Server prend en charge l’équilibrage de charge DNS (Domain Name System) et les programmes d’équilibrage de la charge matérielle.

<div>

## <a name="standard-edition-server"></a>Serveur Standard Edition

Le serveur Standard Edition est conçu pour les petites organisations et pour les projets pilotes de grandes organisations. Il permet à de nombreuses fonctionnalités de Lync Server, y compris les bases de données nécessaires, de s’exécuter sur un seul serveur. Cela vous permet de disposer des fonctionnalités de Lync Server pour un coût réduit, mais ne fournit pas une véritable solution de haute disponibilité.

Standard Edition Server vous permet d’utiliser la messagerie instantanée, la présence, les conférences et voix entreprise, qui s’exécutent toutes sur un serveur.

Pour une solution à haute disponibilité, utilisez Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Serveur frontal et serveur principal

Dans Lync Server Enterprise Edition, le serveur frontal est le rôle serveur principal et exécute de nombreuses fonctions Lync Server de base. Le serveur frontal, ainsi que les serveurs principaux, sont les seuls rôles de serveur requis dans n’importe quel déploiement Lync Server Enterprise Edition.

Un *pool frontal* est un ensemble de serveurs frontaux, configurés à l’identique, qui fonctionnent de pair pour proposer des services à un groupe commun d’utilisateurs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.

Le serveur frontal inclut les fonctionnalités suivantes :

  - Enregistrement et authentification des utilisateurs

  - Informations de présence et échange de cartes de visite

  - Services de carnet d’adresses et développement de listes de distribution

  - Fonctionnalités de messagerie instantanée, y compris les conférences de messagerie instantanée à plusieurs

  - Conférence web, conférence rendez-vous PSTN et conférence A/V (si déployée)

  - Hébergement d’applications, pour les deux applications incluses dans Lync Server (par exemple, application de service de conférence et de groupe de réponse) et applications tierces

  - Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournissent des mesures sur la qualité des médias (audio et vidéo) qui traversent votre réseau pour les appels voix entreprise et les conférences A/V.

  - Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.

  - Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, reportez-vous à la rubrique [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.
    
    Dans Lync Server 2010 et les versions antérieures, la surveillance et l’archivage étaient des rôles serveur distincts, non colocalisés sur un serveur frontal.

  - Services web de conversation permanente, si cette dernière est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.

Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.

De plus, un pool frontal dans le déploiement exécute également le *serveur de gestion centralisée*, qui gère et déploie les données de configuration de base sur tous les serveurs exécutant Lync Server. Le serveur de gestion centralisée fournit également Lync Server Management Shell et les fonctionnalités de transfert de fichiers.

Les serveurs principaux sont des serveurs de base de données exécutant Microsoft SQL Server qui fournissent les services de base de données pour le pool frontal. Les serveurs principaux servent de magasins de sauvegarde pour les données utilisateur et de conférence du pool, et sont les magasins principaux pour d’autres bases de données telles que la base de données de groupes Response Group. Vous pouvez avoir un seul serveur principal, mais une solution qui utilise la mise en miroir SQL Server est recommandée pour le basculement. Les serveurs principaux n’exécutent aucun logiciel Lync Server.

<div>


> [!IMPORTANT]  
> Nous ne recommandons pas les bases de données colocaliser Lync Server avec d’autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées.



</div>

Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.

</div>

<div>

## <a name="edge-server"></a>Serveur Edge

Le serveur Edge permet à vos utilisateurs de communiquer et de collaborer avec des utilisateurs à l’extérieur des pare-feu de l’organisation. Ces utilisateurs externes peuvent inclure les utilisateurs de l’organisation qui travaillent actuellement hors site, les utilisateurs des organisations de partenaires fédérés et les utilisateurs externes qui ont été invités à participer à des conférences hébergées sur votre déploiement Lync Server. Le serveur Edge permet également la connectivité aux services de connectivité de messagerie instantanée publique, y compris\!Windows Live, AOL, Yahoo et Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>



</div>

Le déploiement d’un serveur Edge active également des services de mobilité, lesquels permettent de prendre en charge des fonctionnalités Lync sur des appareils mobiles. Les utilisateurs peuvent employer les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour s’adonner à des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués. La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification qui est envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.

Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour permettre à vos utilisateurs Lync Server 2013 d’ajouter des contacts à partir de partenaires XMPP (tels que Google Talk) pour la messagerie instantanée et la présence.

Pour plus d’informations, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.

</div>

<div>

## <a name="mediation-server"></a>Serveur de médiation

Le serveur de médiation est un composant nécessaire pour la mise en œuvre de voix entreprise et de conférences rendez-vous. Le serveur de médiation traduit la signalisation et, dans certaines configurations, les médias entre votre infrastructure Lync Server interne et une passerelle RTC (Public Switched Telephone Network), un système IP-PBX ou une jonction SIP (Session Initiation Protocol). Vous pouvez exécuter le serveur de médiation s’il est colocalisé sur le même serveur que le serveur frontal ou s’il est séparé dans un pool de serveurs de médiation autonome.

Pour plus d’informations, reportez-vous à [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) dans la documentation de planification.

</div>

<div>

## <a name="director"></a>48000b

Les directeurs peuvent authentifier les demandes des utilisateurs de Lync Server, mais ils ne disposent pas de comptes d’utilisateurs personnels ou fournissent des services de présence ou de conférence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux. Pour plus d’informations, reportez-vous à [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Rôles de serveur de conversation permanente

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques à plusieurs qui persistent dans le temps. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.

Les serveurs exécutant Lync Server Standard Edition peuvent également exécuter la conversation permanente sur le même serveur. Vous ne pouvez pas colocaliser le serveur frontal de conversation permanente avec un serveur frontal Enterprise Edition.

Pour plus d’informations, reportez-vous à la rubrique [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Composant de serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

