---
title: 'Lync Server 2013 : vue d’ensemble du routage des Location-Based'
description: 'Lync Server 2013 : vue d’ensemble du routage des Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562810"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b3a58-103">Vue d’ensemble du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3a58-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3a58-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b3a58-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b3a58-105">Le routage des Location-Based introduit un nouveau jeu de règles qui modifie le routage des appels RTC nationaux et internationaux afin de prévenir toute déviation du péage.</span><span class="sxs-lookup"><span data-stu-id="b3a58-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="b3a58-106">Le routage de Location-Based offre la possibilité d’étendre ces règles à des régions spécifiques, des passerelles spécifiques ou à un ensemble spécifique d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b3a58-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="b3a58-107">Les scénarios suivants illustrent les principaux types de restrictions Location-Based le routage peut appliquer :</span><span class="sxs-lookup"><span data-stu-id="b3a58-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="b3a58-108">Appels sortants : le routage de Location-Based peut appliquer des appels sortants à des sorties à partir d’une passerelle PSTN se trouvant dans la même région que l’appelant pour empêcher le contournement Toll, ce qui empêche les appels à sortir d’une passerelle PSTN située dans une autre région que l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b3a58-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="b3a58-109">Appels entrants : le routage des Location-Based peut empêcher les appels RTC entrants de sonner les points de terminaison Lync si la passerelle PSTN achemine l’appel entrant ne se trouve pas dans la même région que l’utilisateur Lync appelé.</span><span class="sxs-lookup"><span data-stu-id="b3a58-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="b3a58-110">Régions inconnues : le routage des Location-Based limite les appels PSTN entrants et sortants vers et à partir d’utilisateurs situés dans des emplacements indéterminés (c’est-à-dire des utilisateurs distants se connectant à partir d’Internet ou situés dans des régions inconnues).</span><span class="sxs-lookup"><span data-stu-id="b3a58-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="b3a58-111">Régions internationales : le routage des Location-Based applique le routage des appels sortants via des passerelles RTC internationales s’il est impossible de trouver une passerelle locale vers l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3a58-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b3a58-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3a58-112">See Also</span></span>


[<span data-ttu-id="b3a58-113">Planification du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3a58-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

