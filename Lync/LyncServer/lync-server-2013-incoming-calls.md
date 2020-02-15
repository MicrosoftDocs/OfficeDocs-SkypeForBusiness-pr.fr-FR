---
title: 'Lync Server 2013 : appels entrants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c153af6e14c291189f714f7054f72301d6859a88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="5bcab-102">Appels entrants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bcab-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bcab-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5bcab-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5bcab-104">Le routage des appels entrants vers des utilisateurs activés pour le routage géodépendant dépend de l’emplacement du point de terminaison de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5bcab-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="5bcab-105">Le routage des appels entrants est affecté de la manière suivante.</span><span class="sxs-lookup"><span data-stu-id="5bcab-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="5bcab-106">Si un utilisateur a reçu un appel entrant vers un point de terminaison situé dans un site réseau de routage basé sur l’emplacement et que le point de terminaison se trouve dans le même site réseau que la passerelle RTC, l’appel sera acheminé.</span><span class="sxs-lookup"><span data-stu-id="5bcab-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="5bcab-107">Si un utilisateur a reçu un appel entrant vers un point de terminaison situé dans un site réseau de routage basé sur l’emplacement et que le point de terminaison se trouve dans un autre site réseau que la passerelle RTC, l’appel n’est pas acheminé.</span><span class="sxs-lookup"><span data-stu-id="5bcab-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="5bcab-108">Lorsqu’un utilisateur n’a pas de point de terminaison situé dans le même site réseau que la passerelle RTC, l’appel entrant est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel en absence est envoyée à la personne appelée.</span><span class="sxs-lookup"><span data-stu-id="5bcab-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="5bcab-109">Les paramètres de transfert d’appel d’un utilisateur activé pour le routage géodépendant continueront à être appliqués, cependant, les appels transférés seront soumis aux restrictions de routage géodépendant de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5bcab-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="5bcab-110">Le tableau suivant montre comment le routage géodépendant affecte le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5bcab-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="5bcab-111">Le site réseau de la passerelle PSTN est activé pour le routage géodépendant et le routage géodépendant uniquement autorise le routage des appels PSTN vers les points de terminaison au sein du même site réseau.</span><span class="sxs-lookup"><span data-stu-id="5bcab-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="5bcab-112">Appelé recevant un appel entrant du RTC</span><span class="sxs-lookup"><span data-stu-id="5bcab-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5bcab-113">Point de terminaison de l’appelé situé dans le même site réseau que la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="5bcab-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="5bcab-114">Point de terminaison de l’appelé non situé dans le même site réseau que la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="5bcab-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="5bcab-115">Point de terminaison de l’appelé situé dans un site réseau inconnu ou non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="5bcab-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bcab-116">Routage des appels RTC entrants</span><span class="sxs-lookup"><span data-stu-id="5bcab-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="5bcab-117">L’appel entrant est acheminé vers les points de terminaison de l’appelé</span><span class="sxs-lookup"><span data-stu-id="5bcab-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="5bcab-118">L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelé</span><span class="sxs-lookup"><span data-stu-id="5bcab-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="5bcab-119">L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelé</span><span class="sxs-lookup"><span data-stu-id="5bcab-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="5bcab-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5bcab-120">See Also</span></span>


[<span data-ttu-id="5bcab-121">Scénarios de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bcab-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

