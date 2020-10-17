---
title: Modifications apportées à la topologie Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3979aa0725b632a1b5910c5f7e27b9a6a28245d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530391"
---
# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="6d696-102">Modifications de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d696-102">Topology changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d696-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6d696-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6d696-104">Les exigences et les considérations relatives à la topologie de Lync Server 2013 diffèrent de celles des versions antérieures, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="6d696-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="6d696-105">Nouvelle architecture de pools frontaux</span><span class="sxs-lookup"><span data-stu-id="6d696-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="6d696-106">Dans Lync Server 2013, l’architecture des pools frontaux Enterprise Editions a été remplacée par une architecture de systèmes distribués.</span><span class="sxs-lookup"><span data-stu-id="6d696-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="6d696-p101">Avec cette nouvelle architecture, la base de données principale n’est plus le magasin de données en temps réel dans un pool. Les informations relatives à un utilisateur particulier sont conservées sur trois serveurs frontaux dans le pool. Pour chaque utilisateur, un serveur frontal joue le rôle de maître pour les informations de cet utilisateur et deux autres serveurs frontaux servent de réplicas. En cas de défaillance d’un serveur frontal, un autre serveur frontal qui servait de réplica est promu automatiquement en maître.</span><span class="sxs-lookup"><span data-stu-id="6d696-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="6d696-111">Ceci se produisant en arrière-plan, il n’est pas nécessaire que les administrateurs sachent quels serveurs frontaux sont les maîtres pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d696-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="6d696-112">Cette distribution du stockage des données améliore les performances et l’extensibilité au sein du pool, et élimine le point de défaillance unique d’un serveur principal unique.</span><span class="sxs-lookup"><span data-stu-id="6d696-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="6d696-113">Le serveur principal sert de stockage de sauvegarde pour les données utilisateur et de conférence, et est également le stockage principal pour d’autres bases de données telles que la base de données Response Group.</span><span class="sxs-lookup"><span data-stu-id="6d696-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="6d696-114">Ces améliorations sont également synonymes de changements dans la manière dont vous planifiez et maintenez vos pools.</span><span class="sxs-lookup"><span data-stu-id="6d696-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="6d696-115">Nous recommandons que tous les pools frontaux Enterprise Edition incluent au moins trois serveurs frontaux, afin de fournir le nombre complet de réplicas pour lesquels l’architecture de pool frontal est conçue.</span><span class="sxs-lookup"><span data-stu-id="6d696-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="6d696-116">En outre, vous devez suivre certaines procédures lors de l’ajout de serveurs à un pool frontal, de la suppression de serveurs ou de la mise à niveau de serveurs.</span><span class="sxs-lookup"><span data-stu-id="6d696-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="6d696-117">Pour plus d’informations, voir [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="6d696-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="6d696-118">Modifications de topologie de rôles serveur</span><span class="sxs-lookup"><span data-stu-id="6d696-118">Server Role Topology Changes</span></span>

<span data-ttu-id="6d696-119">Certains rôles serveur qui s’exécutaient auparavant sur des serveurs distincts sont maintenant consolidés dans le rôle de serveur frontal, ce qui vous permet de faire des économies sur les coûts matériels.</span><span class="sxs-lookup"><span data-stu-id="6d696-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="6d696-120">Dans Lync Server 2013, le serveur de conférence A/V est toujours colocalisé avec le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="6d696-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="6d696-p104">Les serveurs frontaux de surveillance et d’archivage sont désormais toujours colocalisés avec le serveur frontal. Ces deux fonctionnalités nécessitent toujours une base de données principale distincte, qui peut être colocalisée sur le même serveur que la base de données principale du pool frontal ou peut être hébergée sur des serveurs principaux distincts.</span><span class="sxs-lookup"><span data-stu-id="6d696-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="6d696-123">Le serveur de conversation permanente est maintenant un rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="6d696-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="6d696-124">Dans Microsoft Lync Server 2010, le serveur de conversation de groupe était une application tierce de confiance pour Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6d696-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="6d696-125">Dans Lync Server 2013, la fonctionnalité de serveur de conversation permanente est implémentée à l’aide de trois nouveaux rôles serveur :</span><span class="sxs-lookup"><span data-stu-id="6d696-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="6d696-126">**PersistentChatService :** Principaux services de serveur de conversation permanente implémentés en tant que rôle frontal</span><span class="sxs-lookup"><span data-stu-id="6d696-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="6d696-127">**PersistentChatStore :** Rôle de serveur principal</span><span class="sxs-lookup"><span data-stu-id="6d696-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="6d696-128">**PersistentChatComplianceStore :** Rôle de serveur principal pour la conformité de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6d696-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

