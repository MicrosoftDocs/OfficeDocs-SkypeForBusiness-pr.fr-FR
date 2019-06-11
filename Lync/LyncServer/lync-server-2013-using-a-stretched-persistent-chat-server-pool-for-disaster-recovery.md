---
title: Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="fddfe-102">Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fddfe-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fddfe-103">_**Dernière modification de la rubrique:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fddfe-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fddfe-104">La solution de reprise après sinistre pour le serveur de chat permanent repose sur un pool de serveurs de chat permanent étiré.</span><span class="sxs-lookup"><span data-stu-id="fddfe-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="fddfe-105">Similaire à la résilience de site métropolitain dans Lync Server 2010; Toutefois, il n’existe aucune exigence pour un réseau local virtuel étiré.</span><span class="sxs-lookup"><span data-stu-id="fddfe-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="fddfe-106">En étireant le pool de serveurs de chat permanent, vous configurez essentiellement un pool dans la topologie logiquement, mais vous positionnez physiquement les serveurs dans le pool dans deux centres de données différents.</span><span class="sxs-lookup"><span data-stu-id="fddfe-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="fddfe-107">Configurez la mise en miroir SQL Server pour la base de données de la même manière, puis déployez la base de données et le miroir dans le même centre de données.</span><span class="sxs-lookup"><span data-stu-id="fddfe-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="fddfe-108">Vous devez configurer une base de données de sauvegarde dans le second centre de données (avec un miroir éventuel pour assurer la haute disponibilité pendant la récupération d’urgence).</span><span class="sxs-lookup"><span data-stu-id="fddfe-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="fddfe-109">Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fddfe-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="fddfe-110">Pour plus d’informations sur la configuration de la mise en miroir SQL Server pour une haute disponibilité, voir [mise en miroir SQL Server dans Lync server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="fddfe-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="fddfe-111">Pour plus d’informations sur le basculement de la base de données à des fins de reprise après sinistre, voir Configuration de l' [envoi de journaux dans Lync server 2013 pour la base de données principale du serveur de chat permanent](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) et configuration de l' [expédition du journal SQL Server entre le miroir principal et le journal. Expédition d’une base de données secondaire dans Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).</span><span class="sxs-lookup"><span data-stu-id="fddfe-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

