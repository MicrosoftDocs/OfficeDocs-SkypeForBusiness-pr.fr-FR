---
title: 'Lync Server 2013 : Table SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="78a04-102">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78a04-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a04-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="78a04-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="78a04-104">Chaque enregistrement représente une session d’égal à égal, qui peut être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux parties ou tout autre type de session.</span><span class="sxs-lookup"><span data-stu-id="78a04-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="78a04-105">Vous pouvez effectuer une jointure de tableau avec le [tableau multimédia dans Lync Server 2013](lync-server-2013-media-table.md) pour trouver les détails de chaque média impliqué dans cette session.</span><span class="sxs-lookup"><span data-stu-id="78a04-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="78a04-106">Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été déplacés de la table SessionDetails utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a04-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78a04-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="78a04-107">Column</span></span></th>
<th><span data-ttu-id="78a04-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="78a04-108">Data Type</span></span></th>
<th><span data-ttu-id="78a04-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="78a04-109">Key/Index</span></span></th>
<th><span data-ttu-id="78a04-110">Détails</span><span class="sxs-lookup"><span data-stu-id="78a04-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78a04-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="78a04-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="78a04-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="78a04-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-114">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="78a04-114">Time of session request.</span></span> <span data-ttu-id="78a04-115">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="78a04-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="78a04-116">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-118">int</span><span class="sxs-lookup"><span data-stu-id="78a04-118">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-119">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="78a04-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-120">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-120">ID number to identify the session.</span></span> <span data-ttu-id="78a04-121">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. \* pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-122"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-123">identificateur</span><span class="sxs-lookup"><span data-stu-id="78a04-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-124">Un GUID pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="78a04-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-126">DateHeure</span><span class="sxs-lookup"><span data-stu-id="78a04-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="78a04-127">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-128">Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="78a04-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="78a04-129">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-131">int</span><span class="sxs-lookup"><span data-stu-id="78a04-131">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-132">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-133">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-133">ID number to identify the session.</span></span> <span data-ttu-id="78a04-134">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session qui est remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="78a04-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="78a04-135">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-137">int</span><span class="sxs-lookup"><span data-stu-id="78a04-137">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-138">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-139">ID d’un utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-139">ID of one user in the session.</span></span> <span data-ttu-id="78a04-140">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-142">int</span><span class="sxs-lookup"><span data-stu-id="78a04-142">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-143">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-144">ID de l’autre utilisateur de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-144">ID of the other user in the session.</span></span> <span data-ttu-id="78a04-145">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-147">Identificateur</span><span class="sxs-lookup"><span data-stu-id="78a04-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-148">GUID identifiant le point de terminaison utilisé par le premier utilisateur de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="78a04-149">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a04-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-151">Identificateur</span><span class="sxs-lookup"><span data-stu-id="78a04-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-152">GUID identifiant le point de terminaison utilisé par le second utilisateur de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="78a04-153">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a04-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-155">int</span><span class="sxs-lookup"><span data-stu-id="78a04-155">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-156">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-157">URI de l’utilisateur à l’origine de la demande SIP.</span><span class="sxs-lookup"><span data-stu-id="78a04-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="78a04-158">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-160">int</span><span class="sxs-lookup"><span data-stu-id="78a04-160">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-161">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-162">ID de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-162">ID of the user who started the session.</span></span> <span data-ttu-id="78a04-163">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-165">int</span><span class="sxs-lookup"><span data-stu-id="78a04-165">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-166">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-167">Indique l’IDENTIFIant de l’utilisateur pour lequel l’appelant a son nom.</span><span class="sxs-lookup"><span data-stu-id="78a04-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="78a04-168">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-170">int</span><span class="sxs-lookup"><span data-stu-id="78a04-170">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-171">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-172">ID de l’utilisateur avec lequel l’appel est soumis.</span><span class="sxs-lookup"><span data-stu-id="78a04-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="78a04-173">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-175">int</span><span class="sxs-lookup"><span data-stu-id="78a04-175">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-176">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-177">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="78a04-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="78a04-178">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-180">int</span><span class="sxs-lookup"><span data-stu-id="78a04-180">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-181">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-182">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="78a04-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="78a04-183">Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-185">int</span><span class="sxs-lookup"><span data-stu-id="78a04-185">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-186">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-187">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-187">Content type used in the session.</span></span> <span data-ttu-id="78a04-188">Pour plus d’informations, voir la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-190">int</span><span class="sxs-lookup"><span data-stu-id="78a04-190">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-191">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-192">Version du client utilisée par user1.</span><span class="sxs-lookup"><span data-stu-id="78a04-192">Client version used by User1.</span></span> <span data-ttu-id="78a04-193">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-195">int</span><span class="sxs-lookup"><span data-stu-id="78a04-195">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-196">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-197">Version du client utilisée par utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="78a04-197">Client version used by User2.</span></span> <span data-ttu-id="78a04-198">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-200">int</span><span class="sxs-lookup"><span data-stu-id="78a04-200">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-201">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-202">Serveur Edge utilisé par user1.</span><span class="sxs-lookup"><span data-stu-id="78a04-202">Edge Server used by User1.</span></span> <span data-ttu-id="78a04-203">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-205">int</span><span class="sxs-lookup"><span data-stu-id="78a04-205">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-206">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-207">Serveur Edge utilisé par utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="78a04-207">Edge Server used by User2.</span></span> <span data-ttu-id="78a04-208">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-210">bit</span><span class="sxs-lookup"><span data-stu-id="78a04-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-211">Si User1 est connecté à partir d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="78a04-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-213">bit</span><span class="sxs-lookup"><span data-stu-id="78a04-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-214">L’état d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="78a04-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-216">DateHeure</span><span class="sxs-lookup"><span data-stu-id="78a04-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-217">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="78a04-217">The time of the first INVITE request.</span></span> <span data-ttu-id="78a04-218">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="78a04-219">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="78a04-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="78a04-220">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="78a04-221">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="78a04-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-223">DateHeure</span><span class="sxs-lookup"><span data-stu-id="78a04-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-224">Heure de la réponse au premier message d’invitation.</span><span class="sxs-lookup"><span data-stu-id="78a04-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="78a04-225">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="78a04-226">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="78a04-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-228">int</span><span class="sxs-lookup"><span data-stu-id="78a04-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-229">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="78a04-230">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="78a04-231">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="78a04-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-233">int</span><span class="sxs-lookup"><span data-stu-id="78a04-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-234">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="78a04-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-236">int</span><span class="sxs-lookup"><span data-stu-id="78a04-236">int</span></span></p></td>
<td><p><span data-ttu-id="78a04-237">Externes</span><span class="sxs-lookup"><span data-stu-id="78a04-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78a04-238">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="78a04-238">Call priority.</span></span> <span data-ttu-id="78a04-239">Pour plus d’informations, voir la <a href="lync-server-2013-callpriorities-table.md">table CallPriorities dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="78a04-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-241">int</span><span class="sxs-lookup"><span data-stu-id="78a04-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-242">Nombre de messages envoyés par user1 lors de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-244">int</span><span class="sxs-lookup"><span data-stu-id="78a04-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-245">Nombre de messages envoyés par utilisateur2 lors de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-247">DateHeure</span><span class="sxs-lookup"><span data-stu-id="78a04-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-248">Heure à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="78a04-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-250">int</span><span class="sxs-lookup"><span data-stu-id="78a04-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-251">Un ensemble de bits qui indique le type de média de cette session.</span><span class="sxs-lookup"><span data-stu-id="78a04-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="78a04-252">Voici les définitions des types :</span><span class="sxs-lookup"><span data-stu-id="78a04-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78a04-253">MI</span><span class="sxs-lookup"><span data-stu-id="78a04-253">IM</span></span></p></td>
<td><p><span data-ttu-id="78a04-254">1</span><span class="sxs-lookup"><span data-stu-id="78a04-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="78a04-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="78a04-256">deuxième</span><span class="sxs-lookup"><span data-stu-id="78a04-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="78a04-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="78a04-258">4</span><span class="sxs-lookup"><span data-stu-id="78a04-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="78a04-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="78a04-260">version8</span><span class="sxs-lookup"><span data-stu-id="78a04-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-261">AUDIO</span><span class="sxs-lookup"><span data-stu-id="78a04-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="78a04-262">Seiz</span><span class="sxs-lookup"><span data-stu-id="78a04-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-263">CAMÉSCOPE</span><span class="sxs-lookup"><span data-stu-id="78a04-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="78a04-264">32</span><span class="sxs-lookup"><span data-stu-id="78a04-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="78a04-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="78a04-266">64</span><span class="sxs-lookup"><span data-stu-id="78a04-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-268">type</span><span class="sxs-lookup"><span data-stu-id="78a04-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-269">Un ensemble de bits qui indique les attributs User1.</span><span class="sxs-lookup"><span data-stu-id="78a04-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="78a04-270">Les définitions d’attribut suivantes apparaissent :</span><span class="sxs-lookup"><span data-stu-id="78a04-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="78a04-271">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="78a04-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-273">type</span><span class="sxs-lookup"><span data-stu-id="78a04-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-274">Un ensemble de bits qui indique les attributs utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="78a04-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="78a04-275">Les définitions d’attribut suivantes apparaissent :</span><span class="sxs-lookup"><span data-stu-id="78a04-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="78a04-276">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="78a04-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78a04-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-278">type</span><span class="sxs-lookup"><span data-stu-id="78a04-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-279">Un ensemble de bits qui indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="78a04-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="78a04-280">Les définitions d’attribut suivantes apparaissent :</span><span class="sxs-lookup"><span data-stu-id="78a04-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="78a04-281">0x01-nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="78a04-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="78a04-282">0x02-appel émis par l’agent pour le compte d’un groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="78a04-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78a04-283"><strong>Formé</strong></span><span class="sxs-lookup"><span data-stu-id="78a04-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="78a04-284">bit</span><span class="sxs-lookup"><span data-stu-id="78a04-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78a04-285">Pour une utilisation interne par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="78a04-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="78a04-286">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a04-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="78a04-287">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="78a04-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="78a04-288">S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="78a04-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

