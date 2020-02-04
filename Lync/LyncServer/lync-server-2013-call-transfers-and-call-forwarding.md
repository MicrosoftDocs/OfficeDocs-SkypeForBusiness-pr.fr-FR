---
title: 'Lync Server 2013 : Transferts et renvois d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512deaf8af03f112e35443c25e46685c42a2f2e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="7c0c9-102">Transferts et renvois d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c0c9-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c0c9-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="7c0c9-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="7c0c9-104">Lorsqu’un point de terminaison RTC est impliqué, le routage géolocalisation analyse l’emplacement du point de terminaison de 134 et le point de terminaison de transfert ou de transfert de l’appel (c.-à-d. transférer/transférer la cible).</span><span class="sxs-lookup"><span data-stu-id="7c0c9-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="7c0c9-105">Le routage basé sur l’emplacement détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="7c0c9-106">Le tableau suivant illustre le scénario d’un utilisateur Lync dans un appel avec un point de terminaison PSTN et l’utilisateur de Lync transfère l’appel vers un autre utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="7c0c9-107">En fonction de l’emplacement du site du réseau du point de terminaison du destinataire, le routage de l’emplacement affecte le routage du transfert ou du transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="7c0c9-108">Lancement du transfert ou du renvoi d’appel</span><span class="sxs-lookup"><span data-stu-id="7c0c9-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0c9-109">Utilisateur à l’origine du transfert/renvoi d’appel</span><span class="sxs-lookup"><span data-stu-id="7c0c9-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="7c0c9-110">Point de terminaison cible dans le même site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel</span><span class="sxs-lookup"><span data-stu-id="7c0c9-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="7c0c9-111">Point de terminaison cible dans un autre site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel</span><span class="sxs-lookup"><span data-stu-id="7c0c9-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="7c0c9-112">Le point de terminaison cible est dans un site réseau inconnu ou un site réseau non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="7c0c9-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0c9-113">Utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="7c0c9-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="7c0c9-114">Le transfert ou renvoi de l’appel est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c0c9-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="7c0c9-115">Le transfert ou renvoi de l’appel n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="7c0c9-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="7c0c9-116">Le transfert ou renvoi de l’appel n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="7c0c9-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="7c0c9-117">Par exemple, un utilisateur Lync dans un appel avec un point de terminaison PSTN transfère l’appel vers un autre utilisateur Lync qui se trouve sur le même site réseau.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="7c0c9-118">Dans ce cas, le transfert de l’appel est autorisé.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="7c0c9-119">Le tableau suivant illustre le scénario d’un utilisateur Lync dans un appel d’un autre utilisateur Lync et l’un d’entre eux transfère l’appel à un point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="7c0c9-120">En fonction de l’emplacement de l’utilisateur sur lequel l’appel est transféré, le tableau décrit les détails relatifs à l’appel par le routage selon l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="7c0c9-121">Transfert ou renvoi de l’appel vers le point de terminaison RTC</span><span class="sxs-lookup"><span data-stu-id="7c0c9-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0c9-122">Point de terminaison cible du transfert/renvoi de l’appel</span><span class="sxs-lookup"><span data-stu-id="7c0c9-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="7c0c9-123">Utilisateurs de Lync sur le même site réseau</span><span class="sxs-lookup"><span data-stu-id="7c0c9-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="7c0c9-124">Utilisateurs de Lync dans différents sites réseau</span><span class="sxs-lookup"><span data-stu-id="7c0c9-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="7c0c9-125">L’un ou les deux utilisateurs de Lync sur un site réseau ou un site réseau inconnu non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="7c0c9-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0c9-126">Point de terminaison RTC</span><span class="sxs-lookup"><span data-stu-id="7c0c9-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c0c9-127">Le transfert ou le renvoi de l’appel est autorisé par la stratégie de routage des communications vocales du site du cessionnaire</span><span class="sxs-lookup"><span data-stu-id="7c0c9-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7c0c9-128">Le transfert ou le renvoi de l’appel est autorisé par la stratégie de routage des communications vocales du site du cessionnaire</span><span class="sxs-lookup"><span data-stu-id="7c0c9-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7c0c9-129">Le transfert ou le renvoi de l’appel est autorisé par la stratégie de voix du cessionnaire, uniquement via des jonctions pour lesquelles le routage géodépendant n’est pas activé</span><span class="sxs-lookup"><span data-stu-id="7c0c9-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="7c0c9-130">Par exemple, un utilisateur Lync dans un appel avec un autre utilisateur Lync figurant dans le même site réseau transfère l’appel vers un point de terminaison PSTN et le transfert d’appel est autorisé.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7c0c9-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c0c9-131">See Also</span></span>


[<span data-ttu-id="7c0c9-132">Scénarios de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c0c9-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

