---
title: 'Lync Server 2013 : Ressources requises pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="bdd10-102">Ressources requises pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd10-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdd10-103">_**Dernière modification de la rubrique:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="bdd10-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="bdd10-104">Une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent nécessitent des ressources supplémentaires en plus de ce qui est en général requis pour une opération complète.</span><span class="sxs-lookup"><span data-stu-id="bdd10-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="bdd10-105">Avant de configurer le serveur de chat permanent pour une haute disponibilité et une reprise après sinistre, assurez-vous que vous disposez des ressources suivantes en plus de ce qui est requis pour l’opération de serveur de chat permanent standard.</span><span class="sxs-lookup"><span data-stu-id="bdd10-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="bdd10-106">Pour plus d’informations sur la configuration, voir [configuration du serveur de chat permanent dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bdd10-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="bdd10-107">Une instance de base de données dédiée située dans le même centre de données physiques dans lequel se trouve le serveur frontal principal du service de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="bdd10-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="bdd10-108">Cette base de données fera office de miroir SQL Server pour la base de données de chat permanent principale.</span><span class="sxs-lookup"><span data-stu-id="bdd10-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="bdd10-109">Vous pouvez également désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir si vous voulez un basculement automatisé vers la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="bdd10-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="bdd10-110">Une instance dédiée de la base de données, située dans l’autre centre de données physique.</span><span class="sxs-lookup"><span data-stu-id="bdd10-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="bdd10-111">Cette base de données sera utilisée en tant que base de données secondaire pour l’envoi du journal SQL Server de la base de données dans le centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="bdd10-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="bdd10-112">Une instance de base de données dédiée à faire office de miroir SQL Server pour la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="bdd10-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="bdd10-113">Vous pouvez éventuellement désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="bdd10-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="bdd10-114">Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="bdd10-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="bdd10-115">Si la conformité de serveur Chat permanent est activée, il est nécessaire d’avoir trois instances de base de données spécialisées supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="bdd10-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="bdd10-116">La distribution de la base de données de chat persiste est identique à celle présentée précédemment.</span><span class="sxs-lookup"><span data-stu-id="bdd10-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="bdd10-117">S’il est possible que la base de données de conformité partage la même instance SQL Server que la base de données de chat persistante, nous recommandons des instances autonomes pour une haute disponibilité et une reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="bdd10-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="bdd10-118">Un partage de fichiers doit être créé et désigné pour les journaux de transactions d’envoi du journal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bdd10-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="bdd10-119">Tous les serveurs SQL dans les centres de données exécutant des bases de données de chat permanent doivent disposer d’un accès en lecture/écriture à ce partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bdd10-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="bdd10-120">Celui-ci n’est pas défini avec un rôle FileStore.</span><span class="sxs-lookup"><span data-stu-id="bdd10-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="bdd10-121">Un partage de fichiers sur le serveur de base de données secondaire servant de dossier de destination pour les journaux de transactions SQL Server copiés à partir du partage de fichiers du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="bdd10-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdd10-122">Les serveurs de chat permanent actifs dans un pool de serveurs de chat permanent doivent résider dans le même fuseau horaire que le pool Lync de saut suivant défini dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="bdd10-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="bdd10-123">Les illustrations suivantes fournissent des exemples sur la façon dont l’intégralité du pool de serveurs de chat permanent peut être configuré dans les deux topologies de pool étiré différentes:</span><span class="sxs-lookup"><span data-stu-id="bdd10-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="bdd10-124">Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante élevée et une latence faible.</span><span class="sxs-lookup"><span data-stu-id="bdd10-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="bdd10-125">Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante faible et une latence élevée.</span><span class="sxs-lookup"><span data-stu-id="bdd10-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="bdd10-126">La figure ci-après illustre une topologie de pool de serveurs de chat permanent étirée dans laquelle les centres de données sont géospatiales avec une bande passante élevée et une latence faible.</span><span class="sxs-lookup"><span data-stu-id="bdd10-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="bdd10-127">**Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante élevée et une latence faible.**</span><span class="sxs-lookup"><span data-stu-id="bdd10-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="bdd10-128">![Examen permanent de configuration du pool de serveurs de conversation HBW] (images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen permanent de configuration du pool de serveurs de conversation HBW")</span><span class="sxs-lookup"><span data-stu-id="bdd10-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="bdd10-129">La figure suivante illustre une topologie de pool de serveurs de chat permanent étirée dans laquelle les centres de données sont géospatiales avec une bande passante faible et une latence élevée.</span><span class="sxs-lookup"><span data-stu-id="bdd10-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="bdd10-130">**Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante faible et une latence élevée.**</span><span class="sxs-lookup"><span data-stu-id="bdd10-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="bdd10-131">![Examen permanent de configuration du pool de serveurs de conversation LBW] (images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen permanent de configuration du pool de serveurs de conversation LBW")</span><span class="sxs-lookup"><span data-stu-id="bdd10-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

