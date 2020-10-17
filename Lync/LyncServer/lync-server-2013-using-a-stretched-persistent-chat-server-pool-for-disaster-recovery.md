---
title: Utilisation d’un pool de serveurs de conversation permanente étiré pour la récupération d’urgence
description: Utilisation d’un pool de serveurs de conversation permanente étiré pour la récupération d’urgence.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83a7226f7b9a49a2676b6222505f53247bd5abf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548540"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="076a5-103">Utilisation d’un pool de serveurs de conversation permanente étiré pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="076a5-103">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="076a5-104">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="076a5-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="076a5-105">La solution de récupération d’urgence pour le serveur de conversation permanente est basée sur un pool de serveurs de conversation permanente étiré.</span><span class="sxs-lookup"><span data-stu-id="076a5-105">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="076a5-106">Il s’agit de la résilience de site métropolitaine dans Lync Server 2010 ; Toutefois, il n’est pas nécessaire de disposer d’un réseau local virtuel (VLAN) étiré.</span><span class="sxs-lookup"><span data-stu-id="076a5-106">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="076a5-107">En étirant le pool de serveurs de conversation permanente, vous configurez essentiellement un pool dans la topologie de manière logique, mais vous placez physiquement les serveurs dans le pool dans deux centres de données différents.</span><span class="sxs-lookup"><span data-stu-id="076a5-107">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="076a5-108">Configurez la mise en miroir SQL Server pour la base de données de la même manière et déployez la base de données et le miroir dans le même centre de données.</span><span class="sxs-lookup"><span data-stu-id="076a5-108">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="076a5-109">Vous devez configurer une base de données de sauvegarde dans le centre de données secondaire (avec un miroir facultatif pour fournir une haute disponibilité lors de la récupération d’urgence).</span><span class="sxs-lookup"><span data-stu-id="076a5-109">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="076a5-110">Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="076a5-110">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="076a5-111">Pour plus d’informations sur la configuration de la mise en miroir SQL Server pour la haute disponibilité, voir [mise en miroir SQL Server dans Lync server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="076a5-111">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="076a5-112">Pour plus d’informations sur le basculement de la base de données pour la récupération d’urgence, voir Configuration de la copie [des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) et configuration de la [copie des journaux de transaction SQL Server entre le miroir principal et la base de données secondaire de copie des journaux dans Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md)</span><span class="sxs-lookup"><span data-stu-id="076a5-112">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

