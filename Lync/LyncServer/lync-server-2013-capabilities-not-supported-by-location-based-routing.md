---
title: 'Lync Server 2013 : Fonctionnalités non prises en charge par le routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca2d775fc17d0919ceb31a38b242e54d37b6a55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="ee86e-102">Fonctionnalités non prises en charge par le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86e-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee86e-103">_**Dernière modification de la rubrique:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="ee86e-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="ee86e-104">Le routage basé sur l’emplacement ne s’applique pas aux types d’interactions suivants.</span><span class="sxs-lookup"><span data-stu-id="ee86e-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="ee86e-105">Le routage basé sur l’emplacement n’est pas appliqué lorsque les points de terminaison Lync interagissent avec les points de terminaison RTC à l’aide de ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="ee86e-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="ee86e-106">Appels RTC entrants pour les conférences</span><span class="sxs-lookup"><span data-stu-id="ee86e-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="ee86e-107">Appels RTC entrants et sortants via le groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="ee86e-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="ee86e-108">Parcage d’appel ou récupération des appels via le parcage d’appels</span><span class="sxs-lookup"><span data-stu-id="ee86e-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="ee86e-109">Appels RTC entrants pour le service d’annonce</span><span class="sxs-lookup"><span data-stu-id="ee86e-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="ee86e-110">Appels RTC entrants récupérés via la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="ee86e-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="ee86e-111">Pour appliquer les règles de routage basées sur les emplacements aux types d’interactions dans la liste suivante, vous devez activer le routage par emplacement pour les conférences:</span><span class="sxs-lookup"><span data-stu-id="ee86e-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="ee86e-112">Appels RTC sortants à partir des conférences</span><span class="sxs-lookup"><span data-stu-id="ee86e-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="ee86e-113">Escalades à partir de conversations audio d’P2P vers des conférences impliquant des points de terminaison RTC</span><span class="sxs-lookup"><span data-stu-id="ee86e-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="ee86e-114">Transferts consultatifs impliquant les points de terminaison RTC</span><span class="sxs-lookup"><span data-stu-id="ee86e-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="ee86e-115">Pour activer le routage par emplacement pour les conférences, voir [routage basé sur l’emplacement pour les conférences dans Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="ee86e-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ee86e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee86e-116">See Also</span></span>


[<span data-ttu-id="ee86e-117">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86e-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

