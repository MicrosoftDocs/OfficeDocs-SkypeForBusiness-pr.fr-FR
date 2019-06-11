---
title: Rôles serveur Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8c5b052defcdc1d60ef9900c283f9f50b3809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Rôles serveur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

Chaque serveur exécutant Lync Server exécute un ou plusieurs *rôles serveur*. Un rôle serveur est un ensemble défini de fonctionnalités de Lync Server fournies par ce serveur. Vous n’avez pas besoin de déployer tous les rôles de serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.

Même si vous n’êtes pas familiarisé avec les rôles de serveur dans Lync Server, l’outil de planification peut vous guider vers la solution la plus adaptée aux serveurs que vous devez déployer, en fonction des fonctionnalités que vous souhaitez. Cette section fournit une vue d’ensemble des rôles de serveur et des fonctionnalités générales qu’ils fournissent:

  - Serveur Standard Edition

  - Serveur frontal et serveur principal

  - serveur Edge

  - serveur de médiation

  - directeur

  - Serveur frontal de conversation permanente

  - Store permanent (serveur principal de conversation permanente)

  - Magasin de conformité des conversations permanentes (serveur principal de conformité des conversations permanentes)

Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des *pools* de plusieurs serveurs exécutant tous le même rôle serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Pour la plupart des types de pools dans Lync Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs du pool. Lync Server prend en charge à la fois l’équilibrage de charge DNS (Domain Name System) et les équilibreurs de charge matérielle.

<div>

## <a name="standard-edition-server"></a>Serveur Standard Edition

Le serveur Standard Edition est conçu pour les petites organisations et pour les projets pilotes d’organisations de grande envergure. Il permet à de nombreuses fonctionnalités de Lync Server, y compris aux bases de données nécessaires, de s’exécuter sur un seul serveur. Cela vous permet d’utiliser la fonctionnalité de serveur Lync pour un coût inférieur, mais ne fournit pas de véritable solution de haute disponibilité.

Standard Edition Server vous permet d’utiliser la messagerie instantanée, la présence, les conférences et la voix d’entreprise, qui s’exécutent sur un seul serveur.

Pour une solution de grande disponibilité, utilisez Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Serveur frontal et serveur principal

Dans Lync Server Enterprise Edition, le serveur frontal est le rôle serveur principal et exécute de nombreuses fonctions de base de Lync Server. Le serveur frontal, ainsi que les serveurs dorsaux, sont les seuls rôles de serveur requis pour une version de déploiement de Lync Server Enterprise Edition.

Un *pool frontal* est un ensemble de serveurs frontaux configurés de façon identique, ce qui collabore pour fournir des services à un groupe d’utilisateurs communs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.

Le serveur frontal inclut les éléments suivants:

  - Authentification et inscription des utilisateurs

  - Informations de présence et échange de carte de visite

  - Service de carnet d’adresses et extension de liste de distribution

  - Fonctionnalité de messagerie instantanée, y compris les conférences de messagerie instantanée à plusieurs

  - Conférences Web, conférences rendez-vous RTC et conférences A/V (si déployées)

  - L’hébergement d’applications pour les deux applications fournies avec Lync Server (par exemple, l’application de service de conférence et de Response Group) et des applications tierces.

  - Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournissent des métriques relatives à la qualité du contenu multimédia (audio et vidéo) qui traverse votre réseau pour les appels vocaux d’entreprise et les conférences A/V.

  - Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.

  - Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.
    
    Dans Lync Server 2010 et les versions antérieures, la surveillance et l’archivage étaient des rôles serveur distincts, non localisés sur le serveur frontal.

  - Services web de conversation permanente, si celle-ci est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.

Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.

Par ailleurs, un pool frontal du déploiement exécute également le serveur de *gestion central*, qui gère et déploie les données de configuration de base pour tous les serveurs exécutant Lync Server. Le serveur de gestion central fournit également Lync Server Management Shell et les fonctionnalités de transfert de fichiers.

Le serveur principal est un serveur de base de données exécutant Microsoft SQL Server qui fournit les services de base de données pour le pool frontal. Les serveurs dorsaux servent de magasins de sauvegarde pour les données d’utilisateur et de conférence du pool, et constituent les principaux magasins pour d’autres bases de données telles que la base de données du groupe de réponse. Vous pouvez utiliser un serveur principal unique, mais une solution qui utilise la mise en miroir SQL Server est recommandée pour le basculement. Les serveurs dorsaux n’exécutent aucun logiciel serveur Lync.

<div>


> [!IMPORTANT]  
> Nous déconseillons de collocating bases de données Lync Server avec d’autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées.



</div>

Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.

</div>

<div>

## <a name="edge-server"></a>Serveur Edge

Edge Server permet à vos utilisateurs de communiquer et de collaborer avec des utilisateurs en dehors des pare-feux de l’organisation. Les utilisateurs externes peuvent inclure les propres utilisateurs de l’organisation qui travaillent actuellement sur le site, les utilisateurs d’organisations fédérées et les utilisateurs externes qui ont été invités à participer à des conférences hébergées sur le déploiement de Lync Server. Edge Server permet également une connectivité aux services de connectivité PIC, y compris Windows Live, AOL\!, Yahoo et Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>



</div>

Le déploiement de Edge Server permet également aux services de mobilité, qui prennent en charge les fonctionnalités de Lync sur les appareils mobiles. Les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler par le biais d’un numéro de téléphone, de la messagerie vocale et d’appels manqués. La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.

Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour permettre aux utilisateurs de Lync Server 2013 d’ajouter des contacts à partir de partenaires de XMPP (par exemple, Google Talk) pour la messagerie instantanée et la présence.

Pour plus d’informations, reportez-vous à la [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.

</div>

<div>

## <a name="mediation-server"></a>serveur de médiation

Le serveur de médiation est un composant nécessaire pour implémenter les conférences rendez-vous et les conférences rendez-vous. Le serveur de médiation translate les signaux et, dans certaines configurations, les éléments multimédias entre l’infrastructure de votre serveur Lync interne et une passerelle RTC (réseau téléphonique commuté), un PBX IP ou un réseau SIP (Session Initiation Protocol). Vous pouvez exécuter médiation Server en tant que serveur frontal, ou en les séparant par un pool de serveurs de médiation autonome.

Pour plus d’informations, consultez la section [serveur de médiation dans Lync server 2013](lync-server-2013-mediation-server-component.md) dans la documentation de planification.

</div>

<div>

## <a name="director"></a>directeur

Les directeurs peuvent authentifier les demandes des utilisateurs de Lync Server, mais ne prennent pas en compte les comptes d’utilisateurs privés ou fournissent des services de présence ou de conférence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux. Pour plus d’informations, reportez-vous à [la rubrique scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Rôles de serveur Chat permanent

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques durables à plusieurs. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.

Les serveurs exécutant Lync Server Standard Edition peuvent également exécuter une conversation permanente sur le même serveur. Vous ne pouvez pas collocate le serveur frontal de chat permanent avec un serveur frontal Enterprise Edition.

Pour plus d’informations, reportez-vous à la section [planification du serveur de chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Composant serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)  


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

