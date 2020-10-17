---
title: 'Lync Server 2013 : table VoipDetails'
description: 'Lync Server 2013 : table VoipDetails.'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566280"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="1ea46-103">Table VoipDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ea46-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea46-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1ea46-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1ea46-105">Chaque enregistrement représente un appel entre deux interlocuteurs, où l’un des interlocuteurs est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="1ea46-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ea46-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="1ea46-106">Column</span></span></th>
<th><span data-ttu-id="1ea46-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="1ea46-107">Data Type</span></span></th>
<th><span data-ttu-id="1ea46-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="1ea46-108">Key/Index</span></span></th>
<th><span data-ttu-id="1ea46-109">Détails</span><span class="sxs-lookup"><span data-stu-id="1ea46-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ea46-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1ea46-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ea46-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="1ea46-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ea46-113">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="1ea46-113">Time of session request.</span></span> <span data-ttu-id="1ea46-114">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="1ea46-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1ea46-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea46-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-117">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-117">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-118">Primaire</span><span class="sxs-lookup"><span data-stu-id="1ea46-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ea46-119">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="1ea46-119">ID number to identify the session.</span></span> <span data-ttu-id="1ea46-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="1ea46-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1ea46-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ea46-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-123">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-123">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-124">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-125"><strong>PhoneId</strong> de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="1ea46-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="1ea46-126">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="1ea46-127">Si non NULL et que <strong>FromGatewayId</strong> est non NULL, l’appelant était un utilisateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ea46-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea46-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-129">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-129">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-130">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-131"><strong>PhoneId</strong> du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="1ea46-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="1ea46-132">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="1ea46-133">Si non NULL et que <strong>ToGatewayId</strong> est non NULL, le destinataire de l’appel était un utilisateur PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ea46-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ea46-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-135">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-135">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-136">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-137">Serveur de médiation duquel provient l’appel.</span><span class="sxs-lookup"><span data-stu-id="1ea46-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="1ea46-138">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea46-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-140">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-140">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-141">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-142">Serveur de médiation de destination de l’appel.</span><span class="sxs-lookup"><span data-stu-id="1ea46-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="1ea46-143">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">table table mediationservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ea46-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-145">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-145">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-146">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-147">Passerelle de laquelle provient l’appel.</span><span class="sxs-lookup"><span data-stu-id="1ea46-147">Gateway the call is coming from.</span></span> <span data-ttu-id="1ea46-148">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea46-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-150">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-150">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-151">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-152">Passerelle de destination de l’appel.</span><span class="sxs-lookup"><span data-stu-id="1ea46-152">Gateway the call is going to.</span></span> <span data-ttu-id="1ea46-153">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-gateways-table.md">tableau des passerelles dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ea46-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-155">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-155">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-156">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-157">URI de l’utilisateur ayant déconnecté l’appel, si l’utilisateur était une URI.</span><span class="sxs-lookup"><span data-stu-id="1ea46-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="1ea46-158">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea46-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="1ea46-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ea46-160">int</span><span class="sxs-lookup"><span data-stu-id="1ea46-160">int</span></span></p></td>
<td><p><span data-ttu-id="1ea46-161">Etranger</span><span class="sxs-lookup"><span data-stu-id="1ea46-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ea46-162">ID du téléphone ayant déconnecté l’appel, si celui-ci a été déconnecté depuis un téléphone.</span><span class="sxs-lookup"><span data-stu-id="1ea46-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="1ea46-163">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1ea46-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

