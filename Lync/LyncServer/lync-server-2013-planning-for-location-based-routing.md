---
title: 'Lync Server 2013 : planification du routage des Location-Based'
description: 'Lync Server 2013 : planification du routage des Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 894a596e998fe07b97ad7911441eced670ba85b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553080"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8f8d1-103">Planification du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-103">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f8d1-104">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="8f8d1-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="8f8d1-105">Les informations contenues dans cette rubrique concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-105">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="8f8d1-106">Location-Based le routage permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-106">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="8f8d1-107">Le routage des Location-Based fait partie de l’infrastructure voix entreprise de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-107">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="8f8d1-108">Le routage des Location-Based est une fonctionnalité de gestion des appels qui contrôle la manière dont les appels sont routés par Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-108">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="8f8d1-109">Elle applique les règles d’autorisation d’appels indiquant si les appels peuvent être acheminés vers des points de terminaison PBX ou PSTN en fonction de l’emplacement géographique de l’appelant Lync.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-109">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f8d1-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8f8d1-110">In This Section</span></span>

  - [<span data-ttu-id="8f8d1-111">Vue d’ensemble du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-111">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-112">Conseils pour le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-112">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-113">Scénarios de routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-113">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-114">Considérations techniques relatives au routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-114">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-115">Prise en charge des clients et des serveurs pour le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-115">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-116">Fonctionnalités non prises en charge par le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-116">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-117">Processus de déploiement pour le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-117">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="8f8d1-118">Routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-118">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f8d1-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f8d1-119">See Also</span></span>


[<span data-ttu-id="8f8d1-120">Planification de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f8d1-120">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

