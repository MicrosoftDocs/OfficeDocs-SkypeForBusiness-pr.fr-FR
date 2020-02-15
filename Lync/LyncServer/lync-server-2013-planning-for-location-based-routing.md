---
title: 'Lync Server 2013 : planification du routage géodépendant'
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
ms.openlocfilehash: 307b4d696fdf4348649eb9363d252c7f1d0f8d12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="349df-102">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="349df-103">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="349df-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="349df-104">Les informations contenues dans cette rubrique concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="349df-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="349df-105">Le routage géodépendant permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="349df-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="349df-106">Le routage géodépendant fait partie de l’infrastructure voix entreprise de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="349df-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="349df-107">Le routage géodépendant est une fonctionnalité de gestion des appels qui contrôle la manière dont les appels sont routés par Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="349df-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="349df-108">Elle applique les règles d’autorisation d’appels indiquant si les appels peuvent être acheminés vers des points de terminaison PBX ou PSTN en fonction de l’emplacement géographique de l’appelant Lync.</span><span class="sxs-lookup"><span data-stu-id="349df-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="349df-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="349df-109">In This Section</span></span>

  - [<span data-ttu-id="349df-110">Vue d’ensemble du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="349df-111">Conseils pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="349df-112">Scénarios de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="349df-113">Considérations techniques relatives au routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="349df-114">Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="349df-115">Fonctionnalités non prises en charge par le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="349df-116">Processus de déploiement pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="349df-117">Routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="349df-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="349df-118">See Also</span></span>


[<span data-ttu-id="349df-119">Planification de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="349df-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

