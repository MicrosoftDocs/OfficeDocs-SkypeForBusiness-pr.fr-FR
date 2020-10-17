---
title: 'Lync Server 2013 : fonctionnement de l’archivage'
description: 'Lync Server 2013 : fonctionnement de l’archivage.'
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
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543380"
---
# <a name="how-archiving-works-in-lync-server-2013"></a>Fonctionnement de l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

L’archivage Lync Server 2013 fournit des options pour vous aider à répondre à vos besoins de conformité. Pour mettre en œuvre et assurer la maintenance d’une manière qui répond le mieux aux besoins de votre organisation, vous devez comprendre les éléments suivants :

  - Les informations pouvant être archivées ;

  - Comment activer et désactiver l’archivage dans votre déploiement.

  - Les options d’archivage que vous pouvez configurer pour contrôler la mise en œuvre de l’archivage.

<div>

## <a name="what-information-can-be-archived"></a>Quelles informations peuvent être archivées ?

Les types de contenu suivants peuvent être archivés :

  - Messages instantanés d’égal à égal

  - Conférences (réunions), qui sont des messages instantanés à plusieurs

  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)

  - Tableaux blancs et sondages partagés au cours d’une conférence

Les types de contenu suivants ne sont pas archivés :

  - Transferts de fichiers d’égal à égal

  - Audio/vidéo pour messages instantanés et conférences d’égal à égal

  - Partage d’applications et de bureau pour les messages instantanés d’égal à égal et les conférences

