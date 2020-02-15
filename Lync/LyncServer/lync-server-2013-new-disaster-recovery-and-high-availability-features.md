---
title: 'Lync Server 2013 : nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d69a77e1277b843ed1df13a130e67a9ee081d98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="80df8-102">Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80df8-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80df8-103">_**Dernière modification de la rubrique :** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="80df8-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="80df8-104">Comme dans Lync Server 2010, le schéma haute disponibilité (HA) principal pour Lync Server 2013 repose sur la redondance des serveurs via la mise en pool.</span><span class="sxs-lookup"><span data-stu-id="80df8-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="80df8-105">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="80df8-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="80df8-106">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="80df8-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="80df8-107">Lync Server 2013 ajoute de nouvelles mesures de récupération d’urgence en vous permettant de coupler des pools frontaux situés dans deux centres de données.</span><span class="sxs-lookup"><span data-stu-id="80df8-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="80df8-108">Si l’un des pools appariés n’est plus opérationnel, un administrateur peut effectuer le basculement des utilisateurs de ce pool vers l’autre pool de la paire afin de garantir une continuité du service.</span><span class="sxs-lookup"><span data-stu-id="80df8-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="80df8-109">Cette fonctionnalité ne nécessite aucune solution réseau ou matérielle coûteuse comme les réseaux de stockage ou les disques partagés.</span><span class="sxs-lookup"><span data-stu-id="80df8-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="80df8-110">Lync Server 2013 ajoute également la haute disponibilité du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="80df8-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="80df8-111">Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs principaux pour un pool frontal et configurez la mise en miroir SQL synchrone pour toutes les bases de données Lync exécutées sur les serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="80df8-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="80df8-112">Vous pouvez décider de déployer ou non un serveur témoin pour le miroir.</span><span class="sxs-lookup"><span data-stu-id="80df8-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="80df8-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80df8-113">See Also</span></span>


[<span data-ttu-id="80df8-114">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80df8-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

