---
title: 'Lync Server 2013 : vue d’ensemble de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a31ef3492ff4c6d0ced3dcf08dd385b7a6801ef6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="f69bd-102">Vue d’ensemble de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f69bd-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f69bd-103">_**Dernière modification de la rubrique :** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="f69bd-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="f69bd-104">L’archivage dans Lync Server 2013 vous permet d’archiver les communications envoyées par le biais de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f69bd-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="f69bd-105">Vous pouvez implémenter l’archivage dans le cadre de votre déploiement initial de Lync Server 2013, ou vous pouvez l’ajouter à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="f69bd-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="f69bd-106">Pour utiliser les bases de données d’archivage Lync Server 2013 (bases de données SQL Server) pour le stockage des données d’archivage, vous utilisez le générateur de topologies pour ajouter les bases de données à votre topologie, puis publiez à nouveau la topologie.</span><span class="sxs-lookup"><span data-stu-id="f69bd-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="f69bd-107">Si tous vos utilisateurs sont hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation inaltérable, il n’est pas nécessaire de mettre à jour votre topologie, mais vous devez uniquement activer l’intégration de Microsoft Exchange pour stocker les données archivées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f69bd-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="f69bd-108">Lorsque vous implémentez l’archivage, vous le configurez de façon à indiquer ce qui est archivé.</span><span class="sxs-lookup"><span data-stu-id="f69bd-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="f69bd-109">Par défaut, rien n’est archivé.</span><span class="sxs-lookup"><span data-stu-id="f69bd-109">By default, nothing is archived.</span></span> <span data-ttu-id="f69bd-110">Vous configurez et gérez l’archivage à l’aide du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f69bd-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="f69bd-111">Vous pouvez implémenter l’archivage pour les communications internes, les communications externes ou les deux.</span><span class="sxs-lookup"><span data-stu-id="f69bd-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="f69bd-112">Vous pouvez configurer les paramètres d’archivage de toute votre organisation, mais également de certains sites, de pools spécifiques et d’utilisateurs et groupes d’utilisateurs en particulier.</span><span class="sxs-lookup"><span data-stu-id="f69bd-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="f69bd-113">Pour plus d’informations sur la détermination des options appropriées pour votre organisation, voir définition de la [Configuration requise pour l’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="f69bd-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="f69bd-114">Pour plus d’informations sur l’implémentation des stratégies et des configurations d’archivage, ainsi que des détails sur les informations pouvant ou non être archivées, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f69bd-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

