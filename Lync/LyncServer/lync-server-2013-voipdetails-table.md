---
title: 'Lync Server 2013 : Table VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="30a65-102">Table VoipDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30a65-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30a65-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="30a65-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="30a65-104">Chaque enregistrement 1 2 représente un appel vers un tiers, dont au moins un utilisateur est une VoIP.</span><span class="sxs-lookup"><span data-stu-id="30a65-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30a65-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="30a65-105">Column</span></span></th>
<th><span data-ttu-id="30a65-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="30a65-106">Data Type</span></span></th>
<th><span data-ttu-id="30a65-107">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="30a65-107">Key/Index</span></span></th>
<th><span data-ttu-id="30a65-108">Détails</span><span class="sxs-lookup"><span data-stu-id="30a65-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30a65-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="30a65-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="30a65-111">Principal</span><span class="sxs-lookup"><span data-stu-id="30a65-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="30a65-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="30a65-112">Time of session request.</span></span> <span data-ttu-id="30a65-113">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="30a65-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="30a65-114">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30a65-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-116">int</span><span class="sxs-lookup"><span data-stu-id="30a65-116">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-117">Principal</span><span class="sxs-lookup"><span data-stu-id="30a65-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="30a65-118">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="30a65-118">ID number to identify the session.</span></span> <span data-ttu-id="30a65-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="30a65-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="30a65-120">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30a65-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-122">int</span><span class="sxs-lookup"><span data-stu-id="30a65-122">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-123">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-124"><strong>PhoneId</strong> de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="30a65-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="30a65-125">Pour plus d’informations, voir la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="30a65-126">Si ce n’est pas nul et que <strong>FromGatewayId</strong> n’est pas null, l’appelant était un utilisateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="30a65-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30a65-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-128">int</span><span class="sxs-lookup"><span data-stu-id="30a65-128">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-129">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-130"><strong>PhoneId</strong> du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="30a65-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="30a65-131">Pour plus d’informations, voir la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="30a65-132">Si ce n’est pas nul et que <strong>ToGatewayId</strong> n’est pas null, le destinataire de l’appel était un utilisateur RTC.</span><span class="sxs-lookup"><span data-stu-id="30a65-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30a65-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-134">int</span><span class="sxs-lookup"><span data-stu-id="30a65-134">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-135">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-136">Serveur de médiation depuis lequel l’appel provient.</span><span class="sxs-lookup"><span data-stu-id="30a65-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="30a65-137">Pour plus d’informations, voir la <a href="lync-server-2013-mediationservers-table.md">table MediationServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30a65-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-139">int</span><span class="sxs-lookup"><span data-stu-id="30a65-139">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-140">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-141">Le serveur de médiation appelé va.</span><span class="sxs-lookup"><span data-stu-id="30a65-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="30a65-142">Pour plus d’informations, voir la <a href="lync-server-2013-mediationservers-table.md">table MediationServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30a65-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-144">int</span><span class="sxs-lookup"><span data-stu-id="30a65-144">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-145">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-146">Passerelle provenant de l’appel.</span><span class="sxs-lookup"><span data-stu-id="30a65-146">Gateway the call is coming from.</span></span> <span data-ttu-id="30a65-147">Pour plus d’informations, voir le <a href="lync-server-2013-gateways-table.md">tableau passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30a65-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-149">int</span><span class="sxs-lookup"><span data-stu-id="30a65-149">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-150">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-151">Passerelle de destination de l’appel.</span><span class="sxs-lookup"><span data-stu-id="30a65-151">Gateway the call is going to.</span></span> <span data-ttu-id="30a65-152">Pour plus d’informations, voir le <a href="lync-server-2013-gateways-table.md">tableau passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30a65-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-154">int</span><span class="sxs-lookup"><span data-stu-id="30a65-154">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-155">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-156">URI de l’utilisateur qui a déconnecté l’appel, s’il possède un URI.</span><span class="sxs-lookup"><span data-stu-id="30a65-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="30a65-157">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30a65-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="30a65-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="30a65-159">int</span><span class="sxs-lookup"><span data-stu-id="30a65-159">int</span></span></p></td>
<td><p><span data-ttu-id="30a65-160">Externes</span><span class="sxs-lookup"><span data-stu-id="30a65-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30a65-161">ID du téléphone sur lequel l’appel a été déconnecté d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="30a65-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="30a65-162">Pour plus d’informations, voir la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30a65-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

