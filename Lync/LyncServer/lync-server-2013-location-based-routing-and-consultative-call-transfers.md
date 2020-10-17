---
title: 'Lync Server 2013 : Location-Based de routage et de transfert d’appel consultatif'
description: 'Lync Server 2013 : Location-Based le routage et les transferts d’appels consultatifs.'
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567670"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="7c36b-103">Routage et transfert d’appels consultatifs dans Lync Server 2013 Location-Based</span><span class="sxs-lookup"><span data-stu-id="7c36b-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c36b-104">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="7c36b-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="7c36b-105">En plus de mettre en œuvre le routage des Location-Based vers des réunions Lync, l’application de conférence de routage Location-Based applique les restrictions de routage Location-Based sur les transferts d’appel consultatifs qui sont sortants vers des points de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="7c36b-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="7c36b-106">Un transfert d’appel consultatif est un appel établi entre deux parties où une des parties transfère l’appel vers un nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c36b-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="7c36b-107">Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Lync).</span><span class="sxs-lookup"><span data-stu-id="7c36b-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="7c36b-108">L’utilisateur A détermine que l’utilisateur RTC doit être transféré à l’utilisateur B (utilisateur Lync).</span><span class="sxs-lookup"><span data-stu-id="7c36b-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="7c36b-109">L’utilisateur A passe l’appel avec l’utilisateur RTC en conservation et appelle l’utilisateur B. l’utilisateur B accepte de communiquer avec l’utilisateur RTC.</span><span class="sxs-lookup"><span data-stu-id="7c36b-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="7c36b-110">L’utilisateur A transfère l’appel en attente à l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="7c36b-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="7c36b-111">**Flux d’appels consultatifs de transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="7c36b-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="7c36b-112">![Routage géodépendant pour le diagramme de conférence](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Routage géodépendant pour le diagramme de conférence")</span><span class="sxs-lookup"><span data-stu-id="7c36b-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="7c36b-113">Lorsqu’un utilisateur activé pour le routage des Location-Based lance un transfert d’appel consultatif d’un point de terminaison PSTN (comme illustré dans la figure précédente), cela crée deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur Lync A, et l’autre entre Lync User A et l’utilisateur Lync B. le comportement suivant est appliqué par l’application de conférence de routage Location-Based :</span><span class="sxs-lookup"><span data-stu-id="7c36b-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="7c36b-114">Si le routage des jonctions SIP est autorisé à réacheminer l’appel RTC vers le site réseau où se trouve l’utilisateur Lync B (c.-à-d. cible de transfert), le transfert d’appel sera autorisé ; dans le cas contraire, le transfert consultatif est bloqué.</span><span class="sxs-lookup"><span data-stu-id="7c36b-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="7c36b-115">Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée dans le même site réseau que la jonction SIP qui achemine l’appel actif vers le point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="7c36b-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="7c36b-116">Si le routage de jonction SIP de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site réseau où se trouve la partie transférée (Lync User B) ou la partie transférée dans un site réseau inconnu, le transfert d’appel consultatif vers le point de terminaison PSTN (par exemple, la cible de transfert d’appel) est bloqué.</span><span class="sxs-lookup"><span data-stu-id="7c36b-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="7c36b-117">Le tableau suivant décrit la façon dont les Location-Based les restrictions de routage sont appliquées par l’application de conférence de routage Location-Based pour les transferts d’appel consultatifs.</span><span class="sxs-lookup"><span data-stu-id="7c36b-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="7c36b-118">Bien que les points de terminaison PBX ne soient pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="7c36b-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="7c36b-119">Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="7c36b-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-120">Site réseau de la partie transférée d’appel</span><span class="sxs-lookup"><span data-stu-id="7c36b-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="7c36b-121">Site réseau de la cible de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="7c36b-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="7c36b-122">Comportement</span><span class="sxs-lookup"><span data-stu-id="7c36b-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c36b-123">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-124">Utilisateur Lync dans le même site réseau (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="7c36b-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-125">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-126">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-127">Utilisateur Lync dans différents sites réseau (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="7c36b-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-128">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="7c36b-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c36b-129">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-130">Utilisateur Lync dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="7c36b-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="7c36b-131">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="7c36b-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-132">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-133">Utilisateur Lync fédéré</span><span class="sxs-lookup"><span data-stu-id="7c36b-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="7c36b-134">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="7c36b-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c36b-135">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-136">Point de terminaison PBX dans le même site (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="7c36b-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-137">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-138">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-139">Point de terminaison PBX dans différents sites (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="7c36b-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-140">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="7c36b-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c36b-141">Point de terminaison PBX dans le même site (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="7c36b-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-142">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-143">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-144">Point de terminaison PBX dans un autre site (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="7c36b-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-145">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="7c36b-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7c36b-146">Le transfert consultatif est interdit</span><span class="sxs-lookup"><span data-stu-id="7c36b-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c36b-147">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="7c36b-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7c36b-148">Utilisateur Lync dans le même site réseau (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="7c36b-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-149">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-150">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="7c36b-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7c36b-151">Utilisateur Lync dans différents sites réseau (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="7c36b-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7c36b-152">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c36b-153">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="7c36b-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7c36b-154">Utilisateur Lync dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="7c36b-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="7c36b-155">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c36b-156">Point de terminaison PBX dans n’importe quel site</span><span class="sxs-lookup"><span data-stu-id="7c36b-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7c36b-157">Utilisateur Lync fédéré</span><span class="sxs-lookup"><span data-stu-id="7c36b-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="7c36b-158">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="7c36b-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

