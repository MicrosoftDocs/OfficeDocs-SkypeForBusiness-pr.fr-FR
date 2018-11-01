---
title: Fonctionnement de l’archivage dans Lync Server 2013
TOCTitle: Fonctionnement de l’archivage dans Lync Server 2013
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204900(v=OCS.15)
ms:contentKeyID: 49297215
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnement de l’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-04_

La fonctionnalité d’archivage de Lync Server 2013 fournit des options qui vous permettent de répondre à vos besoins en matière de conformité. Pour l’implémenter et la gérer aussi efficacement que possible en fonction des besoins de votre organisation, vous devez assimiler les aspects suivants :

  - nature des informations pouvant être archivées ;

  - méthode d’activation et de désactivation de l’archivage dans votre déploiement ;

  - options d’archivage que vous pouvez configurer pour contrôler la façon dont l’archivage est implémenté.

## Quelles sont les informations qui peuvent être archivées ?

Les types de contenu suivants peuvent être archivés :

  - Messages instantanés d’égal à égal

  - Conférences (réunions) sous forme de messages instantanés entre plusieurs participants

  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)

  - Tableaux blancs et sondages partagés durant une conférence

Les types de contenu suivants ne sont pas archivés :

  - Transferts de fichiers d’égal à égal

  - Audio/vidéo pour messages instantanés et conférences d’égal à égal

  - Partage d’application et de Bureau pour messages instantanés et conférences d’égal à égal

