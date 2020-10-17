---
title: 'Lync Server 2013 : tblNode'
description: 'Lync Server 2013 : tblNode.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547550"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="ad61d-103">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad61d-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad61d-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ad61d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ad61d-105">tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou de salle de conversation) telle qu’elle est gérée dans le panneau de configuration et les cmdlets administratives Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad61d-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="ad61d-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="ad61d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad61d-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="ad61d-107">Column</span></span></th>
<th><span data-ttu-id="ad61d-108">Type</span><span class="sxs-lookup"><span data-stu-id="ad61d-108">Type</span></span></th>
<th><span data-ttu-id="ad61d-109">Description</span><span class="sxs-lookup"><span data-stu-id="ad61d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="ad61d-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-111">int, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-112">ID de nœud (numéro unique).</span><span class="sxs-lookup"><span data-stu-id="ad61d-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="ad61d-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="ad61d-114">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-115">GUID de nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-116">parentID</span><span class="sxs-lookup"><span data-stu-id="ad61d-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-117">int</span><span class="sxs-lookup"><span data-stu-id="ad61d-117">int</span></span></p></td>
<td><p><span data-ttu-id="ad61d-p101">ID de nœud du parent. Le nœud racine (avec l’ID 1) s’inclut lui-même comme parent.</span><span class="sxs-lookup"><span data-stu-id="ad61d-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="ad61d-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="ad61d-121">bit, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-122">True si le nœud est une catégorie.</span><span class="sxs-lookup"><span data-stu-id="ad61d-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="ad61d-123">False si le nœud est une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ad61d-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="ad61d-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="ad61d-125">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-126">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="ad61d-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="ad61d-128">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-129">Description du nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-130">invite</span><span class="sxs-lookup"><span data-stu-id="ad61d-130">invite</span></span></p></td>
<td><p><span data-ttu-id="ad61d-131">légèrement</span><span class="sxs-lookup"><span data-stu-id="ad61d-131">bit</span></span></p></td>
<td><p><span data-ttu-id="ad61d-132">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="ad61d-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-133">True si les invitations sont activées.</span><span class="sxs-lookup"><span data-stu-id="ad61d-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="ad61d-134">False si les invitations sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="ad61d-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="ad61d-135">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="ad61d-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-136">False si les invitations sont désactivées (remplace la catégorie parente).</span><span class="sxs-lookup"><span data-stu-id="ad61d-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="ad61d-137">Null si le paramètre d’invitation est hérité de la catégorie parente.</span><span class="sxs-lookup"><span data-stu-id="ad61d-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-138">connecté</span><span class="sxs-lookup"><span data-stu-id="ad61d-138">logged</span></span></p></td>
<td><p><span data-ttu-id="ad61d-139">légèrement</span><span class="sxs-lookup"><span data-stu-id="ad61d-139">bit</span></span></p></td>
<td><p><span data-ttu-id="ad61d-140">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="ad61d-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-141">True si l’historique des conversations est activé.</span><span class="sxs-lookup"><span data-stu-id="ad61d-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="ad61d-142">False si l’historique des conversations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="ad61d-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="ad61d-143">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="ad61d-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-144">Valeurs.</span><span class="sxs-lookup"><span data-stu-id="ad61d-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-145">filePost</span><span class="sxs-lookup"><span data-stu-id="ad61d-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="ad61d-146">légèrement</span><span class="sxs-lookup"><span data-stu-id="ad61d-146">bit</span></span></p></td>
<td><p><span data-ttu-id="ad61d-147">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="ad61d-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-148">True si les téléchargements de fichiers sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="ad61d-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="ad61d-149">False si les téléchargements de fichiers sont interdits.</span><span class="sxs-lookup"><span data-stu-id="ad61d-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="ad61d-150">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="ad61d-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-151">Valeurs.</span><span class="sxs-lookup"><span data-stu-id="ad61d-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-152">désactivé</span><span class="sxs-lookup"><span data-stu-id="ad61d-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="ad61d-153">bit, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-p102">True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories.)</span><span class="sxs-lookup"><span data-stu-id="ad61d-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-157">connaissance</span><span class="sxs-lookup"><span data-stu-id="ad61d-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="ad61d-158">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-159">Comportement (tiré de la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="ad61d-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-160">4 : normal (salles de conversation normales).</span><span class="sxs-lookup"><span data-stu-id="ad61d-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="ad61d-161">5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer).</span><span class="sxs-lookup"><span data-stu-id="ad61d-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="ad61d-162">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="ad61d-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-163">visibility</span><span class="sxs-lookup"><span data-stu-id="ad61d-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="ad61d-164">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-165">Visibilité (tirée de la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="ad61d-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="ad61d-166">2 : privée</span><span class="sxs-lookup"><span data-stu-id="ad61d-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="ad61d-167">3 : limitée par une étendue</span><span class="sxs-lookup"><span data-stu-id="ad61d-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="ad61d-168">6 : ouvert</span><span class="sxs-lookup"><span data-stu-id="ad61d-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="ad61d-169">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="ad61d-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-170">siopID</span><span class="sxs-lookup"><span data-stu-id="ad61d-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-171">GUID</span><span class="sxs-lookup"><span data-stu-id="ad61d-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-p103">GUID de complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de complément.)</span><span class="sxs-lookup"><span data-stu-id="ad61d-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="ad61d-174">Les informations relatives aux compléments sont recherchées dans la table SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="ad61d-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="ad61d-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="ad61d-176">int, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-177">ID du principal ayant créé ce nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="ad61d-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="ad61d-179">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-180">Horodatage de la création de nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="ad61d-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="ad61d-182">int, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-183">ID du principal ayant effectué la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="ad61d-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="ad61d-185">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="ad61d-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="ad61d-186">Horodatage de la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="ad61d-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="ad61d-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="ad61d-188">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ad61d-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="ad61d-p104">Heure de la dernière opération de vidage (suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) ayant affecté ce nœud. Utilisé uniquement par le mécanisme de mise à jour du cache interne du service de conversation.</span><span class="sxs-lookup"><span data-stu-id="ad61d-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ad61d-191">Keys</span><span class="sxs-lookup"><span data-stu-id="ad61d-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad61d-192">Colonne</span><span class="sxs-lookup"><span data-stu-id="ad61d-192">Column</span></span></th>
<th><span data-ttu-id="ad61d-193">Description</span><span class="sxs-lookup"><span data-stu-id="ad61d-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="ad61d-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-195">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ad61d-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-196">connaissance</span><span class="sxs-lookup"><span data-stu-id="ad61d-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="ad61d-197">Clé étrangère avec recherche dans la table tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="ad61d-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-198">visibility</span><span class="sxs-lookup"><span data-stu-id="ad61d-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="ad61d-199">Clé étrangère avec recherche dans la table tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="ad61d-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad61d-200">parentID</span><span class="sxs-lookup"><span data-stu-id="ad61d-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-201">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="ad61d-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad61d-202">siopID</span><span class="sxs-lookup"><span data-stu-id="ad61d-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="ad61d-203">Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="ad61d-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

