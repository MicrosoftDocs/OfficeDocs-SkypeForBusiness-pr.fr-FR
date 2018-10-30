---
title: Rôles serveur Lync Server 2013
TOCTitle: Rôles serveur
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398536(v=OCS.15)
ms:contentKeyID: 49297665
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rôles serveur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-07_

Chaque serveur qui exécute Lync Server exécute un ou plusieurs *rôles serveur* . Un rôle serveur est un ensemble défini de fonctionnalités Lync Server fournies par ce serveur. Il n’est pas nécessaire de déployer tous les rôles serveur disponibles dans votre réseau. Installez seulement ceux qui contiennent la fonctionnalité voulue.

Même si vous ne maîtrisez pas les rôles serveur dans Lync Server, l’outil de planification peut vous aider à trouver la meilleure solution pour les serveurs que vous devez déployer, en fonction des fonctionnalités souhaitées. Cette section propose une brève vue d’ensemble des rôles serveur et des fonctionnalités générales qu’ils fournissent :

  - Serveur Standard Edition

  - Serveur frontal et serveur principal

  - serveur Edge

  - serveur de médiation

  - directeur

  - Serveur frontal de conversation permanente

  - Magasin de conversation permanente (serveur principal de conversation permanente)

  - Magasin de conformité de conversation permanente (serveur principal de conformité de conversation permanente)

Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des *pools* de plusieurs serveurs exécutant tous le même rôle serveur. Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques. Pour la plupart des types de pools dans Lync Server, vous devez déployer un équilibrage de charge pour répartir le trafic entre les différents serveurs du pool. Lync Server prend en charge à la fois l’équilibrage de charge DNS (Domain Name System) et les équilibrages de charge matérielle.

## Serveur Standard Edition

Le serveur Standard Edition est conçu pour les petites organisations et pour les projets pilotes de grandes organisations. Il permet à de nombreuses fonctionnalités de Lync Server, notamment les bases de données nécessaires, de s’exécuter sur un seul serveur. Cela vous permet de disposer des fonctionnalités Lync Server à moindre coût, mais ne vous offre pas de véritable solution à disponibilité élevée.

Le serveur Standard Edition vous permet d’utiliser la messagerie instantanée, la présence, la conférence et Voix Entreprise, toutes ces fonctionnalités s’exécutant sur un seul serveur.

Pour une solution à disponibilité élevée, utilisez Lync Server Enterprise Edition.

## Serveur frontal et serveur principal

Dans Lync Server Enterprise Edition, le serveur frontal est le rôle serveur principal. Il exécute de nombreuses fonctionnalités Lync Server de base. Le serveur frontal, ainsi que les serveurs principaux qui fournissent la base de données, sont les seuls rôles serveur requis dans un déploiement Lync Server Enterprise Edition.

Un *pool frontal* est un ensemble de serveurs frontaux, configurés à l’identique, qui fonctionnent de pair pour proposer des services à un groupe commun d’utilisateurs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.

Le serveur frontal inclut les fonctionnalités suivantes :

  - Enregistrement et authentification des utilisateurs

  - Informations de présence et échange de cartes de visite

  - Services de carnet d’adresses et développement de listes de distribution

  - Fonctionnalités de messagerie instantanée, dont les conférences de messagerie instantanée à plusieurs

  - Conférence web, conférence rendez-vous RTC et conférence A/V (si déployée)

  - Hébergement d’applications, à la fois pour les applications incluses dans Lync Server (par exemple, Intendant Conférence et application Response Group) et pour les applications tierces

  - Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER). Ces informations fournissent des mesures sur la qualité des médias (audio et vidéo) qui traversent votre réseau à la fois pour les appels Voix Entreprise et les conférences A/V.

  - Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.

  - Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité. Pour plus d’informations, reportez-vous à [Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.
    
    Dans Lync Server 2010 et ses versions antérieures, la surveillance et l’archivage étaient des rôles serveur distincts, non colocalisés sur un serveur frontal.

  - Services web de conversation permanente, si cette dernière est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.

Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.

De plus, un pool frontal dans le déploiement exécute également le *serveur de gestion centralisée* , qui gère et déploie les données de configuration de base sur tous les serveurs exécutant Lync Server. Le serveur de gestion centralisée fournit également Lync Server Management Shell et des fonctions de transfert de fichiers.

Les serveurs principaux sont des serveurs de base de données exécutant Microsoft SQL Server qui fournissent les services de base de données pour le pool frontal. Les serveurs principaux servent de magasins de stockage pour les données utilisateurs et de conférence du pool. Ils constituent les magasins principaux des autres bases de données telles que la base de données Response Group. Vous pouvez disposer d’un seul serveur principal, mais une solution qui utilise la mise en miroir SQL Server est recommandée pour le basculement. Les serveurs principaux n’exécutent aucun logiciel Lync Server.

> [!IMPORTANT]  
> Il n’est pas recommandé de colocaliser des bases de données Lync Server avec d’autres bases de données. Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées.

Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.

## serveur Edge

Le serveur Edge permet aux utilisateurs de communiquer et de collaborer avec les utilisateurs qui se trouvent à l’extérieur du pare-feu de l’entreprise. Ces utilisateurs externes peuvent inclure les propres utilisateurs de l’entreprise qui travaillent actuellement hors site, les utilisateurs des organisations de partenaires fédérés et les utilisateurs extérieurs qui ont été invités à joindre les conférences hébergées sur votre déploiement Lync Server. Le serveur Edge active également la connectivité vers les services PIC (Public IM Connectivity), notamment Windows Live, AOL, Yahoo\! et Google Talk.

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


Le déploiement d’un serveur Edge active également des services de mobilité, lesquels permettent de prendre en charge des fonctionnalités Lync sur des appareils mobiles. Les utilisateurs peuvent employer les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour s’adonner à des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués. La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.

Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux. Vous pouvez configurer ces composants XMPP pour permettre à vos utilisateurs Lync Server 2013 d’ajouter des contacts provenant de partenaires XMPP (tels que Google Talk) pour la messagerie instantanée et la présence.

Pour plus d’informations, reportez-vous à [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.

## serveur de médiation

Le serveur de médiation est un composant nécessaire pour la mise en œuvre de Voix Entreprise et de la conférence rendez-vous. Le serveur de médiation convertit la signalisation, et dans certaines configurations, le média entre votre infrastructure Lync Server interne et une passerelle de réseau téléphonique commuté (RTC), un système PBX IP ou une jonction SIP. Vous pouvez exécuter le serveur de médiation s’il est colocalisé sur le même serveur que le serveur frontal ou s’il est séparé dans un pool de serveurs de médiation autonome.

Pour plus d’informations, reportez-vous à [Composant Serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md) dans la documentation de planification.

## directeur

Les directeurs peuvent authentifier les demandes d’utilisateurs Lync Server, mais ils n’hébergent pas les comptes d’utilisateur et ne fournissent pas de services de présence ni de conférence. Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes. Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes. En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux. Pour plus d’informations, reportez-vous à [Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

## Rôles serveur de conversations permanentes

La conversation permanente permet aux utilisateurs de participer à des conversations thématiques à plusieurs qui persistent dans le temps. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.

Les serveurs qui exécutent Lync ServerStandard Edition peuvent également exécuter la conversation permanente si elle est colocalisée sur le même serveur. Vous ne pouvez pas colocaliser le serveur frontal de conversation permanente avec un serveur frontalEnterprise Edition.

Pour plus d’informations, reportez-vous à la section [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

## Voir aussi

#### Concepts

[Composant Serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)  

#### Autres ressources

[Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)