Lync Server n’archive pas non plus les conversations de conversation permanente. Pour archiver les conversations de conversation permanente, vous devez activer et configurer le service de conformité, qui est un composant pouvant être déployé avec Microsoft Lync Server 2013, serveur de conversation permanente. Pour plus d’informations, reportez-vous à la rubrique [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Comment puis-je commencer à utiliser l’archivage ?

L’archivage est automatiquement installé sur chaque serveur frontal lorsque vous déployez le serveur, mais l’archivage n’est pas activé tant que vous ne l’avez pas configuré. La manière dont vous le configurez dépend de la façon dont vous déployez l’archivage :

  - **Archivage à l’aide de l’intégration de Microsoft Exchange.** Si certains de vos utilisateurs sont hébergés sur Exchange 2013 et que leur boîte aux lettres a été mise en attente In-Place, vous pouvez sélectionner l’option permettant d’intégrer le stockage Lync Server 2013 avec le stockage Exchange. Si vous choisissez l’option intégration de Microsoft Exchange, vous utilisez les stratégies et les configurations Exchange 2013 pour contrôler l’archivage des données Lync Server 2013 pour ces utilisateurs.

  - **Archivage à l’aide des bases de données d’archivage Lync Server.** Si certains de vos utilisateurs ne sont pas hébergés sur Exchange 2013 ou si leur boîte aux lettres n’a pas été mise en attente In-Place ou si vous ne souhaitez pas utiliser l’intégration de Microsoft Exchange pour un ou tous les utilisateurs de votre déploiement, vous pouvez déployer les bases de données d’archivage Lync Server à l’aide de SQL Server pour stocker les données d’archivage de ces utilisateurs. Dans ce cas, les stratégies et les configurations d’archivage Lync Server 2013 déterminent si l’archivage est activé et comment il est implémenté. Pour utiliser Lync Server 2013, vous devez ajouter les bases de données SQL Server appropriées à votre topologie et publier la topologie.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Configuration de l’archivage lors de l’utilisation de l’intégration de Microsoft Exchange

Si vos utilisateurs sont hébergés sur Exchange 2013 et que leurs boîtes aux lettres ont été placées en conservation In-Place, vous pouvez choisir l’option **intégration de Microsoft Exchange** (comme décrit plus loin dans cette section) pour archiver Lync Server 2013 pour ces utilisateurs, puis contrôler l’archivage pour ces utilisateurs en spécifiant les stratégies et les paramètres de blocage d’Exchange In-Place, ainsi que les configurations Lync Server :

  - L’archivage de la messagerie instantanée, de la Conférence ou des deux.

  - Implémenter le mode critique pour votre déploiement Lync Server.

  - Sélection de l’option d’intégration de Microsoft Exchange pour utiliser Exchange 2013 pour le stockage des données archivées.

Ces options de configuration de l’archivage Lync Server 2013 sont décrites plus loin dans cette section. Pour plus d’informations sur la configuration des stratégies et paramètres de blocage Exchange In-Place afin de prendre en charge l’archivage, voir la documentation du produit Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Configuration de l’archivage lors de l’utilisation du stockage de base de données d’archivage Lync Server

Si vous souhaitez utiliser des bases de données d’archivage Lync Server (à l’aide de bases de données SQL Server) pour archiver des données pour les utilisateurs de votre déploiement, vous pouvez configurer des stratégies d’archivage Lync Server pour contrôler si l’archivage est activé pour ces utilisateurs. Dans chaque stratégie d’archivage, vous pouvez activer ou désactiver l’archivage pour l’un des éléments suivants ou les deux :

  - Communications internes

  - Communications externes

Par défaut, l’archivage n’est pas activé pour les communications internes ou externes dans les stratégies d’archivage Lync Server. Vous activez et désactivez les communications à l’aide du panneau de configuration Lync Server 2013 ou des applets de commande dans Lync Server 2013 Management Shell.

Les stratégies d’archivage Lync Server 2013 sont les suivantes :

  - **Stratégie d’archivage globale**. Il s’agit de la stratégie d’archivage par défaut qui s’applique à l’ensemble de votre déploiement. Il est créé lorsque vous déployez Lync Server 2013 et, par défaut, désactive l’archivage pour les communications internes et externes. Vous ne pouvez pas supprimer cette stratégie. Si vous choisissez l’option Supprimer, la stratégie globale est réinitialisée aux paramètres par défaut.

  - **Stratégie d’archivage de site**. Vous pouvez également activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une stratégie d’archivage au niveau du site pour le site. Lorsque vous créez une stratégie d’archivage au niveau du site, par défaut, l’archivage n’est pas activé. Vous pouvez supprimer toutes les stratégies d’archivage au niveau du site que vous créez. Une stratégie d’archivage au niveau du site remplace la stratégie globale, mais uniquement pour le site spécifié dans la stratégie. Par exemple, si vous activez l’archivage pour les communications internes et externes dans votre stratégie globale et que vous créez une stratégie de site dans laquelle vous désactivez l’archivage pour les communications externes, seules les communications internes seront archivées pour ce site.

  - **Stratégie d’archivage des utilisateurs**. Si vous le souhaitez, vous pouvez activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, en configurant et en appliquant une stratégie d’archivage au niveau utilisateur pour les utilisateurs et groupes d’utilisateurs spécifiés. Lorsque vous créez une stratégie d’archivage au niveau de l’utilisateur, par défaut, l’archivage n’est pas activé. Vous pouvez supprimer toutes les stratégies d’archivage de niveau utilisateur que vous créez et vous pouvez modifier les utilisateurs et les groupes d’utilisateurs auxquels la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau de l’utilisateur remplace la stratégie globale et toutes les stratégies de site, mais uniquement pour les utilisateurs et groupes d’utilisateurs auxquels la stratégie est appliquée. Par exemple, si vous désactivez l’archivage pour les communications internes et externes dans votre stratégie globale, créer une stratégie au niveau du site pour activer l’archivage des communications internes et externes, puis créer une stratégie au niveau de l’utilisateur dans laquelle vous désactivez l’archivage pour les communications externes, les communications seront archivées pour les communications internes et externes de tous les utilisateurs du site, à l’exception de celle pour les utilisateurs auxquels vous appliquez la stratégie au niveau de l’utilisateur. , seules les communications internes seront archivées.

Pour plus d’informations sur la configuration des stratégies d’archivage initiales lors du déploiement de l’archivage, voir [configure and assigning Archiving Policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) dans la documentation de déploiement. Pour plus d’informations sur l’utilisation des stratégies d’archivage pour activer et désactiver les communications après le déploiement, voir [Managing the Archiving of Internal and External Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.

<div>


> [!NOTE]  
> Si vous implémentez les bases de données d’archivage Lync Server 2013 et que vous activez l’intégration de Microsoft Exchange, les stratégies Exchange 2013 remplacent les stratégies d’archivage de Lync Server, mais uniquement pour les utilisateurs hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en conservation In-Place. L’archivage Lync dépend uniquement de la stratégie de blocage de Microsoft Exchange In-Place.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Quelles sont les options disponibles pour la configuration de l’archivage ?

Outre l’utilisation de stratégies et l’activation et la désactivation de l’archivage, d’autres options d’archivage peuvent être configurées pour l’ensemble de votre déploiement et, éventuellement, pour des sites et des pools spécifiques. Vous contrôlez la plupart des options d’archivage à l’aide d’une ou plusieurs configurations d’archivage, qui sont disponibles dans le panneau de configuration Lync Server 2013, mais disposent également d’une autre option disponible uniquement pour la configuration à l’aide de Lync Server 2013 Management Shell.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Options de configuration de l’archivage disponibles dans le panneau de configuration Lync Server 2013

Chaque configuration d’archivage fournit les options suivantes :

La configuration de niveau global est créée automatiquement lorsque vous déployez l’archivage et peut être configurée, mais pas supprimée. Si vous sélectionnez l’option permettant de supprimer la configuration globale, les paramètres sont réinitialisés aux valeurs par défaut. Vous pouvez créer plusieurs configurations de pool et de site qui, avec la configuration globale, contrôlent les paramètres d’archivage. Pour la configuration globale et pour chaque configuration de site et de pool, vous disposez des options suivantes :

  - Désactivez l’archivage, activez l’archivage uniquement pour la messagerie instantanée ou activez l’archivage de la messagerie instantanée et de la Conférence.

  - Configurez le mode critique pour bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance d’un serveur Lync. Les échecs sont les suivants :
    
      - **Messagerie instantanée**. Un problème avec le service de stockage Lync Server. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs qui ont été activés pour l’archivage.
    
      - **Conférence**. : un échec peut être lié à un partage de fichiers non disponible ou à un problème avec le service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de l’échec basculent en mode restreint et les nouvelles conférences ne peuvent pas être activées.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.

  - Spécifier l’utilisation de l’intégration de Microsoft Exchange Server 2013 pour utiliser Exchange 2013 pour le stockage des données archivées, au lieu de configurer des bases de données SQL Server distinctes pour le stockage des données d’archivage Lync Server 2013.

  - Configurez les options de purge pour les données archivées. Cela inclut la spécification du moment où purger les données archivées, qui peut être l’un des suivants :
    
      - Après un nombre spécifique de jours que vous spécifiez
    
      - Après l’exportation des données d’archivage (ce qui inclut les données téléchargées vers Exchange, si vous activez l’intégration de Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Si vous activez l’intégration de Microsoft Exchange, le vidage pour les utilisateurs hébergés sur Exchange 2013 et leurs boîtes aux lettres placées en conservation In-Place est contrôlé par Exchange. La seule qualification concerne les fichiers de conférence, qui sont stockés sur le partage de fichiers Lync Server. Ces fichiers sont vidés du partage de fichiers une fois seulement que les fichiers ont été exportés (téléchargés vers Exchange) si vous sélectionnez l’option consistant à vider les données après l’exportation des données d’archivage, ou après le nombre maximal de jours spécifié si vous spécifiez un nombre maximal de jours de rétention.

    
    </div>

Par défaut, aucune option d’archivage n’est activée. Vous pouvez gérer les configurations d’archivage à l’aide du panneau de configuration Lync Server 2013.

Vous pouvez spécifier les configurations d’archivage suivantes :

  - **Configuration globale de l’archivage**. Il s’agit de la configuration d’archivage par défaut qui s’applique à l’ensemble de votre déploiement. Il est créé lorsque vous déployez Lync Server 2013 et, par défaut, n’active pas la fonctionnalité d’archivage. Vous pouvez modifier la configuration globale, mais vous ne pouvez pas la supprimer. Si vous choisissez l’option Supprimer pour la configuration, la configuration globale est réinitialisée aux paramètres par défaut.

  - **Configuration de l’archivage de site**. Si vous le souhaitez, vous pouvez configurer l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une configuration d’archivage au niveau du site pour un site individuel. Une configuration d’archivage au niveau du site existe uniquement si vous la créez. Vous pouvez modifier ou supprimer une configuration d’archivage au niveau du site. Une configuration d’archivage au niveau du site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration au niveau du site. Par exemple, si vous activez l’archivage uniquement pour la messagerie instantanée dans votre configuration globale et que vous créez une configuration de site dans laquelle vous activez l’archivage pour la messagerie instantanée et la Conférence, la fonctionnalité de conférence n’est archivée que pour le site, pas pour le reste de votre organisation.

  - **Configuration de l’archivage du pool**. Si vous le souhaitez, vous pouvez spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour le pool individuel. Une configuration d’archivage au niveau du pool n’existe que si vous la créez. Vous pouvez modifier et supprimer toute configuration d’archivage au niveau du pool. Une configuration d’archivage au niveau du pool remplace la configuration globale et toute configuration d’archivage de site que vous avez peut-être créée. Par exemple, si vous activez l’archivage uniquement pour la messagerie instantanée dans votre configuration globale, créez une configuration au niveau du site dans laquelle vous activez l’archivage pour la messagerie instantanée et les conférences pour le site, puis créez une configuration au niveau du pool dans laquelle vous activez l’archivage uniquement pour la messagerie instantanée, les communications seront archivées pour tous les utilisateurs du site, à l’exception des utilisateurs hébergés dans le pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, l’archivage est activé uniquement pour la messagerie instantanée.

Pour plus d’informations sur la configuration des configurations d’archivage initiales lors du déploiement de l’archivage, voir [Configuration des options d’archivage dans Lync Server 2013](lync-server-2013-configuring-archiving-options.md) dans la documentation de déploiement. Pour plus d’informations sur l’utilisation des stratégies d’archivage pour activer et désactiver les communications après le déploiement, voir [Managing Archiving configuration options in Lync Server 2013 for Your Organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation des opérations.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Options d’archivage disponibles uniquement dans Windows PowerShell

À l’aide de Lync Server 2013 Management Shell, vous pouvez utiliser des applets de commande pour implémenter des options qui ne sont pas disponibles dans le panneau de configuration Lync Server 2013. Ces options sont les suivantes :

  - **Archivez les messages en double**. Pour plus d’informations, voir [New-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) et [Set-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) dans la documentation des opérations.

  - **Exportez les données archivées**. Pour plus d’informations, consultez la rubrique [Export-applet csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Comment accéder aux données archivées ?

L’accès aux données archivées dépend de l’emplacement de stockage des données :

  - **Stockage Microsoft Exchange**. Si vous choisissez l’option d’intégration d’Exchange, Lync Server dépose le contenu d’archivage dans le magasin Exchange 2013 pour tous les utilisateurs hébergés sur Exchange 2013, et ceux dont les boîtes aux lettres ont été placées en conservation In-Place. Les données archivées sont stockées dans le dossier éléments récupérables des boîtes aux lettres utilisateur, généralement invisible pour les utilisateurs et ne peuvent être recherchés que par les utilisateurs disposant d’un rôle de gestion de la **découverte** Exchange. Exchange Active la recherche et la découverte fédérées, ainsi que SharePoint, si elle est déployée. Pour plus d’informations sur le stockage, la rétention et la découverte des données stockées dans Exchange, reportez-vous à la documentation Exchange 2013 et SharePoint.

  - **Stockage Lync Server**. Si vous configurez les bases de données d’archivage Lync Server 2013 pour le stockage des données Lync Server, les dépôts Lync Server sont stockés dans les bases de données d’archivage de Lync Server (bases de données SQL Server) pour tous les utilisateurs qui ne sont pas hébergés sur Exchange 2013 et qui n’ont pas leurs boîtes aux lettres placées en conservation In-Place. Ces données ne peuvent pas faire l’objet d’une recherche, mais elles peuvent être exportées dans des formats pouvant faire l’objet d’une recherche à l’aide d’autres outils. Pour plus d’informations sur l’exportation de données stockées dans des bases de données d’archivage, voir [exportation des données archivées à partir de Lync Server 2013](lync-server-2013-exporting-archived-data.md) dans la documentation des opérations.

Pour plus d’informations sur la façon dont Lync Server 2013 et Exchange 2013 fonctionnent ensemble, consultez la rubrique [prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) dans la documentation de prise en charge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

