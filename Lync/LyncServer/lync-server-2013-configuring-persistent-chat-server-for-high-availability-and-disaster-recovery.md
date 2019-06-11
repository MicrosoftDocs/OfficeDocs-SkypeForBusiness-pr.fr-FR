---
title: Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c42edb14102b9bbf91b06804c365980a6e19345
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="4f482-102">Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f482-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f482-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4f482-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4f482-104">Le serveur Lync Server 2013, les services de chat permanent utilisent une configuration de *pool ambitieuse* pour la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4f482-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="4f482-105">Un pool étiré est un pool qui comporte des ordinateurs qui sont répartis entre deux centres de données physiques, mais qui se trouvent au sein d’un seul site de serveur Lync logique.</span><span class="sxs-lookup"><span data-stu-id="4f482-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f482-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4f482-106">In This Section</span></span>

  - [<span data-ttu-id="4f482-107">Ressources requises pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f482-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="4f482-108">Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f482-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="4f482-109">Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f482-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="4f482-110">Mise en miroir SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f482-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="4f482-111">Configuration de la copie des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="4f482-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="4f482-112">Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire de copie des journaux de transaction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f482-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

