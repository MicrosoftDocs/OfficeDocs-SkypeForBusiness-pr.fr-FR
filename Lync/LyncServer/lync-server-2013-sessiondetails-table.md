---
title: 'Lync Server 2013 : table SessionDetails'
description: 'Lync Server 2013 : table SessionDetails.'
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
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569930"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="836ff-103">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="836ff-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="836ff-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="836ff-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="836ff-105">Chaque enregistrement représente une session d’égal à égal ; il peut s’agir d’un appel téléphonique VoIP-VoIP, d’une session de messagerie instantanée à deux participants ou de tout autre type de session.</span><span class="sxs-lookup"><span data-stu-id="836ff-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="836ff-106">Vous pouvez effectuer une jointure de tableau avec la [table Media de Lync Server 2013](lync-server-2013-media-table.md) pour trouver les détails de chaque média impliqué dans cette session.</span><span class="sxs-lookup"><span data-stu-id="836ff-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="836ff-107">Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été supprimés de la table SessionDetails utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="836ff-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="836ff-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="836ff-108">Column</span></span></th>
<th><span data-ttu-id="836ff-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="836ff-109">Data Type</span></span></th>
<th><span data-ttu-id="836ff-110">Clé/index</span><span class="sxs-lookup"><span data-stu-id="836ff-110">Key/Index</span></span></th>
<th><span data-ttu-id="836ff-111">Détails</span><span class="sxs-lookup"><span data-stu-id="836ff-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="836ff-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="836ff-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="836ff-114">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="836ff-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-115">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="836ff-115">Time of session request.</span></span> <span data-ttu-id="836ff-116">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="836ff-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="836ff-117">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-119">int</span><span class="sxs-lookup"><span data-stu-id="836ff-119">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-120">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="836ff-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-121">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-121">ID number to identify the session.</span></span> <span data-ttu-id="836ff-122">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. \* pour plus d’informations, consultez le <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-123"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-124">unique</span><span class="sxs-lookup"><span data-stu-id="836ff-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-125">GUID permettant de corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="836ff-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-127">DateHeure</span><span class="sxs-lookup"><span data-stu-id="836ff-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="836ff-128">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-129">Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="836ff-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="836ff-130">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-132">int</span><span class="sxs-lookup"><span data-stu-id="836ff-132">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-133">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-134">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-134">ID number to identify the session.</span></span> <span data-ttu-id="836ff-135">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="836ff-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="836ff-136">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-138">int</span><span class="sxs-lookup"><span data-stu-id="836ff-138">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-139">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-140">ID d’un utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-140">ID of one user in the session.</span></span> <span data-ttu-id="836ff-141">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-143">int</span><span class="sxs-lookup"><span data-stu-id="836ff-143">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-144">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-145">ID de l’autre utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-145">ID of the other user in the session.</span></span> <span data-ttu-id="836ff-146">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-148">Unique</span><span class="sxs-lookup"><span data-stu-id="836ff-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-149">GUID qui identifie le système d’extrémité utilisé par le premier utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="836ff-150">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="836ff-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-152">Unique</span><span class="sxs-lookup"><span data-stu-id="836ff-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-153">GUID qui identifie le système d’extrémité utilisé par le deuxième utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="836ff-154">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="836ff-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-156">int</span><span class="sxs-lookup"><span data-stu-id="836ff-156">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-157">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-158">URI de l’utilisateur « À » d’origine dans la demande SIP.</span><span class="sxs-lookup"><span data-stu-id="836ff-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="836ff-159">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-161">int</span><span class="sxs-lookup"><span data-stu-id="836ff-161">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-162">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-163">ID de l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-163">ID of the user who started the session.</span></span> <span data-ttu-id="836ff-164">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-166">int</span><span class="sxs-lookup"><span data-stu-id="836ff-166">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-167">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-168">Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle.</span><span class="sxs-lookup"><span data-stu-id="836ff-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="836ff-169">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-171">int</span><span class="sxs-lookup"><span data-stu-id="836ff-171">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-172">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-173">ID de l’utilisateur faisant référence à l’appel.</span><span class="sxs-lookup"><span data-stu-id="836ff-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="836ff-174">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-176">int</span><span class="sxs-lookup"><span data-stu-id="836ff-176">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-177">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-178">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="836ff-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="836ff-179">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-181">int</span><span class="sxs-lookup"><span data-stu-id="836ff-181">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-182">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-183">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="836ff-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="836ff-184">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-186">int</span><span class="sxs-lookup"><span data-stu-id="836ff-186">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-187">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-188">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-188">Content type used in the session.</span></span> <span data-ttu-id="836ff-189">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-191">int</span><span class="sxs-lookup"><span data-stu-id="836ff-191">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-192">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-193">Version de client utilisée par User1.</span><span class="sxs-lookup"><span data-stu-id="836ff-193">Client version used by User1.</span></span> <span data-ttu-id="836ff-194">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-196">int</span><span class="sxs-lookup"><span data-stu-id="836ff-196">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-197">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-198">Version de client utilisée par User2.</span><span class="sxs-lookup"><span data-stu-id="836ff-198">Client version used by User2.</span></span> <span data-ttu-id="836ff-199">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-201">int</span><span class="sxs-lookup"><span data-stu-id="836ff-201">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-202">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-203">Serveur Edge utilisé par User1.</span><span class="sxs-lookup"><span data-stu-id="836ff-203">Edge Server used by User1.</span></span> <span data-ttu-id="836ff-204">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-206">int</span><span class="sxs-lookup"><span data-stu-id="836ff-206">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-207">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-208">Serveur Edge utilisé par User2.</span><span class="sxs-lookup"><span data-stu-id="836ff-208">Edge Server used by User2.</span></span> <span data-ttu-id="836ff-209">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-211">légèrement</span><span class="sxs-lookup"><span data-stu-id="836ff-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-212">Indique si User1 est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="836ff-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-214">légèrement</span><span class="sxs-lookup"><span data-stu-id="836ff-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-215">Indique si User2 est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="836ff-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-217">DateHeure</span><span class="sxs-lookup"><span data-stu-id="836ff-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-218">Heure de la première demande INVITE.</span><span class="sxs-lookup"><span data-stu-id="836ff-218">The time of the first INVITE request.</span></span> <span data-ttu-id="836ff-219">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="836ff-220">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="836ff-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="836ff-221">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="836ff-222">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="836ff-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-224">DateHeure</span><span class="sxs-lookup"><span data-stu-id="836ff-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-225">Heure de la réponse au premier message INVITE.</span><span class="sxs-lookup"><span data-stu-id="836ff-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="836ff-226">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="836ff-227">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="836ff-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-229">int</span><span class="sxs-lookup"><span data-stu-id="836ff-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-p121">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="836ff-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-234">int</span><span class="sxs-lookup"><span data-stu-id="836ff-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-235">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="836ff-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-237">int</span><span class="sxs-lookup"><span data-stu-id="836ff-237">int</span></span></p></td>
<td><p><span data-ttu-id="836ff-238">Etranger</span><span class="sxs-lookup"><span data-stu-id="836ff-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="836ff-239">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="836ff-239">Call priority.</span></span> <span data-ttu-id="836ff-240">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-callpriorities-table.md">table table callpriorities dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="836ff-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-242">int</span><span class="sxs-lookup"><span data-stu-id="836ff-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-243">Nombre de messages envoyés par User1 durant la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-245">int</span><span class="sxs-lookup"><span data-stu-id="836ff-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-246">Nombre de messages envoyés par User2 durant la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-248">DateHeure</span><span class="sxs-lookup"><span data-stu-id="836ff-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-249">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="836ff-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-251">int</span><span class="sxs-lookup"><span data-stu-id="836ff-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-p123">Jeu de bits qui indique le type de média de cette session. Voici les définitions des types :</span><span class="sxs-lookup"><span data-stu-id="836ff-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="836ff-254">IM (Messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="836ff-254">IM</span></span></p></td>
<td><p><span data-ttu-id="836ff-255">0,1</span><span class="sxs-lookup"><span data-stu-id="836ff-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="836ff-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="836ff-257">n°2</span><span class="sxs-lookup"><span data-stu-id="836ff-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="836ff-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="836ff-259">4 </span><span class="sxs-lookup"><span data-stu-id="836ff-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="836ff-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="836ff-261">8 </span><span class="sxs-lookup"><span data-stu-id="836ff-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-262">SIGNAUX</span><span class="sxs-lookup"><span data-stu-id="836ff-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="836ff-263">16 </span><span class="sxs-lookup"><span data-stu-id="836ff-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-264">VIDÉO</span><span class="sxs-lookup"><span data-stu-id="836ff-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="836ff-265">32</span><span class="sxs-lookup"><span data-stu-id="836ff-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="836ff-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="836ff-267">64</span><span class="sxs-lookup"><span data-stu-id="836ff-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-269">type</span><span class="sxs-lookup"><span data-stu-id="836ff-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-p124">Jeu de bits qui indique les attributs de User1. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="836ff-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="836ff-272">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="836ff-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-274">type</span><span class="sxs-lookup"><span data-stu-id="836ff-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-p125">Jeu de bits qui indique les attributs de User2. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="836ff-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="836ff-277">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="836ff-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="836ff-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-279">type</span><span class="sxs-lookup"><span data-stu-id="836ff-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-p126">Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="836ff-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="836ff-282">0x01 - Nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="836ff-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="836ff-283">0x02 - Appel effectué par un agent pour le compte d’un groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="836ff-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="836ff-284"><strong>Traiter</strong></span><span class="sxs-lookup"><span data-stu-id="836ff-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="836ff-285">légèrement</span><span class="sxs-lookup"><span data-stu-id="836ff-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="836ff-286">Réservé à un usage interne par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="836ff-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="836ff-287">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="836ff-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="836ff-288">\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="836ff-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="836ff-289">Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="836ff-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

