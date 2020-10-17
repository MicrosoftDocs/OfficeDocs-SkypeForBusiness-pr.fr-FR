---
title: 'Lync Server 2013 : table SessionDetails'
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
ms.openlocfilehash: e49cb6a5715b95758a5e7520c69dd45b757b10c7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510051"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="f2fef-102">Table SessionDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2fef-102">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2fef-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f2fef-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f2fef-104">Chaque enregistrement représente une session d’égal à égal ; il peut s’agir d’un appel téléphonique VoIP-VoIP, d’une session de messagerie instantanée à deux participants ou de tout autre type de session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="f2fef-105">Vous pouvez effectuer une jointure de tableau avec la [table Media de Lync Server 2013](lync-server-2013-media-table.md) pour trouver les détails de chaque média impliqué dans cette session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="f2fef-106">Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été supprimés de la table SessionDetails utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2fef-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2fef-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="f2fef-107">Column</span></span></th>
<th><span data-ttu-id="f2fef-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="f2fef-108">Data Type</span></span></th>
<th><span data-ttu-id="f2fef-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="f2fef-109">Key/Index</span></span></th>
<th><span data-ttu-id="f2fef-110">Détails</span><span class="sxs-lookup"><span data-stu-id="f2fef-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f2fef-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f2fef-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="f2fef-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-114">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-114">Time of session request.</span></span> <span data-ttu-id="f2fef-115">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f2fef-116">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-118">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-118">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-119">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="f2fef-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-120">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-120">ID number to identify the session.</span></span> <span data-ttu-id="f2fef-121">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. \* pour plus d’informations, consultez le <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-122"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-123">unique</span><span class="sxs-lookup"><span data-stu-id="f2fef-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-124">GUID permettant de corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="f2fef-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-126">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f2fef-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="f2fef-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-128">Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle.</span><span class="sxs-lookup"><span data-stu-id="f2fef-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="f2fef-129">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-131">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-131">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-132">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-133">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-133">ID number to identify the session.</span></span> <span data-ttu-id="f2fef-134">Utilisé conjointement avec <strong>ReplacesDialogIdTime</strong> pour identifier de manière unique une session remplacée par cette session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="f2fef-135">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-137">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-137">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-138">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-139">ID d’un utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-139">ID of one user in the session.</span></span> <span data-ttu-id="f2fef-140">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-142">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-142">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-143">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-144">ID de l’autre utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-144">ID of the other user in the session.</span></span> <span data-ttu-id="f2fef-145">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-147">Unique</span><span class="sxs-lookup"><span data-stu-id="f2fef-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-148">GUID qui identifie le système d’extrémité utilisé par le premier utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="f2fef-149">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2fef-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-151">Unique</span><span class="sxs-lookup"><span data-stu-id="f2fef-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-152">GUID qui identifie le système d’extrémité utilisé par le deuxième utilisateur dans la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="f2fef-153">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2fef-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-155">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-155">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-156">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-157">URI de l’utilisateur « À » d’origine dans la demande SIP.</span><span class="sxs-lookup"><span data-stu-id="f2fef-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="f2fef-158">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-160">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-160">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-161">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-162">ID de l’utilisateur ayant démarré la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-162">ID of the user who started the session.</span></span> <span data-ttu-id="f2fef-163">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-165">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-165">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-166">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-167">Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle.</span><span class="sxs-lookup"><span data-stu-id="f2fef-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="f2fef-168">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-170">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-170">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-171">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-172">ID de l’utilisateur faisant référence à l’appel.</span><span class="sxs-lookup"><span data-stu-id="f2fef-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="f2fef-173">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-175">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-175">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-176">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-177">ID du serveur frontal utilisé pour cette session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="f2fef-178">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-180">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-180">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-181">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-182">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="f2fef-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="f2fef-183">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-185">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-185">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-186">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-187">Type de contenu utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-187">Content type used in the session.</span></span> <span data-ttu-id="f2fef-188">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-contenttypes-table.md">table ContentTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-190">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-190">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-191">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-192">Version de client utilisée par User1.</span><span class="sxs-lookup"><span data-stu-id="f2fef-192">Client version used by User1.</span></span> <span data-ttu-id="f2fef-193">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-195">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-195">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-196">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-197">Version de client utilisée par User2.</span><span class="sxs-lookup"><span data-stu-id="f2fef-197">Client version used by User2.</span></span> <span data-ttu-id="f2fef-198">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-200">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-200">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-201">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-202">Serveur Edge utilisé par User1.</span><span class="sxs-lookup"><span data-stu-id="f2fef-202">Edge Server used by User1.</span></span> <span data-ttu-id="f2fef-203">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-205">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-205">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-206">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-207">Serveur Edge utilisé par User2.</span><span class="sxs-lookup"><span data-stu-id="f2fef-207">Edge Server used by User2.</span></span> <span data-ttu-id="f2fef-208">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-210">légèrement</span><span class="sxs-lookup"><span data-stu-id="f2fef-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-211">Indique si User1 est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="f2fef-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-213">légèrement</span><span class="sxs-lookup"><span data-stu-id="f2fef-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-214">Indique si User2 est connecté en interne.</span><span class="sxs-lookup"><span data-stu-id="f2fef-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-216">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f2fef-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-217">Heure de la première demande INVITE.</span><span class="sxs-lookup"><span data-stu-id="f2fef-217">The time of the first INVITE request.</span></span> <span data-ttu-id="f2fef-218">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f2fef-219">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="f2fef-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="f2fef-220">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f2fef-221">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="f2fef-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-223">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f2fef-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-224">Heure de la réponse au premier message INVITE.</span><span class="sxs-lookup"><span data-stu-id="f2fef-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="f2fef-225">Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f2fef-226">En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="f2fef-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-228">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-p121">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="f2fef-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-233">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-234">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="f2fef-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-236">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-236">int</span></span></p></td>
<td><p><span data-ttu-id="f2fef-237">Etranger</span><span class="sxs-lookup"><span data-stu-id="f2fef-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2fef-238">Priorité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f2fef-238">Call priority.</span></span> <span data-ttu-id="f2fef-239">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-callpriorities-table.md">table table callpriorities dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f2fef-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-241">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-242">Nombre de messages envoyés par User1 durant la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-244">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-245">Nombre de messages envoyés par User2 durant la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-247">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f2fef-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-248">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="f2fef-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-250">int</span><span class="sxs-lookup"><span data-stu-id="f2fef-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-p123">Jeu de bits qui indique le type de média de cette session. Voici les définitions des types :</span><span class="sxs-lookup"><span data-stu-id="f2fef-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-253">IM (Messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="f2fef-253">IM</span></span></p></td>
<td><p><span data-ttu-id="f2fef-254">0,1</span><span class="sxs-lookup"><span data-stu-id="f2fef-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="f2fef-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="f2fef-256">n°2</span><span class="sxs-lookup"><span data-stu-id="f2fef-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="f2fef-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="f2fef-258">4 </span><span class="sxs-lookup"><span data-stu-id="f2fef-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="f2fef-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="f2fef-260">8 </span><span class="sxs-lookup"><span data-stu-id="f2fef-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-261">SIGNAUX</span><span class="sxs-lookup"><span data-stu-id="f2fef-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="f2fef-262">16 </span><span class="sxs-lookup"><span data-stu-id="f2fef-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-263">VIDÉO</span><span class="sxs-lookup"><span data-stu-id="f2fef-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="f2fef-264">32</span><span class="sxs-lookup"><span data-stu-id="f2fef-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="f2fef-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="f2fef-266">64</span><span class="sxs-lookup"><span data-stu-id="f2fef-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-268">type</span><span class="sxs-lookup"><span data-stu-id="f2fef-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-p124">Jeu de bits qui indique les attributs de User1. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="f2fef-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2fef-271">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="f2fef-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-273">type</span><span class="sxs-lookup"><span data-stu-id="f2fef-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-p125">Jeu de bits qui indique les attributs de User2. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="f2fef-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2fef-276">0x01 - Intégré dans téléphone de bureau</span><span class="sxs-lookup"><span data-stu-id="f2fef-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fef-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-278">type</span><span class="sxs-lookup"><span data-stu-id="f2fef-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-p126">Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :</span><span class="sxs-lookup"><span data-stu-id="f2fef-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2fef-281">0x01 - Nouvelle tentative de session</span><span class="sxs-lookup"><span data-stu-id="f2fef-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="f2fef-282">0x02 - Appel effectué par un agent pour le compte d’un groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="f2fef-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fef-283"><strong>Traiter</strong></span><span class="sxs-lookup"><span data-stu-id="f2fef-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="f2fef-284">légèrement</span><span class="sxs-lookup"><span data-stu-id="f2fef-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2fef-285">Réservé à un usage interne par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="f2fef-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="f2fef-286">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2fef-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2fef-287">\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="f2fef-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="f2fef-288">Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="f2fef-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

