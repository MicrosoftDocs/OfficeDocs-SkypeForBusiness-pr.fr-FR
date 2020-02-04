---
title: 'Lync Server 2013 : Emplacement de la passerelle RTC'
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
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="f2928-102">Emplacement de la passerelle RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2928-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2928-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f2928-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f2928-104">Les appels routés via des passerelles RTC et des PBX peuvent nécessiter des limitations de routage basées sur l’emplacement selon l’emplacement de ces systèmes.</span><span class="sxs-lookup"><span data-stu-id="f2928-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="f2928-105">Le routage basé sur l’emplacement peut être activé en fonction du niveau de granularité par Trunk.</span><span class="sxs-lookup"><span data-stu-id="f2928-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="f2928-106">Le routage basé sur l’emplacement présente l’ensemble de règles suivant lorsqu’il est activé sur un Trunk :</span><span class="sxs-lookup"><span data-stu-id="f2928-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="f2928-107">Lorsque le routage basé sur l’emplacement est activé sur une base par Trunk, les règles définies sur ce Trunk s’appliquent uniquement aux appels routés via ce Trunk.</span><span class="sxs-lookup"><span data-stu-id="f2928-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="f2928-108">Pour éviter les péages RTC dans lesquels les appels proviennent d’un site réseau différent du site du réseau sur lequel se trouve la passerelle RTC, le routage de géolocalisation présente l’Association d’un site réseau à un Trunk donné.</span><span class="sxs-lookup"><span data-stu-id="f2928-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="f2928-109">Cela permet de définir le site réseau qui permet l’acheminement des appels vers une jonction donnée.</span><span class="sxs-lookup"><span data-stu-id="f2928-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="f2928-110">Les types de Trunk peuvent être activés pour le routage selon l’emplacement de deux manières :</span><span class="sxs-lookup"><span data-stu-id="f2928-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="f2928-p103">La jonction est définie pour une passerelle RTC qui fait sortir les appels vers le réseau téléphonique commuté (RTC). Les appels entrants pris en charge par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.</span><span class="sxs-lookup"><span data-stu-id="f2928-p103">The trunk is defined for a PSTN gateway that egresses calls to the PSTN. Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="f2928-113">Le Trunk est défini pour un homologue de serveur de médiation qui ne sort pas les appels vers les utilisateurs RTC et services avec des téléphones hérités dans des emplacements statiques (tels que les téléphones PBX).</span><span class="sxs-lookup"><span data-stu-id="f2928-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="f2928-114">Pour cette configuration particulière, tous les appels entrants acheminés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction.</span><span class="sxs-lookup"><span data-stu-id="f2928-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="f2928-115">Les appels des utilisateurs PBX auront la même application de routage basée sur l’emplacement que les utilisateurs de Lync situés dans le même site réseau que le Trunk.</span><span class="sxs-lookup"><span data-stu-id="f2928-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="f2928-116">Si deux systèmes PBX situés dans des sites de réseau séparés sont connectés via Lync Server, le routage de l’emplacement autorise le routage à partir d’un point de terminaison PBX dans un site réseau à un autre point de terminaison PBX dans l’autre site réseau.</span><span class="sxs-lookup"><span data-stu-id="f2928-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="f2928-117">Ce scénario ne sera pas bloqué par le routage sur site.</span><span class="sxs-lookup"><span data-stu-id="f2928-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="f2928-118">Outre ce scénario et de la même manière qu’un utilisateur Lync dans le même emplacement, les points de terminaison connectés à un homologue de serveur de médiation doté de cette configuration sont en mesure de passer ou de recevoir des appels vers et à partir d’autres homologues du serveur de médiation qui ne routent pas les appels vers le RTC (i). e. point de terminaison connecté à un autre système PBX), quel que soit le site du réseau auquel l’homologue du serveur de médiation est associé.</span><span class="sxs-lookup"><span data-stu-id="f2928-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="f2928-119">Tous les appels entrants, les appels sortants, les transferts d’appel et les transferts d’appel impliquant des points de terminaison RTC sont soumis à un routage basé sur l’emplacement pour utiliser uniquement les passerelles RTC définies comme étant locales pour ce serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f2928-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f2928-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2928-120">See Also</span></span>


[<span data-ttu-id="f2928-121">Instructions de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2928-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

