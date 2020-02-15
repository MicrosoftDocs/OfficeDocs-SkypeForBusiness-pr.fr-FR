---
title: 'Lync Server 2013 : ressources requises pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9917e6eca4780ec415d2750a8e36d06946130137
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="dcd8f-102">Ressources requises pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcd8f-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcd8f-103">_**Dernière modification de la rubrique :** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="dcd8f-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="dcd8f-104">La haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente nécessitent des ressources supplémentaires au-delà de ce qui est généralement nécessaire pour une exploitation complète.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="dcd8f-105">Avant de configurer le serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence, vérifiez que vous disposez des ressources suivantes en plus des éléments requis pour le fonctionnement du serveur de conversation permanente standard.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="dcd8f-106">Pour plus d’informations sur la configuration, reportez-vous à la rubrique [Configuring persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="dcd8f-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="dcd8f-107">Une instance de base de données dédiée située dans le centre de données physique dans lequel se trouve le serveur frontal du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="dcd8f-108">Cette base de données servira de miroir SQL Server pour la base de données de conversation permanente principale.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="dcd8f-109">Vous pouvez également désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir si vous souhaitez un basculement automatisé vers la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="dcd8f-110">Une instance dédiée de la base de données, située dans l’autre centre de données physique.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="dcd8f-111">Cette base de données servira de base de données secondaire de copie des journaux de transaction SQL Server pour la base de données dans le centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="dcd8f-112">Une instance de base de données dédiée servant de miroir SQL Server pour la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="dcd8f-113">Si vous le souhaitez, désignez un serveur SQL Server supplémentaire comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="dcd8f-114">Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="dcd8f-115">Si la conformité du serveur de conversation permanente est activée, trois instances de base de données dédiées supplémentaires sont requises.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="dcd8f-116">Leur distribution est identique à celles précédemment décrites pour la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="dcd8f-117">Bien qu’il soit possible pour la base de données de conformité de partager la même instance SQL Server que la base de données de conversation permanente, nous vous recommandons des instances autonomes pour la haute disponibilité et la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="dcd8f-118">Un partage de fichiers doit être créé et désigné pour les journaux de transactions de la copie des journaux de transaction SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="dcd8f-119">Tous les serveurs SQL dans les deux centres de données qui exécutent des bases de données de conversation permanente doivent disposer d’un accès en lecture/écriture à ce partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="dcd8f-120">Il n’est pas défini avec un rôle FileStore.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="dcd8f-121">Un partage de fichiers sur le serveur de base de données secondaire servant de dossier de destination pour les journaux de transaction SQL Server qui sont copiés à partir du partage de fichiers du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dcd8f-122">Les serveurs de conversation permanente actifs dans un pool de serveurs de conversation permanente doivent résider dans le même fuseau horaire que le pool Lync de tronçon suivant défini dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="dcd8f-123">Les figures suivantes fournissent des exemples sur la façon dont l’intégralité du pool de serveurs de conversation permanente peut être configurée dans les deux topologies de pools étirées différentes :</span><span class="sxs-lookup"><span data-stu-id="dcd8f-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="dcd8f-124">Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="dcd8f-125">Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="dcd8f-126">La figure suivante illustre une topologie de pool de serveurs de conversation permanente étirée où les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="dcd8f-127">**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.**</span><span class="sxs-lookup"><span data-stu-id="dcd8f-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="dcd8f-128">![Examen de configuration du pool de serveurs de conversation permanente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuration du pool de serveurs de conversation permanente HBW")</span><span class="sxs-lookup"><span data-stu-id="dcd8f-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="dcd8f-129">La figure suivante illustre une topologie de pool de serveurs de conversation permanente étirée où les centres de données sont localisés géographiquement avec une faible bande passante/latence élevée.</span><span class="sxs-lookup"><span data-stu-id="dcd8f-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="dcd8f-130">**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.**</span><span class="sxs-lookup"><span data-stu-id="dcd8f-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="dcd8f-131">![Examen de configuration du pool de serveurs de conversation permanente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuration du pool de serveurs de conversation permanente LBW")</span><span class="sxs-lookup"><span data-stu-id="dcd8f-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

