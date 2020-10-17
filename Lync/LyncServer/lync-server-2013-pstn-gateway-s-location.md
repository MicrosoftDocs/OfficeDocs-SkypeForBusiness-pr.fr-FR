---
title: 'Lync Server 2013 : emplacement de la passerelle RTC'
description: 'Lync Server 2013 : emplacement de la passerelle RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f793249908bd1f064f9038ddd90c7f5b01a61d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565600"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="3785f-103">Emplacement de la passerelle PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3785f-103">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3785f-104">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="3785f-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="3785f-105">Les appels acheminés via des passerelles PSTN et des PBX peuvent nécessiter des restrictions de routage Location-Based en fonction de l’emplacement de ces systèmes.</span><span class="sxs-lookup"><span data-stu-id="3785f-105">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="3785f-106">Location-Based le routage peut être activé au niveau de la granularité par tronçon.</span><span class="sxs-lookup"><span data-stu-id="3785f-106">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="3785f-107">Le routage de Location-Based introduit l’ensemble de règles suivant lorsqu’il est activé sur une jonction :</span><span class="sxs-lookup"><span data-stu-id="3785f-107">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="3785f-108">Lorsque Location-Based routage est activé sur une base par tronçon, les règles définies sur cette jonction s’appliquent uniquement aux appels routés via cette jonction.</span><span class="sxs-lookup"><span data-stu-id="3785f-108">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="3785f-109">Pour empêcher le contournement des péages RTC où les appels proviennent d’un site réseau différent du site réseau où se trouve la passerelle PSTN, Location-Based routage introduit l’Association d’un site réseau à une jonction donnée.</span><span class="sxs-lookup"><span data-stu-id="3785f-109">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="3785f-110">Cela définit le site réseau qui permet de router les appels vers une jonction donnée.</span><span class="sxs-lookup"><span data-stu-id="3785f-110">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="3785f-111">Les jonctions peuvent être activées pour le routage de Location-Based de deux manières :</span><span class="sxs-lookup"><span data-stu-id="3785f-111">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="3785f-112">La jonction est définie pour une passerelle RTC qui egresses appelle le RTC.</span><span class="sxs-lookup"><span data-stu-id="3785f-112">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="3785f-113">Les appels entrants routés par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.</span><span class="sxs-lookup"><span data-stu-id="3785f-113">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="3785f-114">La jonction est définie pour un homologue de serveur de médiation qui ne sort pas les appels vers le réseau téléphonique commuté (RTC) et les utilisateurs de services avec des téléphones hérités dans un emplacement statique (par exemple, téléphones PBX).</span><span class="sxs-lookup"><span data-stu-id="3785f-114">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="3785f-115">Pour cette configuration particulière, tous les appels entrants routés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction.</span><span class="sxs-lookup"><span data-stu-id="3785f-115">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="3785f-116">Les appels des utilisateurs PBX auront le même Location-Based de routage que les utilisateurs Lync qui se trouvent sur le même site réseau que la jonction.</span><span class="sxs-lookup"><span data-stu-id="3785f-116">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="3785f-117">Si deux systèmes PBX situés dans des sites réseau distincts sont connectés via Lync Server, Location-Based le routage permettra le routage d’un point de terminaison PBX dans un site réseau vers un autre point de terminaison PBX dans l’autre site réseau.</span><span class="sxs-lookup"><span data-stu-id="3785f-117">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="3785f-118">Ce scénario ne sera pas bloqué par le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="3785f-118">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="3785f-119">En plus de ce scénario et de la même manière qu’un utilisateur Lync au même endroit, les points de terminaison connectés à un serveur de médiation homologue avec cette configuration peuvent passer ou recevoir des appels vers et à partir d’autres homologues de serveur de médiation qui n’acheminent pas les appels vers le RTC (c.-à-d</span><span class="sxs-lookup"><span data-stu-id="3785f-119">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="3785f-120">Tous les appels entrants, sortants, de transfert d’appel et de transfert d’appels impliquant des points de terminaison PSTN seront soumis à un routage basé sur l’emplacement afin d’utiliser uniquement les passerelles PSTN définies comme locales à un tel homologue de serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3785f-120">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3785f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3785f-121">See Also</span></span>


[<span data-ttu-id="3785f-122">Conseils pour le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3785f-122">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

