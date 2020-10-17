---
title: 'Lync Server 2013 : sonnerie simultanée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358a0dd6dab96b67b26c211c9f28dbc6c0842804
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519791"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="62d83-102">Sonnerie simultanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62d83-102">Simultaneous ringing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62d83-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="62d83-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="62d83-104">Si la sonnerie simultanée est activée pour la partie appelée, le routage Location-Based analyse l’emplacement de la partie appelante et les points de terminaison des parties appelées afin de déterminer si l’appel doit être acheminé.</span><span class="sxs-lookup"><span data-stu-id="62d83-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="62d83-105">Le tableau suivant illustre un utilisateur configuré avec la sonnerie simultanée et la cible de la sonnerie simultanée est un utilisateur du même site réseau, d’un site réseau différent ou d’un site réseau inconnu.</span><span class="sxs-lookup"><span data-stu-id="62d83-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62d83-106">Appel RTC entrant pour</span><span class="sxs-lookup"><span data-stu-id="62d83-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="62d83-107">Situé dans le même site réseau que l’appelé.</span><span class="sxs-lookup"><span data-stu-id="62d83-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="62d83-108">Situé dans un site réseau différent de celui de l’appelé ;</span><span class="sxs-lookup"><span data-stu-id="62d83-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="62d83-109">Situé dans un site réseau inconnu ou non activé pour le routage des Location-Based</span><span class="sxs-lookup"><span data-stu-id="62d83-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62d83-110">Utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="62d83-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="62d83-111">Sonnerie simultanée autorisée</span><span class="sxs-lookup"><span data-stu-id="62d83-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="62d83-112">Sonnerie simultanée non autorisée</span><span class="sxs-lookup"><span data-stu-id="62d83-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="62d83-113">Sonnerie simultanée non autorisée</span><span class="sxs-lookup"><span data-stu-id="62d83-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="62d83-114">Le tableau suivant illustre un appel d’un utilisateur Lync (par exemple, l’appelant Lync) dans le même site réseau, dans un autre site réseau ou à partir d’un site réseau inconnu.</span><span class="sxs-lookup"><span data-stu-id="62d83-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="62d83-115">L’appelé a un point de terminaison PSTN (par exemple, téléphone portable) configuré en tant que cible circulaire simultanée.</span><span class="sxs-lookup"><span data-stu-id="62d83-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="62d83-116">Dans ce scénario, Location-Based routage détermine si l’appel doit être acheminé vers la cible de sonnerie simultanée (téléphone cellulaire) de l’appelé ou non.</span><span class="sxs-lookup"><span data-stu-id="62d83-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62d83-117">Cible annulaire simultanée</span><span class="sxs-lookup"><span data-stu-id="62d83-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="62d83-118">Situé dans le même site réseau que l’appelé.</span><span class="sxs-lookup"><span data-stu-id="62d83-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="62d83-119">Situé dans un site réseau différent de celui de l’appelé ;</span><span class="sxs-lookup"><span data-stu-id="62d83-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="62d83-120">Situé dans un site réseau inconnu ou non activé pour le routage des Location-Based</span><span class="sxs-lookup"><span data-stu-id="62d83-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62d83-121">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="62d83-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="62d83-122">Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</span><span class="sxs-lookup"><span data-stu-id="62d83-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="62d83-123">Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</span><span class="sxs-lookup"><span data-stu-id="62d83-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="62d83-124">Sonnerie simultanée autorisée via la stratégie de voix de l’appelant aux jonctions non activées pour le routage des Location-Based</span><span class="sxs-lookup"><span data-stu-id="62d83-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="62d83-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62d83-125">See Also</span></span>


[<span data-ttu-id="62d83-126">Scénarios de routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62d83-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

