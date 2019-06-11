---
title: Prise en charge du logiciel de base de données Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="442b5-102">Prise en charge du logiciel de base de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="442b5-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="442b5-103">_**Dernière modification de la rubrique:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="442b5-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="442b5-104">Lync Server 2013 prend en charge les systèmes de gestion de base de données suivants:</span><span class="sxs-lookup"><span data-stu-id="442b5-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="442b5-105">**Base de données principale d’un pool frontal, base de données d’archivage, base de données de surveillance, base de données de conversation persistante, et base de données de conformité de la conversation persistante**</span><span class="sxs-lookup"><span data-stu-id="442b5-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="442b5-p101">Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="442b5-108">Microsoft SQL Server 2008 R2 Standard (édition 64 bits).</span><span class="sxs-lookup"><span data-stu-id="442b5-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="442b5-109">Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="442b5-p103">Microsoft SQL Server 2012 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="442b5-p104">Microsoft SQL Server 2012 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="442b5-114">**Bases de données serveur de base de données et serveur frontal Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="442b5-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="442b5-115">Microsoft SQL Server 2012 Express (édition 64 bits).</span><span class="sxs-lookup"><span data-stu-id="442b5-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="442b5-116">Il est également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="442b5-117">Nous prenons en charge l’application de correctifs et la mise à niveau de Microsoft SQL Server sur des serveurs frontaux et des serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="442b5-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="442b5-118">Toutefois, lorsque vous effectuez une mise à niveau ou un correctif sur des serveurs frontaux, vous devez prendre en compte les exigences de quorum.</span><span class="sxs-lookup"><span data-stu-id="442b5-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="442b5-119">Pour plus d’informations, voir [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) et [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="442b5-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="442b5-120">Microsoft SQL Server 2012 Express (64-bit Edition) est installé automatiquement par Lync Server 2013 sur chaque serveur Standard Edition et chaque serveur frontal serveur.</span><span class="sxs-lookup"><span data-stu-id="442b5-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="442b5-121">Lync Server 2013 ne prend pas en charge l’édition 32 bits de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="442b5-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="442b5-122">Vous devez utiliser l’édition 64 bits.</span><span class="sxs-lookup"><span data-stu-id="442b5-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="442b5-123">SQL Server Web Edition et SQL Server Workgroup Edition ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="442b5-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="442b5-124">Vous ne pouvez pas les utiliser avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="442b5-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="442b5-125">Lync Server 2013 prend en charge la mise en miroir de base de données native.</span><span class="sxs-lookup"><span data-stu-id="442b5-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="442b5-126">Pour utiliser le rôle serveur de surveillance, vous devez installer SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="442b5-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="442b5-127">Dans un pool frontal, la base de données principale peut être un ordinateur SQL Server unique.</span><span class="sxs-lookup"><span data-stu-id="442b5-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="442b5-128">Si vous collocate les bases de données Lync Server avec d’autres bases de données, nous vous conseillons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances, et de veiller à ce que, en cas d’échec d’un nœud, le nœud restant puisse gérer le chargement.</span><span class="sxs-lookup"><span data-stu-id="442b5-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="442b5-129">Pour vérifier les capacités de basculement, nous vous recommandons de tester tous les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="442b5-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="442b5-130">Utilisation de la mise en miroir SQL et du clustering SQL</span><span class="sxs-lookup"><span data-stu-id="442b5-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="442b5-131">Lync Server 2013 prend en charge l’utilisation de la mise en miroir SQL ou du regroupement SQL pour chaque base de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="442b5-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="442b5-132">Vous pouvez facilement configurer la mise en miroir SQL à l’aide de l’outil générateur de topologie dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="442b5-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="442b5-133">Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="442b5-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="442b5-134">Lync Server 2013 prend en charge la mise en miroir SQL et la topologie de regroupement SQL pour tous les déploiements, y compris les déploiements Greenfield et les organisations ayant procédé à une mise à niveau à partir de versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="442b5-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="442b5-p111">La prise en charge du clustering SQL concerne les configurations active/passive. Pour des raisons de performance, le nœud passif ne doit pas être partagé par une autre instance SQL.</span><span class="sxs-lookup"><span data-stu-id="442b5-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="442b5-137">La prise en charge suivante est incluse :</span><span class="sxs-lookup"><span data-stu-id="442b5-137">The following support is included:</span></span>

  - <span data-ttu-id="442b5-138">Clustering de basculement à deux nœuds pour les configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="442b5-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="442b5-p112">Microsoft SQL Server 2012 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="442b5-p113">Microsoft SQL Server 2008 R2 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="442b5-143">Clustering de basculement à 16 nœuds maximum pour les configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="442b5-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="442b5-p114">Microsoft SQL Server 2012 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="442b5-p115">Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.</span><span class="sxs-lookup"><span data-stu-id="442b5-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="442b5-148">Pour plus d’informations sur la mise en miroir SQL, voir [disponibilité du serveur principal dans Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="442b5-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="442b5-149">Pour plus d’informations sur le déploiement de la fonction de regroupement SQL, voir [configurer le regroupement SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="442b5-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="442b5-150">Pour plus d’informations et des meilleures pratiques pour la mise en cluster de basculement <http://technet.microsoft.com/en-us/library/hh231721.aspx>dans SQL Server 2012, voir.</span><span class="sxs-lookup"><span data-stu-id="442b5-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="442b5-151">Pour la mise en cluster de basculement dans SQL <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>Server 2008, voir.</span><span class="sxs-lookup"><span data-stu-id="442b5-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

