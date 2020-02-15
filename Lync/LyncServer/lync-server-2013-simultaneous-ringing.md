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
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="bed37-102">Sonnerie simultanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed37-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed37-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="bed37-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="bed37-104">Lorsque le composant appelé dispose d’une sonnerie simultanée, le routage géodépendant permet d’analyser l’emplacement de l’appelant et les points de terminaison des parties appelées afin de déterminer si l’appel doit être acheminé.</span><span class="sxs-lookup"><span data-stu-id="bed37-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="bed37-105">Le tableau suivant illustre un utilisateur configuré avec la sonnerie simultanée et la cible de la sonnerie simultanée est un utilisateur du même site réseau, d’un site réseau différent ou d’un site réseau inconnu.</span><span class="sxs-lookup"><span data-stu-id="bed37-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed37-106">Appel RTC entrant pour</span><span class="sxs-lookup"><span data-stu-id="bed37-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="bed37-107">Situé dans le même site réseau que l’appelé.</span><span class="sxs-lookup"><span data-stu-id="bed37-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="bed37-108">Situé dans un site réseau différent de celui de l’appelé ;</span><span class="sxs-lookup"><span data-stu-id="bed37-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="bed37-109">Situé dans un site réseau inconnu ou non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="bed37-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed37-110">Utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="bed37-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="bed37-111">Sonnerie simultanée autorisée</span><span class="sxs-lookup"><span data-stu-id="bed37-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="bed37-112">Sonnerie simultanée non autorisée</span><span class="sxs-lookup"><span data-stu-id="bed37-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="bed37-113">Sonnerie simultanée non autorisée</span><span class="sxs-lookup"><span data-stu-id="bed37-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="bed37-114">Le tableau suivant illustre un appel d’un utilisateur Lync (par exemple, l’appelant Lync) dans le même site réseau, dans un autre site réseau ou à partir d’un site réseau inconnu.</span><span class="sxs-lookup"><span data-stu-id="bed37-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="bed37-115">L’appelé a un point de terminaison PSTN (par exemple, téléphone portable) configuré en tant que cible circulaire simultanée.</span><span class="sxs-lookup"><span data-stu-id="bed37-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="bed37-116">Dans ce scénario, le routage géodépendant indique si l’appel doit être acheminé vers la cible de sonnerie simultanée (téléphone cellulaire) de l’appelé ou non.</span><span class="sxs-lookup"><span data-stu-id="bed37-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed37-117">Cible annulaire simultanée</span><span class="sxs-lookup"><span data-stu-id="bed37-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="bed37-118">Situé dans le même site réseau que l’appelé.</span><span class="sxs-lookup"><span data-stu-id="bed37-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="bed37-119">Situé dans un site réseau différent de celui de l’appelé ;</span><span class="sxs-lookup"><span data-stu-id="bed37-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="bed37-120">Situé dans un site réseau inconnu ou non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="bed37-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed37-121">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="bed37-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="bed37-122">Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</span><span class="sxs-lookup"><span data-stu-id="bed37-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bed37-123">Sonnerie simultanée autorisée via la stratégie de routage des communications vocales du site de l’appelant</span><span class="sxs-lookup"><span data-stu-id="bed37-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bed37-124">Sonnerie simultanée autorisée via la stratégie de voix de l’appelant aux jonctions non activées pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="bed37-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="bed37-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bed37-125">See Also</span></span>


[<span data-ttu-id="bed37-126">Scénarios de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed37-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

