---
title: Prise en charge des logiciels de base de données Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da1ffd79ccfb652c0f853cb027577d477a14d33e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="4106c-102">Prise en charge du logiciel de base de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4106c-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4106c-103">_**Dernière modification de la rubrique :** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="4106c-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="4106c-104">Lync Server 2013 prend en charge les systèmes de gestion de bases de données suivants :</span><span class="sxs-lookup"><span data-stu-id="4106c-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="4106c-105">**Base de données principale d’un pool frontal, base de données d’archivage, base de données de surveillance, base de données de conversation persistante, et base de données de conformité de la conversation persistante**</span><span class="sxs-lookup"><span data-stu-id="4106c-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="4106c-p101">Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4106c-p102">Microsoft SQL Server 2008 R2 Standard (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-p102">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4106c-p103">Microsoft SQL Server 2012 Enterprise (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4106c-p104">Microsoft SQL Server 2012 Standard (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="4106c-114">**Base de données du serveur Standard Edition et bases de données du serveur frontal**</span><span class="sxs-lookup"><span data-stu-id="4106c-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="4106c-115">Microsoft SQL Server 2012 Express (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="4106c-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="4106c-116">L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="4106c-117">Nous prenons en charge l’application de correctifs et la mise à niveau de Microsoft SQL Server sur les serveurs frontaux et les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4106c-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="4106c-118">Toutefois, lorsque vous effectuez une mise à niveau ou un correctif sur des serveurs frontaux, vous devez tenir compte des exigences en matière de quorum.</span><span class="sxs-lookup"><span data-stu-id="4106c-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="4106c-119">Pour plus d’informations, reportez-vous [à mise à niveau ou mise à jour des serveurs frontaux dans Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) et [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="4106c-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4106c-120">Microsoft SQL Server 2012 Express (64-bit Edition) est automatiquement installé par Lync Server 2013 sur chaque serveur Standard Edition et chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="4106c-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4106c-121">Lync Server 2013 ne prend pas en charge l’édition 32 bits de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4106c-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="4106c-122">Vous devez utiliser l’édition 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4106c-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="4106c-123">SQL Server Web Edition et SQL Server Workgroup Edition ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4106c-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="4106c-124">Vous ne pouvez pas les utiliser avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4106c-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="4106c-125">Lync Server 2013 prend en charge la mise en miroir native des bases de données.</span><span class="sxs-lookup"><span data-stu-id="4106c-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="4106c-126">Pour utiliser le rôle serveur de surveillance, vous devez installer SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="4106c-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4106c-127">Dans un pool frontal, la base de données principale peut être un seul ordinateur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4106c-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4106c-128">Si vous colocaliser des bases de données Lync Server avec d’autres bases de données, nous vous recommandons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances, et de s’assurer qu’en cas de défaillance d’un nœud, le reste du nœud peut gérer la charge.</span><span class="sxs-lookup"><span data-stu-id="4106c-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="4106c-129">Pour vérifier les capacités de basculement, nous vous recommandons de tester tous les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="4106c-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="4106c-130">Utilisation de la mise en miroir SQL et du clustering SQL</span><span class="sxs-lookup"><span data-stu-id="4106c-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="4106c-131">Lync Server 2013 prend en charge l’utilisation de la mise en miroir SQL ou du clustering SQL pour chaque base de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4106c-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="4106c-132">Vous pouvez facilement configurer la mise en miroir SQL à l’aide de l’outil générateur de topologies dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4106c-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="4106c-133">Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="4106c-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="4106c-134">Lync Server 2013 prend en charge les topologies de mise en miroir SQL et de clustering SQL pour tous les déploiements, y compris les déploiements et les organisations déploiements qui ont été mis à niveau à partir de versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4106c-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="4106c-135">La prise en charge de la mise en cluster SQL est pour une configuration active/passive.</span><span class="sxs-lookup"><span data-stu-id="4106c-135">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="4106c-136">Pour des raisons de performances, le nœud passif ne doit pas être partagé par une autre instance SQL.</span><span class="sxs-lookup"><span data-stu-id="4106c-136">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="4106c-137">La prise en charge suivante est incluse :</span><span class="sxs-lookup"><span data-stu-id="4106c-137">The following support is included:</span></span>

  - <span data-ttu-id="4106c-138">Clustering de basculement à deux nœuds pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4106c-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="4106c-139">Microsoft SQL Server 2012 Standard (édition 64 bits).</span><span class="sxs-lookup"><span data-stu-id="4106c-139">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="4106c-140">L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-140">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4106c-141">Microsoft SQL Server 2008 R2 Standard (édition 64 bits).</span><span class="sxs-lookup"><span data-stu-id="4106c-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="4106c-142">L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-142">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="4106c-143">Clustering de basculement à seize nœuds pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4106c-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="4106c-144">Microsoft SQL Server 2012 Enterprise (édition 64 bits).</span><span class="sxs-lookup"><span data-stu-id="4106c-144">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="4106c-145">L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-145">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4106c-146">Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits).</span><span class="sxs-lookup"><span data-stu-id="4106c-146">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="4106c-147">L’exécution du Service Pack le plus récent est également recommandée.</span><span class="sxs-lookup"><span data-stu-id="4106c-147">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="4106c-148">Pour plus d’informations sur la mise en miroir SQL, reportez-vous à la rubrique [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="4106c-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="4106c-149">Pour plus d’informations sur le déploiement du clustering SQL, reportez-vous à [configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="4106c-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="4106c-150">Pour plus d’informations et les meilleures pratiques pour le clustering de basculement dans <http://technet.microsoft.com/library/hh231721.aspx>SQL Server 2012, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="4106c-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="4106c-151">Pour le clustering de basculement dans SQL Server <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>2008, reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="4106c-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

