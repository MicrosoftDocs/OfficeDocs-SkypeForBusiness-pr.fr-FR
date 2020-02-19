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
ms.openlocfilehash: d18ef5092f0506951dd9b431c6a44945b87b7f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="fce68-102">Emplacement de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce68-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fce68-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="fce68-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="fce68-104">Le routage géodépendant s’appuie sur les mêmes régions réseau, sites et sous-réseaux que ceux définis dans Lync Server utilisé par E9-1-1, le contrôle d’admission des appels et la déviation du trafic multimédia pour appliquer des restrictions de routage des appels afin d’empêcher le contournement des appels RTC.</span><span class="sxs-lookup"><span data-stu-id="fce68-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="fce68-105">L’emplacement d’un utilisateur est déterminé par le sous-réseau IP des points de terminaison Lync de l’utilisateur qui sont connectés.</span><span class="sxs-lookup"><span data-stu-id="fce68-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="fce68-106">Chaque sous-réseau IP est associé à un site réseau, qui est regroupé en régions réseau définies par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="fce68-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="fce68-107">Le routage géodépendant est appliqué en fonction du site réseau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fce68-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="fce68-108">Les règles de routage basées sur l’emplacement sont appliquées pour chaque site réseau, ce qui signifie qu’un ensemble de règles donné est appliqué à tous les points de terminaison activés pour le routage géodépendant qui sont situés au sein du même site réseau.</span><span class="sxs-lookup"><span data-stu-id="fce68-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="fce68-109">Les administrateurs peuvent appliquer le routage géodépendant aux sites réseau qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="fce68-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="fce68-110">Les stratégies de routage des communications vocales peuvent être définies par site réseau pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="fce68-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="fce68-111">Ces stratégies de routage des communications vocales prévalent sur le routage défini par la stratégie de voix de l’utilisateur lorsque celui-ci se trouve dans un site réseau pour lequel le routage géodépendant est activé, et empêche le routage des appels via d’autres passerelles RTC activées pour Routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="fce68-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="fce68-112">Lorsqu’un utilisateur Lync passe un appel RTC, la stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à passer l’appel.</span><span class="sxs-lookup"><span data-stu-id="fce68-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="fce68-113">Si la stratégie de voix de l’utilisateur permet à l’utilisateur de passer l’appel, le routage géodépendant détermine la passerelle PSTN à partir de laquelle l’appel doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="fce68-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="fce68-114">Le routage géodépendant effectue cette détermination en fonction de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fce68-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="fce68-115">Un emplacement d’utilisateur peut être classé comme suit :</span><span class="sxs-lookup"><span data-stu-id="fce68-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="fce68-116">L’utilisateur se trouve dans un site réseau connu activé pour le routage géodépendant et son numéro DID (numérotation directe vers l’intérieur) se termine sur une passerelle RTC placée dans le même site réseau (c.-à-d. Office).</span><span class="sxs-lookup"><span data-stu-id="fce68-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="fce68-117">Le routage des appels sortants s’effectue par le biais de la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fce68-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="fce68-118">Les appels RTC entrants vers l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="fce68-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="fce68-119">L’utilisateur se trouve dans un site réseau connu qui est différent du site réseau où se trouve la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="fce68-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="fce68-120">(par exemple, l’utilisateur est parcouru à un autre bureau d’entreprise).</span><span class="sxs-lookup"><span data-stu-id="fce68-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="fce68-121">Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel se trouve l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fce68-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="fce68-122">Les appels RTC entrants vers l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans des sites différents de celui de la passerelle PSTN afin d’empêcher le contournement payant PSTN.</span><span class="sxs-lookup"><span data-stu-id="fce68-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="fce68-123">Lorsqu’un utilisateur se trouve dans un site réseau inconnu du déploiement de Lync Server, le routage des appels sortants est basé sur la stratégie de voix attribuée à l’utilisateur sur les passerelles PSTN qui ne sont pas liées à des restrictions de routage basées sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fce68-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="fce68-124">Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement payant PSTN.</span><span class="sxs-lookup"><span data-stu-id="fce68-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fce68-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fce68-125">See Also</span></span>


[<span data-ttu-id="fce68-126">Conseils pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce68-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

