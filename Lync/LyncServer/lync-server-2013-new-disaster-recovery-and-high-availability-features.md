---
title: 'Lync Server 2013 : Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="da658-102">Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da658-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da658-103">_**Dernière modification de la rubrique:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="da658-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="da658-104">Comme dans Lync Server 2010, le schéma principal de haute disponibilité pour Lync Server 2013 repose sur la redondance du serveur via le regroupement.</span><span class="sxs-lookup"><span data-stu-id="da658-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="da658-105">Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="da658-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="da658-106">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="da658-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="da658-107">Lync Server 2013 ajoute de nouvelles mesures de reprise après sinistre en vous permettant de jumeler les pools front-end situés dans deux centres de données.</span><span class="sxs-lookup"><span data-stu-id="da658-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="da658-108">Si l’une des listes de réserve s’affiche, un administrateur peut basculer sur les utilisateurs de ce pool vers l’autre pool de la paire pour garantir la continuation du service.</span><span class="sxs-lookup"><span data-stu-id="da658-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="da658-109">Cette fonctionnalité n’exige pas de solutions réseau ou matérielles onéreuses, telles que les réseaux de stockage ou les disques partagés.</span><span class="sxs-lookup"><span data-stu-id="da658-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="da658-110">Lync Server 2013 ajoute également la haute disponibilité du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="da658-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="da658-111">Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs dorsaux pour un pool frontal, et configurez la mise en miroir SQL synchrone pour toutes les bases de données Lync exécutées sur les serveurs dorsaux.</span><span class="sxs-lookup"><span data-stu-id="da658-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="da658-112">Vous pouvez décider de déployer un témoin pour le miroir.</span><span class="sxs-lookup"><span data-stu-id="da658-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="da658-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da658-113">See Also</span></span>


[<span data-ttu-id="da658-114">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da658-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

