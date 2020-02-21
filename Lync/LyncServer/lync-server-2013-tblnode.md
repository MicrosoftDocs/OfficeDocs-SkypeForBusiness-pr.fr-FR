---
title: 'Lync Server 2013 : tblNode'
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
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="79a0c-102">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79a0c-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79a0c-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="79a0c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="79a0c-104">tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou de salle de conversation) telle qu’elle est gérée dans le panneau de configuration et les cmdlets administratives Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79a0c-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="79a0c-105">Columns</span><span class="sxs-lookup"><span data-stu-id="79a0c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79a0c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="79a0c-106">Column</span></span></th>
<th><span data-ttu-id="79a0c-107">Type</span><span class="sxs-lookup"><span data-stu-id="79a0c-107">Type</span></span></th>
<th><span data-ttu-id="79a0c-108">Description</span><span class="sxs-lookup"><span data-stu-id="79a0c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="79a0c-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-111">ID de nœud (numéro unique).</span><span class="sxs-lookup"><span data-stu-id="79a0c-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="79a0c-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="79a0c-113">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-114">GUID de nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-115">parentID</span><span class="sxs-lookup"><span data-stu-id="79a0c-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-116">int</span><span class="sxs-lookup"><span data-stu-id="79a0c-116">int</span></span></p></td>
<td><p><span data-ttu-id="79a0c-p101">ID de nœud du parent. Le nœud racine (avec l’ID 1) s’inclut lui-même comme parent.</span><span class="sxs-lookup"><span data-stu-id="79a0c-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="79a0c-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="79a0c-120">bit, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-121">True si le nœud est une catégorie.</span><span class="sxs-lookup"><span data-stu-id="79a0c-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="79a0c-122">False si le nœud est une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="79a0c-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="79a0c-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="79a0c-124">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-125">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="79a0c-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="79a0c-127">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-128">Description du nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-129">invite</span><span class="sxs-lookup"><span data-stu-id="79a0c-129">invite</span></span></p></td>
<td><p><span data-ttu-id="79a0c-130">légèrement</span><span class="sxs-lookup"><span data-stu-id="79a0c-130">bit</span></span></p></td>
<td><p><span data-ttu-id="79a0c-131">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="79a0c-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-132">True si les invitations sont activées.</span><span class="sxs-lookup"><span data-stu-id="79a0c-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="79a0c-133">False si les invitations sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="79a0c-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="79a0c-134">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="79a0c-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-135">False si les invitations sont désactivées (remplace la catégorie parente).</span><span class="sxs-lookup"><span data-stu-id="79a0c-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="79a0c-136">Null si le paramètre d’invitation est hérité de la catégorie parente.</span><span class="sxs-lookup"><span data-stu-id="79a0c-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-137">connecté</span><span class="sxs-lookup"><span data-stu-id="79a0c-137">logged</span></span></p></td>
<td><p><span data-ttu-id="79a0c-138">légèrement</span><span class="sxs-lookup"><span data-stu-id="79a0c-138">bit</span></span></p></td>
<td><p><span data-ttu-id="79a0c-139">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="79a0c-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-140">True si l’historique des conversations est activé.</span><span class="sxs-lookup"><span data-stu-id="79a0c-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="79a0c-141">False si l’historique des conversations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="79a0c-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="79a0c-142">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="79a0c-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-143">Valeurs.</span><span class="sxs-lookup"><span data-stu-id="79a0c-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-144">filePost</span><span class="sxs-lookup"><span data-stu-id="79a0c-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="79a0c-145">légèrement</span><span class="sxs-lookup"><span data-stu-id="79a0c-145">bit</span></span></p></td>
<td><p><span data-ttu-id="79a0c-146">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="79a0c-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-147">True si les téléchargements de fichiers sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="79a0c-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="79a0c-148">False si les téléchargements de fichiers sont interdits.</span><span class="sxs-lookup"><span data-stu-id="79a0c-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="79a0c-149">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="79a0c-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-150">Valeurs.</span><span class="sxs-lookup"><span data-stu-id="79a0c-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-151">activation</span><span class="sxs-lookup"><span data-stu-id="79a0c-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="79a0c-152">bit, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-p102">True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories.)</span><span class="sxs-lookup"><span data-stu-id="79a0c-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-156">connaissance</span><span class="sxs-lookup"><span data-stu-id="79a0c-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="79a0c-157">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-158">Comportement (tiré de la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="79a0c-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-159">4 : normal (salles de conversation normales).</span><span class="sxs-lookup"><span data-stu-id="79a0c-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="79a0c-160">5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer).</span><span class="sxs-lookup"><span data-stu-id="79a0c-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="79a0c-161">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="79a0c-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-162">visibility</span><span class="sxs-lookup"><span data-stu-id="79a0c-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="79a0c-163">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-164">Visibilité (tirée de la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="79a0c-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="79a0c-165">2 : privée</span><span class="sxs-lookup"><span data-stu-id="79a0c-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="79a0c-166">3 : limitée par une étendue</span><span class="sxs-lookup"><span data-stu-id="79a0c-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="79a0c-167">6 : ouvert</span><span class="sxs-lookup"><span data-stu-id="79a0c-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="79a0c-168">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="79a0c-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-169">siopID</span><span class="sxs-lookup"><span data-stu-id="79a0c-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-170">GUID</span><span class="sxs-lookup"><span data-stu-id="79a0c-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-p103">GUID de complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de complément.)</span><span class="sxs-lookup"><span data-stu-id="79a0c-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="79a0c-173">Les informations relatives aux compléments sont recherchées dans la table SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="79a0c-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="79a0c-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="79a0c-175">int, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-176">ID du principal ayant créé ce nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="79a0c-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="79a0c-178">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-179">Horodatage de la création de nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="79a0c-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="79a0c-181">int, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-182">ID du principal ayant effectué la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="79a0c-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="79a0c-184">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="79a0c-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="79a0c-185">Horodatage de la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="79a0c-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="79a0c-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="79a0c-187">DateHeure</span><span class="sxs-lookup"><span data-stu-id="79a0c-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="79a0c-p104">Heure de la dernière opération de vidage (suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) ayant affecté ce nœud. Utilisé uniquement par le mécanisme de mise à jour du cache interne du service de conversation.</span><span class="sxs-lookup"><span data-stu-id="79a0c-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="79a0c-190">Keys</span><span class="sxs-lookup"><span data-stu-id="79a0c-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79a0c-191">Colonne</span><span class="sxs-lookup"><span data-stu-id="79a0c-191">Column</span></span></th>
<th><span data-ttu-id="79a0c-192">Description</span><span class="sxs-lookup"><span data-stu-id="79a0c-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="79a0c-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-194">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="79a0c-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-195">connaissance</span><span class="sxs-lookup"><span data-stu-id="79a0c-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="79a0c-196">Clé étrangère avec recherche dans la table tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="79a0c-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-197">visibility</span><span class="sxs-lookup"><span data-stu-id="79a0c-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="79a0c-198">Clé étrangère avec recherche dans la table tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="79a0c-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79a0c-199">parentID</span><span class="sxs-lookup"><span data-stu-id="79a0c-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-200">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="79a0c-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79a0c-201">siopID</span><span class="sxs-lookup"><span data-stu-id="79a0c-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="79a0c-202">Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="79a0c-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

