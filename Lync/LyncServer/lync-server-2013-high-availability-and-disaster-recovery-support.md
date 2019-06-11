---
title: 'Lync Server 2013 : Prise en charge de la haute disponibilité et de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="b1ae4-102">Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1ae4-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1ae4-103">_**Dernière modification de la rubrique:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="b1ae4-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="b1ae4-104">Lync Server 2013 offre une haute disponibilité grâce à la redondance du serveur via le regroupement.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="b1ae4-105">Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="b1ae4-106">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="b1ae4-107">Pour plus d’informations sur les rôles de serveur, voir [rôles de serveur dans Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b1ae4-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="b1ae4-108">Lync Server 2013 fournit également des mesures de reprise après sinistre en activant le jumelage de pools.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="b1ae4-109">Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="b1ae4-110">Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="b1ae4-111">Lync Server 2013 prend également en charge la haute disponibilité du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="b1ae4-112">Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs back-end pour une liste frontale et configurez la mise en miroir SQL Server synchrone pour toutes les bases de données Lync exécutées sur les serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="b1ae4-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="b1ae4-113">Pour plus d’informations sur le jumelage de pools et la mise en miroir du serveur principal, voir [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b1ae4-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b1ae4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1ae4-114">See Also</span></span>


[<span data-ttu-id="b1ae4-115">Rôles serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1ae4-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="b1ae4-116">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1ae4-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

