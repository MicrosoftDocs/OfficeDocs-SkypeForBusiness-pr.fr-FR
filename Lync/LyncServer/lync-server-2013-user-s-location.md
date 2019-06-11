---
title: 'Lync Server 2013 : Emplacement de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="d8fdf-102">Emplacement de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8fdf-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8fdf-103">_**Dernière modification de la rubrique:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d8fdf-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d8fdf-104">Le routage basé sur géolocalisation exploite les mêmes régions, sites et sous-réseaux tels qu’ils sont définis dans Lync Server utilisé par E9-1-1, CAC et Media bypass pour appliquer des restrictions de routage des appels pour empêcher le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="d8fdf-105">L’emplacement d’un utilisateur est déterminé par le sous-réseau IP du ou des points de terminaison Lync de l’utilisateur qui sont connectés.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="d8fdf-106">Chaque sous-réseau IP est associé à un site réseau, regroupé au sein de régions réseau définies par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="d8fdf-107">Le routage géodépendant est appliqué sur la base du site réseau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="d8fdf-108">Les règles de routage basées sur le niveau de géolocalisation sont appliquées au niveau de chaque site du réseau, ce qui signifie qu’un ensemble de règles donné sera appliqué à tous les points de terminaison activés pour le routage par emplacement situés au sein du même site réseau.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="d8fdf-109">Les administrateurs peuvent appliquer le routage sur site aux sites réseau qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="d8fdf-110">Il est possible de définir les stratégies de routage vocal sur une base de site réseau par site pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="d8fdf-111">Ces stratégies de routage de la voix prévaudront sur le routage défini par la stratégie vocale de l’utilisateur lorsque celui-ci se trouve dans un site réseau activé pour le routage de l’emplacement et qu’il empêche le routage des appels via d’autres passerelles RTC activées pour Routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="d8fdf-112">Lorsqu’un utilisateur de Lync place un appel RTC, la stratégie vocale de l’utilisateur détermine si l’utilisateur peut être autorisé à effectuer l’appel.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="d8fdf-113">Si la stratégie vocale de l’utilisateur permet à l’utilisateur de passer l’appel, le routage basé sur l’emplacement détermine la passerelle RTC à partir de laquelle l’appel doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="d8fdf-114">Le routage basé sur l’emplacement effectue cette détermination en fonction de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="d8fdf-115">L’emplacement d’un utilisateur peut être classé comme suit :</span><span class="sxs-lookup"><span data-stu-id="d8fdf-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="d8fdf-116">L’utilisateur se trouve dans un site réseau connu activé pour le routage géolocalisation et il se termine par un numéro sur une passerelle RTC placée sur le même site (par exemple, Office).</span><span class="sxs-lookup"><span data-stu-id="d8fdf-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="d8fdf-117">Le routage des appels sortants est effectué via la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="d8fdf-118">Les appels RTC entrants destinés à l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="d8fdf-p105">L’utilisateur est situé dans un site réseau connu différent du site réseau dans lequel la passerelle RTC est située (l’utilisateur a été déplacé vers une autre agence). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans d’autres sites que la passerelle RTC pour empêcher le contournement des frais de réseau téléphonique commuté.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-p105">The user is located in a known network site that is in different from the network site where the PSTN gateway is located. (i.e. the user traveled to another corporate office). The routing of outbound calls will be using the voice routing policy of the network site in which the user is located. Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="d8fdf-123">Lorsqu’un utilisateur se trouve dans un site réseau qui n’est pas connu du déploiement de Lync Server, le routage des appels sortants sera basé sur la stratégie vocale attribuée à l’utilisateur sur les passerelles RTC qui ne sont pas liées aux restrictions de routage basées sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="d8fdf-124">Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement des frais de réseau téléphonique commuté.</span><span class="sxs-lookup"><span data-stu-id="d8fdf-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d8fdf-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8fdf-125">See Also</span></span>


[<span data-ttu-id="d8fdf-126">Instructions de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8fdf-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

