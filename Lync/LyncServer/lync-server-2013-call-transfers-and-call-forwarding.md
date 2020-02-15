---
title: 'Lync Server 2013 : transferts d’appels et transfert d’appel'
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
ms.openlocfilehash: 46b16ad2faac58a5999b803c75d02e01da0da2dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="27b43-102">Transferts d’appels et transfert d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b43-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27b43-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="27b43-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="27b43-104">Lorsqu’un point de terminaison PSTN est impliqué, le routage géodépendant analyse l’emplacement du point de terminaison du Calle et le point de terminaison vers lequel l’appel sera transféré ou transféré (c.-à-d. cible de transfert/transfert).</span><span class="sxs-lookup"><span data-stu-id="27b43-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="27b43-105">Routage géodépendant détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="27b43-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="27b43-106">Le tableau suivant illustre le scénario d’un utilisateur Lync dans un appel avec un point de terminaison PSTN, et l’utilisateur Lync transfère l’appel vers un autre utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="27b43-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="27b43-107">En fonction de l’emplacement du site réseau du point de terminaison du cessionnaire, le routage géodépendant a une incidence sur le routage du transfert d’appel ou vers l’aval.</span><span class="sxs-lookup"><span data-stu-id="27b43-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="27b43-108">Lancement du transfert ou du transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="27b43-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27b43-109">Utilisateur lançant le transfert/transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="27b43-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="27b43-110">Le point de terminaison cible se trouve dans le même site réseau que l’utilisateur à l’origine du transfert ou du transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="27b43-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="27b43-111">Le point de terminaison cible se trouve dans un autre site réseau que l’utilisateur à l’origine du transfert ou du transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="27b43-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="27b43-112">Le point de terminaison cible se trouve dans un site réseau inconnu ou le site réseau n’est pas activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="27b43-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27b43-113">Utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="27b43-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="27b43-114">Le transfert d’appel ou le transfert est autorisé</span><span class="sxs-lookup"><span data-stu-id="27b43-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="27b43-115">Le transfert d’appel ou le transfert n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="27b43-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="27b43-116">Le transfert d’appel ou le transfert n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="27b43-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="27b43-117">Par exemple : un utilisateur Lync dans un appel avec un point de terminaison PSTN transfère l’appel vers un autre utilisateur Lync qui se trouve dans le même site réseau.</span><span class="sxs-lookup"><span data-stu-id="27b43-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="27b43-118">Dans ce cas, le transfert d’appel est autorisé.</span><span class="sxs-lookup"><span data-stu-id="27b43-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="27b43-119">Le tableau suivant illustre le scénario d’un utilisateur Lync dans un appel avec un autre utilisateur Lync, et l’un des utilisateurs transfère l’appel vers un point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="27b43-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="27b43-120">En fonction de l’emplacement de l’utilisateur vers lequel l’appel est transféré, le tableau explique en détail comment le routage géodépendant affecte l’appel.</span><span class="sxs-lookup"><span data-stu-id="27b43-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="27b43-121">Transfert d’appel ou transfert vers le point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="27b43-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27b43-122">Cible de point de terminaison/transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="27b43-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="27b43-123">Utilisateurs Lync dans le même site réseau</span><span class="sxs-lookup"><span data-stu-id="27b43-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="27b43-124">Utilisateurs Lync dans différents sites réseau</span><span class="sxs-lookup"><span data-stu-id="27b43-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="27b43-125">Un ou les deux utilisateurs Lync dans un site réseau inconnu ou un site réseau non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="27b43-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27b43-126">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="27b43-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27b43-127">Transfert d’appel ou transfert autorisé par la stratégie de routage des communications vocales du site de l’utilisateur transféré</span><span class="sxs-lookup"><span data-stu-id="27b43-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="27b43-128">Transfert d’appel ou transfert autorisé par la stratégie de routage des communications vocales du site de l’utilisateur transféré</span><span class="sxs-lookup"><span data-stu-id="27b43-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="27b43-129">Transfert d’appel ou transfert autorisé par la stratégie de voix de l’utilisateur transféré uniquement via des jonctions non activées pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="27b43-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="27b43-130">Par exemple : un utilisateur Lync dans un appel avec un autre utilisateur Lync qui se trouve sur le même site réseau transfère l’appel vers un point de terminaison PSTN et le transfert d’appel est autorisé.</span><span class="sxs-lookup"><span data-stu-id="27b43-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="27b43-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27b43-131">See Also</span></span>


[<span data-ttu-id="27b43-132">Scénarios de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27b43-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