Lync Server n’archive pas non plus les conversations de type conversation permanente. Pour archiver les conversations de type conversation permanente, vous devez activer et configurer le service de conformité, qui est un composant pouvant être déployé avec Microsoft Lync Server 2013, un serveur de conversations permanentes. Pour plus d’informations, voir [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

## Comment se mettre à utiliser l’archivage ?

L’archivage est automatiquement installé sur chaque serveur frontal quand vous déployez ce dernier. Toutefois, il n’est pas activé tant que vous ne l’avez pas configuré. Le mode de configuration est déterminé par le mode de déploiement de l’archivage :

  - **Archivage à l’aide de l’intégration de Microsoft Exchange.** Si vous avez des utilisateurs hébergés sur Exchange 2013 et si leurs boîtes aux lettres sont placées en archive permanente, vous pouvez sélectionner l’option permettant d’intégrer le stockage de Lync Server 2013 au stockage d’Exchange. Si vous choisissez l’option d’intégration de Microsoft Exchange, vous utilisez les stratégies et configurations d’Exchange 2013 pour contrôler l’archivage des données Lync Server 2013 de ces utilisateurs.

  - **Archivage à l’aide de bases de données d’archivage Lync Server.** Si vous avez des utilisateurs non hébergés sur Exchange 2013 ou si leurs boîtes aux lettres sont placées en archive permanente, ou si vous ne souhaitez pas utiliser l’intégration de Microsoft Exchange pour une partie ou la totalité des utilisateurs de votre déploiement, vous pouvez déployer les bases de données d’archivage de Lync Server via SQL Server afin de stocker les données d’archivage de ces utilisateurs. Dans ce cas, les configurations et les stratégies d’archivage de Lync Server 2013 déterminent si l’archivage est activé et selon quel mode d’implémentation. Pour utiliser Lync Server 2013, vous devez ajouter les bases de données SQL Server appropriées à votre topologie et publier cette dernière.

## Configuration de l’archivage lors de l’utilisation de l’intégration de Microsoft Exchange

Si vos utilisateurs sont hébergés sur Exchange 2013 et si leurs boîtes aux lettres sont placées en archive permanente, vous pouvez choisir l’option d’intégration de **Microsoft Exchange** (comme décrit plus loin dans cette section) afin d’archiver Lync Server 2013 pour ces utilisateurs. Vous pouvez ensuite contrôler l’archivage de ces utilisateurs en spécifiant les paramètres et stratégies de la fonctionnalité d’archive permanente d’Exchange, ainsi que les configurations de Lync Server pour déterminer s’il faut :

  - archiver la messagerie instantanée et/ou les conférences ;

  - implémenter le mode critique pour le déploiement de Lync Server ;

  - sélectionner l’option d’intégration de Microsoft Exchange pour l’utilisation d’Exchange 2013 à des fins de stockage des données archivées.

Ces options de configuration de l’archivage de Lync Server 2013 sont décrites plus loin dans cette section. Pour plus d’informations sur la configuration des paramètres et stratégies de la fonctionnalité d’archive permanente d’Exchange dans le cadre de la prise en charge de l’archivage, voir la documentation du produit Exchange 2013.

## Configuration de l’archivage lors de l’utilisation de l’espace de stockage des bases de données d’archivage de Lync Server

Si vous souhaitez utiliser des bases de données d’archivage Lync Server (à l’aide de bases de données SQL Server) pour archiver les données des utilisateurs de votre déploiement, vous pouvez configurer des stratégies d’archivage Lync Server afin de contrôler si l’archivage est activé pour les utilisateurs. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un ou l’autre des éléments suivants :

  - Communications internes

  - Communications externes

Par défaut, l’archivage n’est pas activé pour les communications internes ou externes, quelle que soit la stratégie d’archivage de Lync Server. Vous activez et désactivez les communications à l’aide du Panneau de configuration Lync Server 2013 ou des applets de commande de Lync Server 2013 Management Shell.

Stratégies d’archivage de Lync Server 2013 :

  - **Stratégie d’archivage globale**. Il s’agit de la stratégie d’archivage par défaut qui s’applique à l’intégralité de votre déploiement. Elle est créée quand vous déployez Lync Server 2013. Par défaut, elle désactive l’archivage des communications internes et externes. Vous ne pouvez pas supprimer cette stratégie. Si vous choisissez l’option de suppression, les paramètres par défaut de la stratégie globale sont réinitialisés.

  - **Stratégie d’archivage de site**. Vous pouvez éventuellement activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une stratégie d’archivage au niveau du site. Quand vous créez une stratégie d’archivage au niveau du site, l’archivage est désactivé par défaut. Vous pouvez supprimer les stratégies d’archivage au niveau du site que vous avez créées. Une stratégie d’archivage au niveau du site remplace la stratégie globale, mais seulement pour le site spécifié dans la stratégie. Par exemple, si vous activez l’archivage des communications internes et externes dans votre stratégie globale et si vous créez une stratégie de site dans laquelle vous désactivez l’archivage des communications externes, seules les communications internes sont archivées pour ce site.

  - **Stratégie d’archivage utilisateur**. Vous pouvez éventuellement activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, en configurant et en appliquant une stratégie d’archivage au niveau de l’utilisateur pour les utilisateurs et groupes d’utilisateurs spécifiés. Quand vous créez une stratégie d’archivage au niveau de l’utilisateur, l’archivage est désactivé par défaut. Vous pouvez supprimer les stratégies d’archivage au niveau de l’utilisateur que vous avez créées. En outre, vous pouvez modifier les utilisateurs et groupes d’utilisateurs auxquels la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau de l’utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et groupes d’utilisateurs auxquels la stratégie est appliquée. Par exemple, si vous désactivez l’archivage des communications internes et externes dans votre stratégie globale, créez une stratégie au niveau du site dans laquelle vous activez l’archivage des communications internes et externes, puis créez une stratégie au niveau de l’utilisateur dans laquelle vous désactivez l’archivage des communications externes. Dans ce cas, les communications internes et externes sont archivées pour tous les utilisateurs du site, sauf pour les utilisateurs auxquels vous appliquez la stratégie au niveau de l’utilisateur, où seules les communications internes sont archivées.

Pour plus d’informations sur la configuration des stratégies d’archivage initiales quand vous déployez l’archivage, voir [Configuration et affectation des stratégies d’archivage](lync-server-2013-configuring-and-assigning-archiving-policies.md) dans la documentation de déploiement. Pour plus d’informations sur l’utilisation de stratégies d’archivage afin d’activer et de désactiver les communications après le déploiement, voir [Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.

> [!NOTE]  
> Si vous implémentez des bases de données d’archivage Lync Server 2013 tout en activant l’intégration de Microsoft Exchange, les stratégies d’Exchange 2013 remplacent les stratégies d’archivage de Lync Server mais uniquement pour les utilisateurs hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente. L’archivage Lync dépend uniquement de la stratégie d’archive permanente de Microsoft Exchange.

## Quelles sont mes options en matière de configuration de l’archivage ?

Outre l’utilisation de stratégies pour activer et désactiver l’archivage, vous disposez d’autres options d’archivage qui peuvent être configurées pour l’intégralité de votre déploiement et, éventuellement, pour des sites et pools spécifiques. Vous contrôlez la plupart des options d’archivage à l’aide d’une ou de plusieurs configurations d’archivage, lesquelles sont disponibles dans le Panneau de configuration Lync Server 2013. Vous disposez également d’une autre option réservée à la configuration via Lync Server 2013 Management Shell.

## Options de configuration d’archivage disponibles dans le Panneau de configuration Lync Server 2013

Chaque configuration d’archivage offre les options suivantes :

La configuration au niveau global est créée automatiquement quand vous déployez l’archivage. Vous pouvez la modifier mais pas la supprimer. Si vous sélectionnez l’option permettant de supprimer la configuration globale, les valeurs par défaut des paramètres sont réinitialisées. Vous pouvez créer plusieurs configurations de sites et de pools qui, avec la configuration globale, permettent de contrôler les paramètres d’archivage. En matière de configuration globale et de configuration de chaque site et pool, vous disposez des options suivantes :

  - Vous pouvez désactiver l’archivage, activer l’archivage uniquement pour la messagerie instantanée ou activer l’archivage pour la messagerie instantanée et les conférences.

  - Vous pouvez configurer le mode critique afin de bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Lync Server. Les défaillances possibles sont les suivantes :
    
      - **Messagerie instantanée**. Il peut s’agir d’un problème au niveau du service de stockage de Lync Server. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs ayant accès à l’archivage.
    
      - **Conférence**. Il peut s’agir d’une défaillance liée à un partage de fichiers non disponible ou à un problème au niveau du service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de la défaillance passent en mode restreint et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.

  - Vous pouvez spécifier l’utilisation de l’intégration de Microsoft Exchange Server 2013 afin d’utiliser Exchange 2013 pour le stockage des données archivées, au lieu de configurer des bases de données SQL Server distinctes pour le stockage des données d’archivage Lync Server 2013.

  - Vous pouvez configurer les options de suppression définitive des données archivées. En outre, vous pouvez spécifier le moment auquel les données archivées doivent être supprimées définitivement :
    
      - après un nombre spécifique de jours, que vous définissez ;
    
      - après l’exportation des données d’archivage (qui incluent les données téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    > [!NOTE]  
    > Si vous activez l’intégration de Microsoft Exchange, la fonctionnalité de suppression définitive pour les utilisateurs hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente est contrôlée par Exchange. La seule exception concerne les fichiers de conférence, qui sont stockés sur le partage de fichiers Lync Server. Ces fichiers ne sont supprimés définitivement du partage de fichiers qu’après avoir été exportés (téléchargés vers Exchange), si vous sélectionnez l’option permettant de supprimer définitivement les données après l’exportation des données d’archivage ou après le nombre maximal de jours spécifié (si vous indiquez un nombre maximal de jours de rétention).

Par défaut, aucune option d’archivage n’est activée. Vous pouvez gérer les configurations d’archivage à l’aide du Panneau de configuration Lync Server 2013.

Vous pouvez spécifier les configurations d’archivage suivantes :

  - **Configuration d’archivage globale**. Il s’agit de la configuration d’archivage par défaut qui s’applique à l’intégralité de votre déploiement. Elle est créée quand vous déployez Lync Server 2013. Par défaut, elle désactive la fonctionnalité d’archivage. Vous pouvez modifier la configuration globale mais pas la supprimer. Si vous choisissez l’option de suppression de la configuration, les paramètres par défaut de la configuration globale sont réinitialisés.

  - **Configuration d’archivage de site**. Vous pouvez éventuellement configurer l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une configuration d’archivage au niveau du site pour un site particulier. Une configuration d’archivage au niveau du site n’existe que si vous la créez. Vous pouvez modifier ou supprimer une configuration d’archivage au niveau du site. La configuration d’archivage au niveau du site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration au niveau du site. Par exemple, si vous activez l’archivage de la messagerie instantanée uniquement dans votre configuration globale et si vous créez une configuration de site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences, ces dernières ne sont archivées que pour le site et non pour le reste de votre organisation.

  - **Configuration d’archivage de pool**. Vous pouvez éventuellement spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour un pool particulier. Une configuration d’archivage au niveau du pool n’existe que si vous la créez. Vous pouvez modifier et supprimer une configuration d’archivage au niveau du pool. Une configuration d’archivage au niveau du pool remplace la configuration globale et les configurations d’archivage de site que vous avez créées. Par exemple, si vous activez uniquement l’archivage de la messagerie instantanée dans votre configuration globale, créez une configuration au niveau du site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences pour le site, puis créez une configuration au niveau du pool dans laquelle vous activez uniquement l’archivage de la messagerie instantanée. Dans ce cas, les communications relatives à la messagerie instantanée et aux conférences sont archivées pour tous les utilisateurs du site à l’exception des utilisateurs hébergés au sein du pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, seul l’archivage de la messagerie instantanée est activé.

Pour plus d’informations sur l’implémentation des configurations d’archivage initiales quand vous déployez l’archivage, voir [Configuration des options d’archivage](lync-server-2013-configuring-archiving-options.md) dans la documentation de déploiement. Pour plus d’informations sur l’utilisation de stratégies d’archivage afin d’activer et de désactiver les communications après le déploiement, voir [Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation des opérations.

## Options d’archivage disponibles uniquement dans Windows PowerShell

Avec Lync Server 2013 Management Shell, vous pouvez utiliser des applets de commande pour implémenter des options qui ne sont pas disponibles dans le Panneau de configuration Lync Server 2013. Ces options sont les suivantes :

  - **Archiver les messages dupliqués**. Pour plus d’informations, voir [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration) et [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) dans la documentation des opérations.

  - **Exporter les données archivées**. Pour plus d’informations, voir [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)

## Comment accéder aux données archivées ?

L’accès aux données archivées dépend de l’emplacement où les données sont stockées :

  - Stockage **Microsoft Exchange**. Si vous choisissez l'option d'intégration Exchange, Lync Server dépose le contenu d'archivage dans le magasin Exchange 2013 pour tous les utilisateurs hébergés sur Exchange 2013, et dont les boîtes aux lettres sont placées en archive permanente. Les données archivées sont stockées dans le dossier Éléments récupérables des boîtes aux lettres des utilisateurs. En règle générale, ce dossier n'est pas visible par les utilisateurs et ne peut faire l'objet de recherches qu'à l'aide d'un rôle Exchange**Gestion de la découverte**. Exchange permet la recherche fédérée et la découverte, tout comme SharePoint, s'il est déployé. Pour plus d'informations sur le stockage, la conservation et la découverte des données stockées dans Exchange, voir la documentation d'Exchange 2013 et SharePoint.

  - **Stockage Lync Server**. Si vous configurez des bases de données d’archivage Lync Server 2013 pour le stockage de données Lync Server, Lync Server dépose le contenu d’archivage dans les bases de données d’archivage Lync Server (bases de données SQL Server) pour les utilisateurs qui ne sont pas hébergés sur Exchange 2013 et dont les boîtes aux lettres ne sont pas placées en archive permanente. Ces données peuvent faire l’objet de recherches mais peuvent également être exportées vers des formats autorisant les recherches à l’aide d’autres outils. Pour plus d’informations sur l’exportation des données stockées dans les bases de données d’archivage, voir [Exportation des données archivées dans Lync Server 2013](lync-server-2013-exporting-archived-data.md) dans la documentation des opérations.

Pour plus d’informations sur l’interaction entre Lync Server 2013 et Exchange 2013, voir [Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation de prise en charge.

