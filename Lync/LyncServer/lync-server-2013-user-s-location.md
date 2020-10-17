---
title: 'Lync Server 2013 : emplacement de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 854e887605cc1d3d2b6d394228ebd3e8059644ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518831"
---
# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="dccfa-102">Emplacement de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dccfa-102">User's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dccfa-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="dccfa-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="dccfa-104">Location-Based le routage exploite les mêmes régions réseau, sites et sous-réseaux qu’il est défini dans Lync Server et utilisé par E9-1-1, le contrôle d’admission des appels et la déviation du trafic multimédia pour appliquer des restrictions de routage des appels afin d’empêcher le contournement Toll.</span><span class="sxs-lookup"><span data-stu-id="dccfa-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="dccfa-105">L’emplacement d’un utilisateur est déterminé par le sous-réseau IP des points de terminaison Lync de l’utilisateur qui sont connectés.</span><span class="sxs-lookup"><span data-stu-id="dccfa-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="dccfa-106">Chaque sous-réseau IP est associé à un site réseau, qui est regroupé en régions réseau définies par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="dccfa-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="dccfa-107">Le routage des Location-Based est appliqué en fonction du site réseau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dccfa-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="dccfa-108">Les règles de routage des Location-Based sont appliquées en fonction du site réseau, ce qui signifie qu’un ensemble de règles donné est appliqué à tous les points de terminaison activés pour le routage Location-Based qui sont situés dans le même site réseau.</span><span class="sxs-lookup"><span data-stu-id="dccfa-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="dccfa-109">Les administrateurs peuvent appliquer des Location-Based le routage aux sites réseau qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="dccfa-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="dccfa-110">Les stratégies de routage des communications vocales peuvent être définies par site réseau pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="dccfa-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="dccfa-111">Ces stratégies de routage des communications vocales prévalent sur le routage défini par la stratégie de voix de l’utilisateur lorsque celui-ci se trouve dans un site réseau activé pour le routage des Location-Based et qu’il empêche le routage des appels via d’autres passerelles RTC qui sont activées pour le routage de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="dccfa-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="dccfa-112">Lorsqu’un utilisateur Lync passe un appel RTC, la stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à passer l’appel.</span><span class="sxs-lookup"><span data-stu-id="dccfa-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="dccfa-113">Si la stratégie de voix de l’utilisateur autorise l’utilisateur à passer l’appel, Location-Based routage détermine la passerelle PSTN à partir de laquelle l’appel doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="dccfa-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="dccfa-114">Location-Based routage effectue cette détermination en fonction de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dccfa-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="dccfa-115">Un emplacement d’utilisateur peut être classé comme suit :</span><span class="sxs-lookup"><span data-stu-id="dccfa-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="dccfa-116">L’utilisateur se trouve dans un site réseau connu activé pour le routage des Location-Based et son numéro a (numérotation directe vers l’intérieur) se termine sur une passerelle RTC placée dans le même site réseau (c.-à-d. Office).</span><span class="sxs-lookup"><span data-stu-id="dccfa-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="dccfa-117">Le routage des appels sortants s’effectue par le biais de la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dccfa-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="dccfa-118">Les appels RTC entrants vers l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="dccfa-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="dccfa-119">L’utilisateur se trouve dans un site réseau connu qui est différent du site réseau où se trouve la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="dccfa-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="dccfa-120">(par exemple, l’utilisateur est parcouru à un autre bureau d’entreprise).</span><span class="sxs-lookup"><span data-stu-id="dccfa-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="dccfa-121">Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dccfa-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="dccfa-122">Les appels RTC entrants vers l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans des sites différents de celui de la passerelle PSTN afin d’empêcher le contournement payant PSTN.</span><span class="sxs-lookup"><span data-stu-id="dccfa-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="dccfa-123">Lorsqu’un utilisateur se trouve dans un site réseau inconnu du déploiement Lync Server, le routage des appels sortants est basé sur la stratégie de voix attribuée à l’utilisateur sur les passerelles PSTN qui ne sont pas liées à des restrictions de routage Location-Based.</span><span class="sxs-lookup"><span data-stu-id="dccfa-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="dccfa-124">Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement payant PSTN.</span><span class="sxs-lookup"><span data-stu-id="dccfa-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dccfa-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dccfa-125">See Also</span></span>


[<span data-ttu-id="dccfa-126">Conseils pour le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dccfa-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

