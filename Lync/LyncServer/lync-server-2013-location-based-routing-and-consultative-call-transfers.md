---
title: 'Lync Server 2013 : routage par emplacement et transferts d’appel consultatifs'
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
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="3dcea-102">Routage par emplacement et transferts d’appels de consultation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dcea-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dcea-103">_**Dernière modification de la rubrique :** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="3dcea-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="3dcea-104">En plus d’appliquer le routage par emplacement aux réunions Lync, l’application de conférence de routage basée sur l’emplacement applique les restrictions de routage basées sur les emplacements aux points de terminaison RTC.</span><span class="sxs-lookup"><span data-stu-id="3dcea-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="3dcea-105">Un transfert d’appel consultatif est un appel établi entre deux parties dans lequel une des parties transfère l’appel vers un nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3dcea-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="3dcea-106">Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Lync).</span><span class="sxs-lookup"><span data-stu-id="3dcea-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="3dcea-107">Un utilisateur A détermine que l’utilisateur RTC doit être renvoyé à l’utilisateur B (utilisateur Lync).</span><span class="sxs-lookup"><span data-stu-id="3dcea-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="3dcea-108">L’utilisateur A passe l’appel avec l’utilisateur PSTN en attente, et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="3dcea-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="3dcea-109">L’utilisateur A transfère l’appel en attente à l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="3dcea-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="3dcea-110">**Flux des transferts d’appel consultatifs**</span><span class="sxs-lookup"><span data-stu-id="3dcea-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="3dcea-111">![Diagramme Routage géodépendant pour les conférences](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Diagramme Routage géodépendant pour les conférences")</span><span class="sxs-lookup"><span data-stu-id="3dcea-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="3dcea-112">Lorsqu’un utilisateur a activé le routage de géolocalisation, le transfert d’appel d’un point de terminaison PSTN (tel qu’indiqué dans la figure ci-dessus) entraîne la création de deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur de Lync et l’utilisateur Lync B. le comportement suivant est appliqué par l’application de conférence de routage basée sur l’emplacement :</span><span class="sxs-lookup"><span data-stu-id="3dcea-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="3dcea-113">Si le routage SIP Trunk est autorisé à rediriger l’appel RTC vers le site du réseau sur lequel l’utilisateur de Lync B (c.-à-d. destination du transfert) se trouve, le transfert d’appel sera autorisé. dans le cas contraire, le transfert d’appel consultatif sera bloqué.</span><span class="sxs-lookup"><span data-stu-id="3dcea-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="3dcea-114">Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée sur le même site réseau que le Trunk SIP qui achemine l’appel actif vers le point de terminaison RTC.</span><span class="sxs-lookup"><span data-stu-id="3dcea-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="3dcea-115">Si le routage SIP à l’origine de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site du réseau sur lequel la partie transférée (utilisateur Lync B) est située ou si la partie transférée est située sur un site réseau inconnu, le transfert d’appel vers le RTC le point de terminaison (par exemple, cible de transfert d’appel) sera bloqué.</span><span class="sxs-lookup"><span data-stu-id="3dcea-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="3dcea-116">Le tableau suivant décrit la façon dont les restrictions de routage basées sur les emplacements sont appliquées par l’application de conférence de routage basée sur l’emplacement pour les transferts d’appel.</span><span class="sxs-lookup"><span data-stu-id="3dcea-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="3dcea-117">Si les points de terminaison PBX ne sont pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="3dcea-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="3dcea-118">Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="3dcea-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-119">Site réseau de la partie dont l’appel est transféré</span><span class="sxs-lookup"><span data-stu-id="3dcea-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="3dcea-120">Site réseau de la cible de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="3dcea-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="3dcea-121">Comportement</span><span class="sxs-lookup"><span data-stu-id="3dcea-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dcea-122">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-123">Utilisateur Lync sur le même site réseau (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="3dcea-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-124">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-125">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-126">Utilisateur Lync dans différents sites réseau (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="3dcea-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-127">Le transfert consultatif n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dcea-128">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-129">Utilisateur Lync dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="3dcea-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="3dcea-130">Le transfert consultatif n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-131">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-132">Utilisateur fédéré de Lync</span><span class="sxs-lookup"><span data-stu-id="3dcea-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="3dcea-133">Le transfert consultatif n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dcea-134">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-135">Point de terminaison PBX dans le même site (site 1)</span><span class="sxs-lookup"><span data-stu-id="3dcea-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-136">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-137">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-138">Point de terminaison PBX dans un autre site (site 2)</span><span class="sxs-lookup"><span data-stu-id="3dcea-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-139">Le transfert consultatif n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dcea-140">Point de terminaison PBX dans le même site (site 1)</span><span class="sxs-lookup"><span data-stu-id="3dcea-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-141">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-142">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-143">Point de terminaison PBX dans un autre site (site 2)</span><span class="sxs-lookup"><span data-stu-id="3dcea-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-144">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcea-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3dcea-145">Le transfert consultatif n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dcea-146">Point de terminaison PBX dans un site quelconque</span><span class="sxs-lookup"><span data-stu-id="3dcea-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="3dcea-147">Utilisateur Lync sur le même site réseau (par exemple, site 1)</span><span class="sxs-lookup"><span data-stu-id="3dcea-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-148">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-149">Point de terminaison PBX dans un site quelconque</span><span class="sxs-lookup"><span data-stu-id="3dcea-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="3dcea-150">Utilisateur Lync dans différents sites réseau (par exemple, site 2)</span><span class="sxs-lookup"><span data-stu-id="3dcea-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="3dcea-151">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dcea-152">Point de terminaison PBX dans un site quelconque</span><span class="sxs-lookup"><span data-stu-id="3dcea-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="3dcea-153">Utilisateur Lync dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="3dcea-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="3dcea-154">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dcea-155">Point de terminaison PBX dans un site quelconque</span><span class="sxs-lookup"><span data-stu-id="3dcea-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="3dcea-156">Utilisateur fédéré de Lync</span><span class="sxs-lookup"><span data-stu-id="3dcea-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="3dcea-157">Le transfert consultatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="3dcea-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

