---
title: 'Lync Server 2013 : fonctionnement de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca026dcfb9b994353de139b6e10ecd419c9dd165
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Fonctionnement de l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

L’archivage de Lync Server 2013 fournit des options qui vous permettent de répondre à vos besoins en matière de conformité. Pour le mettre en œuvre et le mettre à jour de manière à satisfaire les exigences de votre organisation, vous devez comprendre les éléments suivants :

  - Quelles informations peuvent être archivées ;

  - Procédures d’activation et de désactivation de l’archivage dans votre déploiement.

  - Les options d’archivage que vous pouvez configurer pour contrôler l’implémentation de l’archivage.

<div>

## <a name="what-information-can-be-archived"></a>Quelles informations peuvent être archivées ?

Les types de contenu suivants peuvent être archivés :

  - Messages instantanés P2P

  - Conférences (réunions) sous forme de messages instantanés entre plusieurs participants

  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)

  - Tableaux blancs et sondages partagés durant une conférence

Les types de contenu suivants ne sont pas archivés :

  - Transfert de fichiers d’égal à égal

  - Audio/vidéo pour messages instantanés et conférences P2P

  - Partage d’application et de Bureau pour messages instantanés et conférences d’égal à égal

Le serveur Lync n’archive pas non plus les conversations persistantes. Pour archiver des conversations permanentes, vous devez activer et configurer le service de conformité, qui est un composant qui peut être déployé avec Microsoft Lync Server 2013, le serveur de chat permanent. Pour plus d’informations, reportez-vous à [planification du serveur de conversation persistant dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Comment commencer à utiliser l’archivage ?

L’archivage est automatiquement installé sur chaque serveur frontal lors du déploiement du serveur, mais la mise à jour n’est pas activée tant que vous ne l’avez pas configuré. La configuration de celle-ci est déterminée par le déploiement de l’archivage :

  - **Archivage avec l’intégration de Microsoft Exchange.** Si vous avez des utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres ont été placées sur place, vous pouvez sélectionner l’option d’intégration du stockage de Lync Server 2013 avec le stockage Exchange. Si vous choisissez l’option intégration de Microsoft Exchange, vous utilisez les stratégies et configurations Exchange 2013 pour contrôler l’archivage des données de Lync Server 2013 pour ces utilisateurs.

  - **Archivage à l’aide de bases de données d’archivage de Lync Server.** Si vous avez des utilisateurs qui ne sont pas hébergés sur Exchange 2013 ou qui n’ont pas de boîte aux lettres en conservation sur place, ou si vous ne voulez pas utiliser l’intégration de Microsoft Exchange pour tous les utilisateurs ou tous les utilisateurs de votre déploiement, vous pouvez déployer des bases de données d’archivage Lync Server à l’aide de SQL Server.  pour stocker les données d’archivage de ces utilisateurs. Dans ce cas, les stratégies et configurations d’archivage de Lync Server 2013 déterminent l’activation de l’archivage et la façon de l’implémenter. Pour utiliser Lync Server 2013, vous devez ajouter les bases de données SQL Server appropriées à votre topologie et publier la topologie.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Configuration de l’archivage avec l’intégration de Microsoft Exchange

Si vos utilisateurs sont hébergés sur Exchange 2013 et leurs boîtes aux lettres ont été placées sur place, vous pouvez choisir l’option d' **intégration de Microsoft Exchange** (comme décrit plus loin dans cette section) pour archiver Lync Server 2013 pour ces utilisateurs, puis contrôler l’archivage de ces utilisateurs en spécifiant des stratégies de blocage et des paramètres Exchange, ainsi que les configurations de Lync Server pour contrôler les éléments suivants :

  - L’archivage des messages instantanés, des conférences ou les deux.

  - Si vous implémentez le mode critique pour le déploiement de Lync Server.

  - Choix de l’option d’intégration de Microsoft Exchange pour l’utilisation d’Exchange 2013 pour le stockage des données archivées.

Les options de configuration de l’archivage de Lync Server 2013 sont décrites plus loin dans cette section. Pour plus d’informations sur la configuration des stratégies de blocage et des paramètres Exchange pour la prise en charge de l’archivage, voir la documentation du produit Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Configuration de l’archivage lors de l’utilisation du stockage de la base de données d’archivage Lync Server

Si vous voulez utiliser les bases de données d’archivage de Lync Server (à l’aide de bases de données SQL Server) pour archiver des données pour des utilisateurs de votre déploiement, vous pouvez configurer les stratégies d’archivage de Lync Server pour contrôler si l’archivage est activé pour ces utilisateurs. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un ou l’autre des éléments suivants :

  - Communications internes

  - Communications externes

Par défaut, l’archivage n’est pas activé pour des communications internes ou des communications externes dans une stratégie d’archivage Lync Server. Activez et désactivez les communications à l’aide du panneau de configuration de Lync Server 2013 ou de l’utilisation des applets de commande dans Lync Server 2013 Management Shell.

Les stratégies d’archivage de Lync Server 2013 incluent les éléments suivants :

  - **Stratégie d’archivage globale**. Il s’agit de la stratégie d’archivage par défaut qui s’applique à votre déploiement complet. Il est créé lors du déploiement de Lync Server 2013 et, par défaut, désactive l’archivage pour les communications internes et externes. Vous ne pouvez pas supprimer cette stratégie. Si vous choisissez l’option Supprimer, la stratégie globale est réinitialisée aux paramètres par défaut.

  - **Stratégie d’archivage de site**. Si vous le souhaitez, vous pouvez activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une stratégie d’archivage au niveau du site pour le site. Lorsque vous créez une stratégie d’archivage au niveau du site, par défaut, l’archivage n’est pas activé. Vous pouvez supprimer toutes les stratégies d’archivage au niveau du site que vous créez. Une stratégie d’archivage au niveau du site remplace la stratégie globale, mais uniquement pour le site spécifié dans la stratégie. Par exemple, si vous activez l’archivage pour les communications internes et externes dans votre stratégie globale et que vous créez une stratégie de site dans laquelle vous désactivez l’archivage pour les communications externes, seules les communications internes seront archivées pour ce site.

  - **Stratégie d’archivage des utilisateurs**. Si vous le souhaitez, vous pouvez activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, en configurant et en appliquant une stratégie d’archivage au niveau utilisateur pour les utilisateurs et groupes d’utilisateurs spécifiés. Lorsque vous créez une stratégie d’archivage au niveau utilisateur, par défaut, l’archivage n’est pas activé. Vous pouvez supprimer n’importe quelle stratégie d’archivage au niveau utilisateur que vous créez, mais vous pouvez modifier les utilisateurs et le groupe d’utilisateurs auxquels la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels la stratégie est appliquée. Par exemple, si vous désactivez l’archivage pour les communications internes et externes dans votre stratégie globale, créez une stratégie de niveau site dans laquelle vous activez l’archivage des communications internes et externes, puis créez une stratégie de niveau utilisateur dans laquelle vous désactivez Dans le cas d’une archivage pour les communications externes, les communications seront archivées pour les communications internes et externes de tous les utilisateurs du site, à l’exception de celle-ci, pour les utilisateurs auxquels vous appliquez la stratégie de niveau utilisateur, seules les communications internes seront archivées.

Pour plus d’informations sur la configuration des stratégies d’archivage initial lors du déploiement de l’archivage, voir [configuration et affectation de stratégies d’archivage dans Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) dans la documentation de déploiement. Pour plus d’informations sur l’utilisation des stratégies d’archivage pour activer et désactiver les communications après le déploiement, reportez-vous à la rubrique [gestion de l’archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.

<div>


> [!NOTE]  
> Si vous implémentez les bases de données d’archivage Lync Server 2013 et activez l’intégration de Microsoft Exchange, les stratégies Exchange 2013 remplacent les stratégies d’archivage de Lync Server, mais uniquement pour les utilisateurs hébergés sur Exchange 2013 et ayant reçu leurs boîtes aux lettres en conservation inaltérable . L’archivage de Lync dépend de la stratégie de conservation inaltérable de Microsoft Exchange uniquement.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Quelles sont les options de configuration de l’archivage ?

Outre l’utilisation de stratégies et l’activation ou la désactivation de l’archivage, vous disposez d’autres options d’archivage qui peuvent être configurées pour votre déploiement complet et, si vous le souhaitez, pour des sites et des groupes spécifiques. Vous contrôlez la plupart des options d’archivage à l’aide d’une ou de plusieurs configurations d’archivage, qui sont disponibles dans le panneau de configuration de Lync Server 2013, mais disposent également d’une autre option disponible uniquement pour la configuration à l’aide de Lync Server 2013 Management Shell.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Options de configuration de l’archivage disponibles dans le panneau de configuration de Lync Server 2013

Chaque configuration de l’archivage fournit les options suivantes :

La configuration de niveau global est créée automatiquement lors du déploiement de l’archivage et peut être configurée, mais pas supprimée. Si vous sélectionnez l’option de suppression de la configuration globale, les paramètres sont rétablis sur les valeurs par défaut. Vous pouvez créer plusieurs configurations de sites et de pools, ainsi que la configuration globale, des paramètres d’archivage des contrôles. Pour la configuration globale et chaque configuration de site et de pool, vous disposez des options suivantes :

  - Désactivez l’archivage, activez l’archivage uniquement pour la messagerie instantanée ou activez l’archivage des messages instantanés et des conférences.

  - Configurer le mode critique pour bloquer les sessions de messagerie instantanée et de conférence en cas de panne du serveur Lync. Les échecs incluent les éléments suivants :
    
      - **Messagerie instantanée**. Un problème avec le service de stockage de Lync Server. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs activés pour l’archivage.
    
      - **Conferencing**. : il peut s’agir d’un échec lié à un partage de fichiers indisponibles ou à un problème au niveau du service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool lors de l’échec passent en mode restreint, et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.

  - Spécifiez l’utilisation de l’intégration de Microsoft Exchange Server 2013 pour l’utilisation d’Exchange 2013 pour le stockage des données archivées, au lieu de configurer des bases de données SQL Server distinctes pour le stockage des données d’archivage de Lync Server 2013.

  - Configurer les options de purge pour les données archivées Cela inclut la définition du moment où effacer les données archivées, qui peuvent être l’un des éléments suivants :
    
      - Après un nombre spécifique de jours que vous spécifiez
    
      - Après l’exportation des données d’archivage (y compris les données téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Si vous activez l’intégration de Microsoft Exchange, le vidage pour les utilisateurs hébergés sur Exchange 2013 et leurs boîtes aux lettres placés dans la conservation inaltérable sont contrôlés par Exchange. La seule qualification concerne les fichiers de conférence stockés sur le partage de fichiers de Lync Server. Ces fichiers ne sont purgés à partir du partage de fichiers qu’une fois que les fichiers ont été exportés (téléchargés vers Exchange) si vous sélectionnez l’option de purge des données après l’exportation des données d’archivage ou après le nombre maximal de jours spécifié si vous spécifiez un nombre maximal de jours de rétention.

    
    </div>

Par défaut, aucune option d’archivage n’est activée. Vous pouvez gérer les configurations d’archivage à l’aide du panneau de configuration de Lync Server 2013.

Vous pouvez spécifier les configurations d’archivage suivantes :

  - **Configuration de l’archivage global**. Il s’agit de la configuration de l’archivage par défaut qui s’applique à votre déploiement complet. Il est créé lors du déploiement de Lync Server 2013 et, par défaut, ne permet pas la fonctionnalité d’archivage. Vous pouvez modifier la configuration globale sans pouvoir la supprimer. Si vous choisissez l’option Supprimer pour la configuration, la configuration globale est réinitialisée aux paramètres par défaut.

  - **Configuration de l’archivage des sites**. Le cas échéant, vous pouvez configurer l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une configuration d’archivage au niveau du site pour un site individuel. La configuration de l’archivage au niveau du site n’existe que si vous la créez. Vous pouvez modifier ou supprimer toute configuration d’archivage au niveau du site. La configuration de l’archivage au niveau du site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration au niveau du site. Par exemple, si vous activez l’archivage pour la messagerie instantanée uniquement dans votre configuration globale et que vous créez une configuration de site pour l’activation de l’archivage pour les conférences et la messagerie instantanée, les conférences ne seront archivées que pour le site, et non pour le reste de votre organisation.

  - **Configuration de l’archivage du pool**. Si vous le souhaitez, vous pouvez spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour le pool individuel. La configuration de l’archivage au niveau du pool existe uniquement si vous la créez. Vous pouvez modifier et supprimer toute configuration d’archivage au niveau du pool. La configuration de l’archivage au niveau du pool prévaut sur la configuration globale et sur toute configuration de l’archivage de site que vous avez créé. Par exemple, si vous activez l’archivage pour la messagerie instantanée uniquement dans votre configuration globale, créez une configuration au niveau du site dans laquelle vous activez l’archivage pour les conférences de messagerie instantanée et de conférence pour le site, puis créez une configuration au niveau du pool dans laquelle vous activez l’archivage uniquement pour La messagerie instantanée, les communications seront archivées pour tous les utilisateurs du site, à l’exception des utilisateurs hébergés dans le pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, l’archivage ne sera activé que pour la messagerie instantanée.

Pour plus d’informations sur la configuration d’un archivage initial lors du déploiement de l’archivage, voir [Configuration des options d’archivage dans Lync Server 2013](lync-server-2013-configuring-archiving-options.md) dans la documentation de déploiement. Pour plus d’informations sur l’utilisation des stratégies d’archivage pour activer et désactiver les communications après le déploiement, voir [gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation des opérations

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Options d’archivage disponibles uniquement dans Windows PowerShell

À l’aide de Lync Server 2013 Management Shell, vous pouvez utiliser les applets de commande pour implémenter des options qui ne sont pas disponibles dans Lync Server 2013 le panneau de configuration. Les options suivantes sont disponibles :

  - **Archiver des messages en double**. Pour plus d’informations, reportez-vous à [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) et [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) dans la documentation sur les opérations.

  - **Exporter des données archivées**. Pour plus d’informations, voir [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Comment accéder aux données archivées ?

L’accès aux données archivées dépend de l’emplacement où les données sont stockées :

  - **Stockage Microsoft Exchange**. Si vous choisissez l’option intégration Exchange, Lync Server stocke le contenu d’archivage dans le magasin 2013 Exchange pour tous les utilisateurs qui sont hébergés sur Exchange 2013 et qui ont eu accès à leurs boîtes aux lettres en conservation inaltérable. Les données archivées sont stockées dans le dossier éléments récupérables de la boîte aux lettres utilisateur, qui est généralement invisible pour les utilisateurs et ne peut être recherchée que par les utilisateurs disposant d’un rôle de gestion de la **découverte** Exchange. Exchange autorise la recherche et la découverte fédéré, ainsi que SharePoint, s’il est déployé. Pour plus d’informations sur le stockage, la rétention et la découverte des données stockées dans Exchange, voir la documentation Exchange 2013 et SharePoint.

  - **Stockage serveur Lync**. Si vous configurez les bases de données d’archivage Lync Server 2013 pour le stockage des données de Lync Server, Lync Server Deposit archivage content dans les bases de données d’archivage de Lync Server (bases de données SQL Server) pour les utilisateurs qui ne sont pas hébergés sur Exchange 2013 et qui n’ont pas mis en place leurs boîtes aux lettres Blocage sur place. This data is not searchable, but it can be exported to formats that are searchable using other tools. Pour plus d’informations sur l’exportation de données stockées dans les bases de données d’archivage, voir [exporter des données archivées à partir de Lync Server 2013](lync-server-2013-exporting-archived-data.md) dans la documentation des opérations.

Pour plus d’informations sur la façon dont Lync Server 2013 et Exchange 2013 fonctionnent conjointement, voir [prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation de support technique.

</div>

</div>

<span> </span>

</div>

</div>

</div>

