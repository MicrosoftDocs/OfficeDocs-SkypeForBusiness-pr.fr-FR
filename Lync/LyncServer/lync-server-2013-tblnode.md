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
ms.openlocfilehash: 1e6070f6a575466d9ce7063c588e5d470e047d52
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523811"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="bb09e-102">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb09e-102">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb09e-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bb09e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bb09e-104">tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou de salle de conversation) telle qu’elle est gérée dans le panneau de configuration et les cmdlets administratives Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb09e-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="bb09e-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="bb09e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb09e-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="bb09e-106">Column</span></span></th>
<th><span data-ttu-id="bb09e-107">Type</span><span class="sxs-lookup"><span data-stu-id="bb09e-107">Type</span></span></th>
<th><span data-ttu-id="bb09e-108">Description</span><span class="sxs-lookup"><span data-stu-id="bb09e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="bb09e-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-111">ID de nœud (numéro unique).</span><span class="sxs-lookup"><span data-stu-id="bb09e-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="bb09e-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="bb09e-113">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-114">GUID de nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-115">parentID</span><span class="sxs-lookup"><span data-stu-id="bb09e-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-116">int</span><span class="sxs-lookup"><span data-stu-id="bb09e-116">int</span></span></p></td>
<td><p><span data-ttu-id="bb09e-p101">ID de nœud du parent. Le nœud racine (avec l’ID 1) s’inclut lui-même comme parent.</span><span class="sxs-lookup"><span data-stu-id="bb09e-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="bb09e-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="bb09e-120">bit, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-121">True si le nœud est une catégorie.</span><span class="sxs-lookup"><span data-stu-id="bb09e-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="bb09e-122">False si le nœud est une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="bb09e-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="bb09e-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="bb09e-124">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-125">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="bb09e-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="bb09e-127">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-128">Description du nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-129">invite</span><span class="sxs-lookup"><span data-stu-id="bb09e-129">invite</span></span></p></td>
<td><p><span data-ttu-id="bb09e-130">légèrement</span><span class="sxs-lookup"><span data-stu-id="bb09e-130">bit</span></span></p></td>
<td><p><span data-ttu-id="bb09e-131">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="bb09e-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-132">True si les invitations sont activées.</span><span class="sxs-lookup"><span data-stu-id="bb09e-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="bb09e-133">False si les invitations sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="bb09e-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="bb09e-134">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="bb09e-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-135">False si les invitations sont désactivées (remplace la catégorie parente).</span><span class="sxs-lookup"><span data-stu-id="bb09e-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="bb09e-136">Null si le paramètre d’invitation est hérité de la catégorie parente.</span><span class="sxs-lookup"><span data-stu-id="bb09e-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-137">connecté</span><span class="sxs-lookup"><span data-stu-id="bb09e-137">logged</span></span></p></td>
<td><p><span data-ttu-id="bb09e-138">légèrement</span><span class="sxs-lookup"><span data-stu-id="bb09e-138">bit</span></span></p></td>
<td><p><span data-ttu-id="bb09e-139">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="bb09e-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-140">True si l’historique des conversations est activé.</span><span class="sxs-lookup"><span data-stu-id="bb09e-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="bb09e-141">False si l’historique des conversations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="bb09e-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="bb09e-142">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="bb09e-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-143">Valeurs.</span><span class="sxs-lookup"><span data-stu-id="bb09e-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-144">filePost</span><span class="sxs-lookup"><span data-stu-id="bb09e-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="bb09e-145">légèrement</span><span class="sxs-lookup"><span data-stu-id="bb09e-145">bit</span></span></p></td>
<td><p><span data-ttu-id="bb09e-146">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="bb09e-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-147">True si les téléchargements de fichiers sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="bb09e-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="bb09e-148">False si les téléchargements de fichiers sont interdits.</span><span class="sxs-lookup"><span data-stu-id="bb09e-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="bb09e-149">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="bb09e-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-150">Valeurs.</span><span class="sxs-lookup"><span data-stu-id="bb09e-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-151">désactivé</span><span class="sxs-lookup"><span data-stu-id="bb09e-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="bb09e-152">bit, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-p102">True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories.)</span><span class="sxs-lookup"><span data-stu-id="bb09e-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-156">connaissance</span><span class="sxs-lookup"><span data-stu-id="bb09e-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="bb09e-157">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-158">Comportement (tiré de la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="bb09e-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-159">4 : normal (salles de conversation normales).</span><span class="sxs-lookup"><span data-stu-id="bb09e-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="bb09e-160">5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer).</span><span class="sxs-lookup"><span data-stu-id="bb09e-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="bb09e-161">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="bb09e-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-162">visibility</span><span class="sxs-lookup"><span data-stu-id="bb09e-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="bb09e-163">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-164">Visibilité (tirée de la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="bb09e-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="bb09e-165">2 : privée</span><span class="sxs-lookup"><span data-stu-id="bb09e-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="bb09e-166">3 : limitée par une étendue</span><span class="sxs-lookup"><span data-stu-id="bb09e-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="bb09e-167">6 : ouvert</span><span class="sxs-lookup"><span data-stu-id="bb09e-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="bb09e-168">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="bb09e-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-169">siopID</span><span class="sxs-lookup"><span data-stu-id="bb09e-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-170">GUID</span><span class="sxs-lookup"><span data-stu-id="bb09e-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-p103">GUID de complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de complément.)</span><span class="sxs-lookup"><span data-stu-id="bb09e-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="bb09e-173">Les informations relatives aux compléments sont recherchées dans la table SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="bb09e-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="bb09e-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="bb09e-175">int, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-176">ID du principal ayant créé ce nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="bb09e-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="bb09e-178">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-179">Horodatage de la création de nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bb09e-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="bb09e-181">int, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-182">ID du principal ayant effectué la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="bb09e-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="bb09e-184">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="bb09e-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bb09e-185">Horodatage de la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="bb09e-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="bb09e-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="bb09e-187">DateHeure</span><span class="sxs-lookup"><span data-stu-id="bb09e-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb09e-p104">Heure de la dernière opération de vidage (suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) ayant affecté ce nœud. Utilisé uniquement par le mécanisme de mise à jour du cache interne du service de conversation.</span><span class="sxs-lookup"><span data-stu-id="bb09e-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bb09e-190">Keys</span><span class="sxs-lookup"><span data-stu-id="bb09e-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb09e-191">Colonne</span><span class="sxs-lookup"><span data-stu-id="bb09e-191">Column</span></span></th>
<th><span data-ttu-id="bb09e-192">Description</span><span class="sxs-lookup"><span data-stu-id="bb09e-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="bb09e-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-194">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="bb09e-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-195">connaissance</span><span class="sxs-lookup"><span data-stu-id="bb09e-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="bb09e-196">Clé étrangère avec recherche dans la table tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="bb09e-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-197">visibility</span><span class="sxs-lookup"><span data-stu-id="bb09e-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="bb09e-198">Clé étrangère avec recherche dans la table tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="bb09e-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb09e-199">parentID</span><span class="sxs-lookup"><span data-stu-id="bb09e-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-200">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="bb09e-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb09e-201">siopID</span><span class="sxs-lookup"><span data-stu-id="bb09e-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="bb09e-202">Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="bb09e-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

