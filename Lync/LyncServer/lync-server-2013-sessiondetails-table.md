---
title: 'Lync Server 2013 : Table SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="763f3-102">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="763f3-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="763f3-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="763f3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="763f3-104">Chaque enregistrement représente une session d’égal à égal, qui peut être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux parties ou tout autre type de session.</span><span class="sxs-lookup"><span data-stu-id="763f3-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="763f3-105">Vous pouvez effectuer une jointure de tableau avec le [tableau multimédia dans Lync Server 2013](lync-server-2013-media-table.md) pour trouver les détails de chaque média impliqué dans cette session.</span><span class="sxs-lookup"><span data-stu-id="763f3-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="763f3-106">Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été déplacés de la table SessionDetails utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="763f3-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="763f3-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="763f3-107">Column</span></span></th>
<th><span data-ttu-id="763f3-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="763f3-108">Data Type</span></span></th>
<th><span data-ttu-id="763f3-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="763f3-109">Key/Index</span></span></th>
<th><span data-ttu-id="763f3-110">Détails</span><span class="sxs-lookup"><span data-stu-id="763f3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="763f3-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="763f3-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="763f3-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="763f3-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-114">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="763f3-114">Time of session request.</span></span> <span data-ttu-id="763f3-115">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="763f3-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="763f3-116">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-118">int</span><span class="sxs-lookup"><span data-stu-id="763f3-118">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-119">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="763f3-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-120">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-120">ID number to identify the session.</span></span> <span data-ttu-id="763f3-121">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. \* pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-122"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-123">identificateur</span><span class="sxs-lookup"><span data-stu-id="763f3-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-124">Un GUID pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="763f3-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-126">DateHeure</span><span class="sxs-lookup"><span data-stu-id="763f3-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="763f3-127">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-128">Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="763f3-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="763f3-129">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-131">int</span><span class="sxs-lookup"><span data-stu-id="763f3-131">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-132">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-133">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-133">ID number to identify the session.</span></span> <span data-ttu-id="763f3-134">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session qui est remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="763f3-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="763f3-135">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-137">int</span><span class="sxs-lookup"><span data-stu-id="763f3-137">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-138">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-139">ID d’un utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-139">ID of one user in the session.</span></span> <span data-ttu-id="763f3-140">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-142">int</span><span class="sxs-lookup"><span data-stu-id="763f3-142">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-143">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-144">ID de l’autre utilisateur de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-144">ID of the other user in the session.</span></span> <span data-ttu-id="763f3-145">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-147">Identificateur</span><span class="sxs-lookup"><span data-stu-id="763f3-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-148">GUID identifiant le point de terminaison utilisé par le premier utilisateur de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="763f3-149">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="763f3-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-151">Identificateur</span><span class="sxs-lookup"><span data-stu-id="763f3-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-152">GUID identifiant le point de terminaison utilisé par le second utilisateur de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="763f3-153">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="763f3-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-155">int</span><span class="sxs-lookup"><span data-stu-id="763f3-155">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-156">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-157">URI de l’utilisateur à l’origine de la demande SIP.</span><span class="sxs-lookup"><span data-stu-id="763f3-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="763f3-158">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-160">int</span><span class="sxs-lookup"><span data-stu-id="763f3-160">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-161">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-162">ID de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-162">ID of the user who started the session.</span></span> <span data-ttu-id="763f3-163">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-165">int</span><span class="sxs-lookup"><span data-stu-id="763f3-165">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-166">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-167">Indique l’IDENTIFIant de l’utilisateur pour lequel l’appelant a son nom.</span><span class="sxs-lookup"><span data-stu-id="763f3-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="763f3-168">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-170">int</span><span class="sxs-lookup"><span data-stu-id="763f3-170">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-171">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-172">ID de l’utilisateur avec lequel l’appel est soumis.</span><span class="sxs-lookup"><span data-stu-id="763f3-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="763f3-173">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-175">int</span><span class="sxs-lookup"><span data-stu-id="763f3-175">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-176">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-177">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="763f3-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="763f3-178">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-180">int</span><span class="sxs-lookup"><span data-stu-id="763f3-180">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-181">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-182">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="763f3-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="763f3-183">Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-185">int</span><span class="sxs-lookup"><span data-stu-id="763f3-185">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-186">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-187">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-187">Content type used in the session.</span></span> <span data-ttu-id="763f3-188">Pour plus d’informations, voir la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-190">int</span><span class="sxs-lookup"><span data-stu-id="763f3-190">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-191">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-192">Version du client utilisée par user1.</span><span class="sxs-lookup"><span data-stu-id="763f3-192">Client version used by User1.</span></span> <span data-ttu-id="763f3-193">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-195">int</span><span class="sxs-lookup"><span data-stu-id="763f3-195">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-196">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-197">Version du client utilisée par utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="763f3-197">Client version used by User2.</span></span> <span data-ttu-id="763f3-198">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-200">int</span><span class="sxs-lookup"><span data-stu-id="763f3-200">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-201">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-202">Serveur Edge utilisé par user1.</span><span class="sxs-lookup"><span data-stu-id="763f3-202">Edge Server used by User1.</span></span> <span data-ttu-id="763f3-203">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-205">int</span><span class="sxs-lookup"><span data-stu-id="763f3-205">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-206">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-207">Serveur Edge utilisé par utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="763f3-207">Edge Server used by User2.</span></span> <span data-ttu-id="763f3-208">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-210">bit</span><span class="sxs-lookup"><span data-stu-id="763f3-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-211">Si User1 est connecté à partir d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="763f3-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-213">bit</span><span class="sxs-lookup"><span data-stu-id="763f3-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-214">L’état d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="763f3-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-216">DateHeure</span><span class="sxs-lookup"><span data-stu-id="763f3-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-217">Heure de la première demande d’invitation.</span><span class="sxs-lookup"><span data-stu-id="763f3-217">The time of the first INVITE request.</span></span> <span data-ttu-id="763f3-218">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="763f3-219">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="763f3-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="763f3-220">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="763f3-221">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="763f3-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-223">DateHeure</span><span class="sxs-lookup"><span data-stu-id="763f3-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-224">Heure de la réponse au premier message d’invitation.</span><span class="sxs-lookup"><span data-stu-id="763f3-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="763f3-225">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="763f3-226">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="763f3-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-228">int</span><span class="sxs-lookup"><span data-stu-id="763f3-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-229">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="763f3-230">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="763f3-231">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="763f3-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-233">int</span><span class="sxs-lookup"><span data-stu-id="763f3-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-234">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="763f3-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-236">int</span><span class="sxs-lookup"><span data-stu-id="763f3-236">int</span></span></p></td>
<td><p><span data-ttu-id="763f3-237">Externes</span><span class="sxs-lookup"><span data-stu-id="763f3-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="763f3-238">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="763f3-238">Call priority.</span></span> <span data-ttu-id="763f3-239">Pour plus d’informations, voir la <a href="lync-server-2013-callpriorities-table.md">table CallPriorities dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="763f3-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-241">int</span><span class="sxs-lookup"><span data-stu-id="763f3-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-242">Nombre de messages envoyés par user1 lors de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-244">int</span><span class="sxs-lookup"><span data-stu-id="763f3-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-245">Nombre de messages envoyés par utilisateur2 lors de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-247">DateHeure</span><span class="sxs-lookup"><span data-stu-id="763f3-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-248">Heure à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="763f3-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-250">int</span><span class="sxs-lookup"><span data-stu-id="763f3-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-251">Un ensemble de bits qui indique le type de média de cette session.</span><span class="sxs-lookup"><span data-stu-id="763f3-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="763f3-252">Voici les définitions des types:</span><span class="sxs-lookup"><span data-stu-id="763f3-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="763f3-253">MI</span><span class="sxs-lookup"><span data-stu-id="763f3-253">IM</span></span></p></td>
<td><p><span data-ttu-id="763f3-254">1</span><span class="sxs-lookup"><span data-stu-id="763f3-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="763f3-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="763f3-256">2</span><span class="sxs-lookup"><span data-stu-id="763f3-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="763f3-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="763f3-258">4</span><span class="sxs-lookup"><span data-stu-id="763f3-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="763f3-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="763f3-260">version8</span><span class="sxs-lookup"><span data-stu-id="763f3-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-261">AUDIO</span><span class="sxs-lookup"><span data-stu-id="763f3-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="763f3-262">Seiz</span><span class="sxs-lookup"><span data-stu-id="763f3-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-263">CAMÉSCOPE</span><span class="sxs-lookup"><span data-stu-id="763f3-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="763f3-264">32</span><span class="sxs-lookup"><span data-stu-id="763f3-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="763f3-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="763f3-266">64</span><span class="sxs-lookup"><span data-stu-id="763f3-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-268">type</span><span class="sxs-lookup"><span data-stu-id="763f3-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-269">Un ensemble de bits qui indique les attributs User1.</span><span class="sxs-lookup"><span data-stu-id="763f3-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="763f3-270">Les définitions d’attribut suivantes apparaissent:</span><span class="sxs-lookup"><span data-stu-id="763f3-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="763f3-271">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="763f3-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-273">type</span><span class="sxs-lookup"><span data-stu-id="763f3-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-274">Un ensemble de bits qui indique les attributs utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="763f3-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="763f3-275">Les définitions d’attribut suivantes apparaissent:</span><span class="sxs-lookup"><span data-stu-id="763f3-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="763f3-276">0x01-intégré sur le téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="763f3-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="763f3-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-278">type</span><span class="sxs-lookup"><span data-stu-id="763f3-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-279">Un ensemble de bits qui indique les attributs d’appel.</span><span class="sxs-lookup"><span data-stu-id="763f3-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="763f3-280">Les définitions d’attribut suivantes apparaissent:</span><span class="sxs-lookup"><span data-stu-id="763f3-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="763f3-281">0x01-nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="763f3-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="763f3-282">0x02-appel émis par l’agent pour le compte d’un groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="763f3-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="763f3-283"><strong>Formé</strong></span><span class="sxs-lookup"><span data-stu-id="763f3-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="763f3-284">bit</span><span class="sxs-lookup"><span data-stu-id="763f3-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="763f3-285">Pour une utilisation interne par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="763f3-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="763f3-286">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="763f3-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="763f3-287">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="763f3-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="763f3-288">S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="763f3-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

