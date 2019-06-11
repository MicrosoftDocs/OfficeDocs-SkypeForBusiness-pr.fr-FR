---
title: 'Lync Server 2013 : Chemins de migration de serveurs et scénarios de coexistence pris en charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33b2ce878fef53f444e3834e8b1cd40286c24b0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="9a056-102">Chemins de migration de serveurs et scénarios de coexistence pris en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a056-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a056-103">_**Dernière modification de la rubrique:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="9a056-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="9a056-104">Lync Server 2013 prend en charge la migration de l’un des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="9a056-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="9a056-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9a056-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="9a056-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9a056-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="9a056-107">La migration à partir d’un environnement exécutant ces deux versions précédentes n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9a056-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="9a056-108">La migration de versions antérieures, comme Microsoft Office Communications Server 2007 ou Live Communications Server 2005, n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9a056-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="9a056-109">Si votre déploiement précédent incluait une discussion de groupe, vous devez le faire séparément.</span><span class="sxs-lookup"><span data-stu-id="9a056-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="9a056-110">Méthodes de migration</span><span class="sxs-lookup"><span data-stu-id="9a056-110">Migration Methods</span></span>

<span data-ttu-id="9a056-111">La migration de tous les rôles serveur et topologies Lync Server est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9a056-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="9a056-112">Vous pouvez effectuer une migration d’une topologie vers une autre topologie, y compris de Standard Edition Server vers Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="9a056-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="9a056-113">Lync Server 2013 ne prend en charge que la méthode de migration suivante:</span><span class="sxs-lookup"><span data-stu-id="9a056-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="9a056-114">**Migration côte à côte.**</span><span class="sxs-lookup"><span data-stu-id="9a056-114">**Side-by-side migration.**</span></span> <span data-ttu-id="9a056-115">Dans la migration côte à côte, Lync Server 2013 est déployé parallèlement à un déploiement Microsoft Lync Server 2010 ou Office Communications Server 2007 R2, puis transférez des opérations vers les nouveaux serveurs et déplacez les utilisateurs vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a056-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="9a056-116">Cette méthode nécessite des plateformes serveur supplémentaires, notamment du matériel et du logiciel, lors de la migration, et les noms de systèmes et de pools sont différents dans la nouvelle configuration.</span><span class="sxs-lookup"><span data-stu-id="9a056-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="9a056-117">S’il est nécessaire de revenir à la version précédente, vous pouvez basculer les opérations sur les serveurs précédents.</span><span class="sxs-lookup"><span data-stu-id="9a056-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="9a056-118">La migration dans les forêts de services de domaine Active Directory n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9a056-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="9a056-119">Le chemin de migration recommandé est une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="9a056-119">The recommended migration path is a phased approach.</span></span> <span data-ttu-id="9a056-120">Pour plus d’informations sur la migration à partir d’une version précédente, y compris la mise à l’exécution appropriée du déploiement des composants, voir les rubriques suivantes dans la documentation relative à la migration:</span><span class="sxs-lookup"><span data-stu-id="9a056-120">For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="9a056-121">Migration de Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a056-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="9a056-122">Migration d’Office Communications Server 2007 R2 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a056-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="9a056-123">Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9a056-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="9a056-124">Scénarios de coexistence</span><span class="sxs-lookup"><span data-stu-id="9a056-124">Coexistence Scenarios</span></span>

<span data-ttu-id="9a056-125">Lync Server 2013 peut cohabiter avec les composants d’un déploiement de Lync Server 2010 ou d’un déploiement d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9a056-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="9a056-126">Le déploiement simultané de Lync Server 2013 avec Lync Server 2010 et Office Communications Server 2007 R2 (le déploiement simultané de ces trois versions) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9a056-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="9a056-127">Dans le cadre d’une migration par phases dans laquelle un déploiement de Lync Server 2010 ou Office Communications Server 2007 R2 est le plus temporaire avec le nouveau déploiement Lync Server 2013, la prise en charge du routage de version mixte est limitée.</span><span class="sxs-lookup"><span data-stu-id="9a056-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="9a056-128">Pour plus d’informations, voir la documentation relative à la migration.</span><span class="sxs-lookup"><span data-stu-id="9a056-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="9a056-129">Vous devez utiliser des ordinateurs distincts et distincts exécutant Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour vos instances de base de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a056-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="9a056-130">Vous ne pouvez pas utiliser la même instance de SQL Server pour une liste frontale Lync Server 2013 que vous utilisez pour une liste frontale Lync Server 2010 ou Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9a056-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="9a056-131">Si vous définissez et configurez Lync Server 2013 dans le générateur de topologie pour un déploiement qui dispose déjà de Lync Server 2010 ou d’Office Communications Server 2007 R2, le générateur de topologie n’autorise pas la définition d’une instance de Lync Server 2013 déjà utilisée dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="9a056-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="9a056-132">Le générateur de topologie affiche le message suivant pour vous signaler ce problème: «le nom de domaine \[complet SQL Server du\] serveur contient déjà un rôle d’hébergement d’instances SQL».</span><span class="sxs-lookup"><span data-stu-id="9a056-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a056-133">Si vous envisagez de déployer des rôles de serveur nouveaux dans votre déploiement Lync Server 2013, vous devez commencer par mettre à niveau votre déploiement actuel comme décrit dans la documentation de migration et la documentation de déploiement, puis déployer les nouveaux rôles de serveur comme décrit dans documentation et documentation sur le déploiement de la planification.</span><span class="sxs-lookup"><span data-stu-id="9a056-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="9a056-134">Si vous effectuez une migration à partir d’une version précédente de discussion de groupe, migrez-la en dernier, une fois que vous avez terminé le processus de migration de tous les autres composants de Lync Server 2010 ou Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9a056-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="9a056-135">Pour plus d’informations sur les exigences spécifiques de coexistence et sur la coexistence et la migration de Lync Server 2010 ou d’Office Communications Server 2007 R2 et Lync Server 2013, voir [migration de Lync server 2010 vers Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) et [ Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) dans la documentation de migration.</span><span class="sxs-lookup"><span data-stu-id="9a056-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="9a056-136">Pour plus d’informations sur la prise en charge des versions mixtes pour les clients, voir [clients pris en charge dans Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="9a056-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

