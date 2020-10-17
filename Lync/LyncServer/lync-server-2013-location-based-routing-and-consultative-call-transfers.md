---
title: 'Lync Server 2013 : Location-Based de routage et de transfert d’appel consultatif'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513811"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="c8b42-102">Routage et transfert d’appels consultatifs dans Lync Server 2013 Location-Based</span><span class="sxs-lookup"><span data-stu-id="c8b42-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8b42-103">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="c8b42-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="c8b42-104">En plus de mettre en œuvre le routage des Location-Based vers des réunions Lync, l’application de conférence de routage Location-Based applique les restrictions de routage Location-Based sur les transferts d’appel consultatifs qui sont sortants vers des points de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="c8b42-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="c8b42-105">Un transfert d’appel consultatif est un appel établi entre deux parties où une des parties transfère l’appel vers un nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c8b42-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="c8b42-106">Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Lync).</span><span class="sxs-lookup"><span data-stu-id="c8b42-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="c8b42-107">L’utilisateur A détermine que l’utilisateur RTC doit être transféré à l’utilisateur B (utilisateur Lync).</span><span class="sxs-lookup"><span data-stu-id="c8b42-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="c8b42-108">L’utilisateur A passe l’appel avec l’utilisateur RTC en conservation et appelle l’utilisateur B. l’utilisateur B accepte de communiquer avec l’utilisateur RTC.</span><span class="sxs-lookup"><span data-stu-id="c8b42-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="c8b42-109">L’utilisateur A transfère l’appel en attente à l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="c8b42-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="c8b42-110">**Flux d’appels consultatifs de transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="c8b42-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="c8b42-111">![Routage géodépendant pour le diagramme de conférence](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Routage géodépendant pour le diagramme de conférence")</span><span class="sxs-lookup"><span data-stu-id="c8b42-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="c8b42-112">Lorsqu’un utilisateur activé pour le routage des Location-Based lance un transfert d’appel consultatif d’un point de terminaison PSTN (comme illustré dans la figure précédente), cela crée deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur Lync A, et l’autre entre Lync User A et l’utilisateur Lync B. le comportement suivant est appliqué par l’application de conférence de routage Location-Based :</span><span class="sxs-lookup"><span data-stu-id="c8b42-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c8b42-113">Si le routage des jonctions SIP est autorisé à réacheminer l’appel RTC vers le site réseau où se trouve l’utilisateur Lync B (c.-à-d. cible de transfert), le transfert d’appel sera autorisé ; dans le cas contraire, le transfert consultatif est bloqué.</span><span class="sxs-lookup"><span data-stu-id="c8b42-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="c8b42-114">Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée dans le même site réseau que la jonction SIP qui achemine l’appel actif vers le point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="c8b42-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="c8b42-115">Si le routage de jonction SIP de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site réseau où se trouve la partie transférée (Lync User B) ou la partie transférée dans un site réseau inconnu, le transfert d’appel consultatif vers le point de terminaison PSTN (par exemple, la cible de transfert d’appel) est bloqué.</span><span class="sxs-lookup"><span data-stu-id="c8b42-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="c8b42-116">Le tableau suivant décrit la façon dont les Location-Based les restrictions de routage sont appliquées par l’application de conférence de routage Location-Based pour les transferts d’appel consultatifs.</span><span class="sxs-lookup"><span data-stu-id="c8b42-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="c8b42-117">Bien que les points de terminaison PBX ne soient pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="c8b42-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="c8b42-118">Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="c8b42-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-119">Site réseau de la partie transférée d’appel</span><span class="sxs-lookup"><span data-stu-id="c8b42-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="c8b42-120">Site réseau de la cible de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="c8b42-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="c8b42-121">Comportement</span><span class="sxs-lookup"><span data-stu-id="c8b42-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b42-122">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-123">Utilisateur Lync dans le même site réseau (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="c8b42-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-124">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-125">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-126">Utilisateur Lync dans différents sites réseau (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="c8b42-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-127">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="c8b42-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b42-128">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-129">Utilisateur Lync dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="c8b42-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c8b42-130">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="c8b42-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-131">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-132">Utilisateur Lync fédéré</span><span class="sxs-lookup"><span data-stu-id="c8b42-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c8b42-133">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="c8b42-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b42-134">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-135">Point de terminaison PBX dans le même site (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="c8b42-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-136">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-137">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-138">Point de terminaison PBX dans différents sites (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="c8b42-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-139">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="c8b42-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b42-140">Point de terminaison PBX dans le même site (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="c8b42-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-141">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-142">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-143">Point de terminaison PBX dans un autre site (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="c8b42-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-144">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="c8b42-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c8b42-145">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="c8b42-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b42-146">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="c8b42-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c8b42-147">Utilisateur Lync dans le même site réseau (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="c8b42-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-148">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-149">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="c8b42-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c8b42-150">Utilisateur Lync dans différents sites réseau (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="c8b42-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c8b42-151">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b42-152">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="c8b42-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c8b42-153">Utilisateur Lync dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="c8b42-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c8b42-154">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b42-155">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="c8b42-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c8b42-156">Utilisateur Lync fédéré</span><span class="sxs-lookup"><span data-stu-id="c8b42-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c8b42-157">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="c8b42-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

