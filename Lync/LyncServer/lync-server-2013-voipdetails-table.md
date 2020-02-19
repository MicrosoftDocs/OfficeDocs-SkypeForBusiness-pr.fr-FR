---
title: 'Lync Server 2013 : table VoipDetails'
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
ms.openlocfilehash: 4aac4ae26de4c80f7ed1396e647701a0b49a1c4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42119237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="fc22e-102">Table VoipDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc22e-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc22e-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fc22e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fc22e-104">Chaque enregistrement représente un appel entre deux interlocuteurs, où l’un des interlocuteurs est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="fc22e-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc22e-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="fc22e-105">Column</span></span></th>
<th><span data-ttu-id="fc22e-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="fc22e-106">Data Type</span></span></th>
<th><span data-ttu-id="fc22e-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="fc22e-107">Key/Index</span></span></th>
<th><span data-ttu-id="fc22e-108">Détails</span><span class="sxs-lookup"><span data-stu-id="fc22e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc22e-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fc22e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fc22e-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="fc22e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="fc22e-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="fc22e-112">Time of session request.</span></span> <span data-ttu-id="fc22e-113">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="fc22e-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fc22e-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc22e-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-116">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-116">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="fc22e-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="fc22e-118">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="fc22e-118">ID number to identify the session.</span></span> <span data-ttu-id="fc22e-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="fc22e-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fc22e-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc22e-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-122">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-122">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-124"><strong>PhoneId</strong> de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fc22e-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="fc22e-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="fc22e-126">Si non NULL et que <strong>FromGatewayId</strong> est non NULL, l’appelant était un utilisateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="fc22e-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc22e-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-128">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-128">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-129">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-130"><strong>PhoneId</strong> du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="fc22e-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="fc22e-131">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="fc22e-132">Si non NULL et que <strong>ToGatewayId</strong> est non NULL, le destinataire de l’appel était un utilisateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="fc22e-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc22e-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-134">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-134">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-135">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-136">Serveur de médiation duquel provient l’appel.</span><span class="sxs-lookup"><span data-stu-id="fc22e-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="fc22e-137">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc22e-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-139">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-139">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-140">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-141">Serveur de médiation de destination de l’appel.</span><span class="sxs-lookup"><span data-stu-id="fc22e-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="fc22e-142">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc22e-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-144">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-144">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-145">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-146">Passerelle de laquelle provient l’appel.</span><span class="sxs-lookup"><span data-stu-id="fc22e-146">Gateway the call is coming from.</span></span> <span data-ttu-id="fc22e-147">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc22e-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-149">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-149">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-150">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-151">Passerelle de destination de l’appel.</span><span class="sxs-lookup"><span data-stu-id="fc22e-151">Gateway the call is going to.</span></span> <span data-ttu-id="fc22e-152">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc22e-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-154">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-154">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-155">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-156">URI de l’utilisateur ayant déconnecté l’appel, si l’utilisateur était une URI.</span><span class="sxs-lookup"><span data-stu-id="fc22e-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="fc22e-157">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc22e-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="fc22e-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="fc22e-159">int</span><span class="sxs-lookup"><span data-stu-id="fc22e-159">int</span></span></p></td>
<td><p><span data-ttu-id="fc22e-160">Etranger</span><span class="sxs-lookup"><span data-stu-id="fc22e-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc22e-161">ID du téléphone ayant déconnecté l’appel, si celui-ci a été déconnecté depuis un téléphone.</span><span class="sxs-lookup"><span data-stu-id="fc22e-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="fc22e-162">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fc22e-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

