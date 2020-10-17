---
title: 'Lync Server 2013 : appels sortants'
description: 'Lync Server 2013 : appels sortants.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14f19dec35a6da47a2ddd62657d5d087a854f16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546850"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="83fa5-103">Appels sortants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fa5-103">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83fa5-104">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="83fa5-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="83fa5-105">Le routage des appels sortants d’utilisateurs activés pour le routage des Location-Based est affecté par l’emplacement réseau du point de terminaison de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="83fa5-105">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="83fa5-106">Le tableau suivant montre comment Location-Based routage affecte le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83fa5-106">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="83fa5-107">Appelant passant un appel sortant vers le réseau téléphonique commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="83fa5-107">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="83fa5-108">Point de terminaison d’utilisateur situé dans un site réseau activé pour le routage des Location-Based</span><span class="sxs-lookup"><span data-stu-id="83fa5-108">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="83fa5-109">Point de terminaison de l’utilisateur situé dans un site réseau inconnu ou non activé pour le routage des Location-Based</span><span class="sxs-lookup"><span data-stu-id="83fa5-109">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83fa5-110">Autorisation des appels sortants</span><span class="sxs-lookup"><span data-stu-id="83fa5-110">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="83fa5-111">L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="83fa5-111">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="83fa5-112">L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="83fa5-112">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83fa5-113">Routage des appels sortants</span><span class="sxs-lookup"><span data-stu-id="83fa5-113">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="83fa5-114">L’appel est acheminé en fonction de la stratégie de routage des communications vocales du site réseau</span><span class="sxs-lookup"><span data-stu-id="83fa5-114">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="83fa5-115">L’appel est acheminé en fonction de la stratégie de voix de l’utilisateur et uniquement via des jonctions non activées pour le routage des Location-Based (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="83fa5-115">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="83fa5-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83fa5-116">See Also</span></span>


[<span data-ttu-id="83fa5-117">Scénarios de routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fa5-117">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

