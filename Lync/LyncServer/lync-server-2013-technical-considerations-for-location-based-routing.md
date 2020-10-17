---
title: 'Lync Server 2013 : considérations techniques relatives au routage des Location-Based'
description: 'Lync Server 2013 : considérations techniques relatives au routage des Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568050"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="73b81-103">Considérations techniques relatives au routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b81-103">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b81-104">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="73b81-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="73b81-105">Lors de la planification de la Location-Based routage, vous devez prendre en compte l’impact sur les scénarios suivants.</span><span class="sxs-lookup"><span data-stu-id="73b81-105">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="73b81-106">Récupération d'urgence</span><span class="sxs-lookup"><span data-stu-id="73b81-106">Disaster Recovery</span></span>

<span data-ttu-id="73b81-107">Pendant un basculement depuis le pool principal vers un pool de sauvegarde, ainsi que lors de la restauration des opérations normales vers le pool principal, Location-Based routage reste appliqué à tout moment lors d’une procédure de récupération d’urgence et de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="73b81-107">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="73b81-108">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="73b81-108">Survivable Branch Appliance</span></span>

<span data-ttu-id="73b81-109">La configuration du routage des Location-Based a une incidence sur la planification de l’endroit où vous déployez les passerelles associées à vos Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="73b81-109">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="73b81-110">La passerelle associée à votre SBA doit se trouver dans le même site réseau que votre Survivable Branch Appliance ; dans le cas contraire, les utilisateurs hébergés sur votre Survivable Branch Appliance ne seront pas autorisés à effectuer des appels sortants si Location-Based routage est configuré.</span><span class="sxs-lookup"><span data-stu-id="73b81-110">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="73b81-111">Lorsque la connexion de réseau étendu entre votre Survivable Branch appliance et le site central est inactive, Location-Based les restrictions de routage restent appliquées.</span><span class="sxs-lookup"><span data-stu-id="73b81-111">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73b81-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73b81-112">See Also</span></span>


[<span data-ttu-id="73b81-113">Planification du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b81-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

