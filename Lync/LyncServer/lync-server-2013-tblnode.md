---
title: 'Lync Server 2013 : tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="67ce4-102">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ce4-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67ce4-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="67ce4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="67ce4-104">tblNode contient l’arborescence d’objets (avec des nœuds de catégorie ou de salle de conversation) qui est gérée dans le panneau de configuration et les applets de commande d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67ce4-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="67ce4-105">Celles</span><span class="sxs-lookup"><span data-stu-id="67ce4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67ce4-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="67ce4-106">Column</span></span></th>
<th><span data-ttu-id="67ce4-107">Type</span><span class="sxs-lookup"><span data-stu-id="67ce4-107">Type</span></span></th>
<th><span data-ttu-id="67ce4-108">Description</span><span class="sxs-lookup"><span data-stu-id="67ce4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-109">ID</span><span class="sxs-lookup"><span data-stu-id="67ce4-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="67ce4-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-111">ID de nœud (numéro unique).</span><span class="sxs-lookup"><span data-stu-id="67ce4-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="67ce4-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="67ce4-113">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-114">GUID du nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-115">Parent</span><span class="sxs-lookup"><span data-stu-id="67ce4-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-116">int</span><span class="sxs-lookup"><span data-stu-id="67ce4-116">int</span></span></p></td>
<td><p><span data-ttu-id="67ce4-117">ID de nœud du parent.</span><span class="sxs-lookup"><span data-stu-id="67ce4-117">Node ID of parent.</span></span> <span data-ttu-id="67ce4-118">Le nœud racine (avec l’ID 1) s’intègre également en tant que parent.</span><span class="sxs-lookup"><span data-stu-id="67ce4-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="67ce4-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="67ce4-120">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-121">True si le nœud est une catégorie.</span><span class="sxs-lookup"><span data-stu-id="67ce4-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="67ce4-122">Faux si le nœud est une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="67ce4-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="67ce4-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="67ce4-124">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-125">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="67ce4-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="67ce4-127">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-128">Description du nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-129">inviter</span><span class="sxs-lookup"><span data-stu-id="67ce4-129">invite</span></span></p></td>
<td><p><span data-ttu-id="67ce4-130">bit</span><span class="sxs-lookup"><span data-stu-id="67ce4-130">bit</span></span></p></td>
<td><p><span data-ttu-id="67ce4-131">Pour les catégories:</span><span class="sxs-lookup"><span data-stu-id="67ce4-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-132">True si les invitations sont activées.</span><span class="sxs-lookup"><span data-stu-id="67ce4-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="67ce4-133">Faux si les invitations sont désdésactivées.</span><span class="sxs-lookup"><span data-stu-id="67ce4-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="67ce4-134">Pour les salles:</span><span class="sxs-lookup"><span data-stu-id="67ce4-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-135">Faux si les invitations sont désactivées (ignore la catégorie parent).</span><span class="sxs-lookup"><span data-stu-id="67ce4-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="67ce4-136">NULL si le paramètre d’invitations est hérité de la catégorie parent.</span><span class="sxs-lookup"><span data-stu-id="67ce4-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-137">utilisé</span><span class="sxs-lookup"><span data-stu-id="67ce4-137">logged</span></span></p></td>
<td><p><span data-ttu-id="67ce4-138">bit</span><span class="sxs-lookup"><span data-stu-id="67ce4-138">bit</span></span></p></td>
<td><p><span data-ttu-id="67ce4-139">Pour les catégories:</span><span class="sxs-lookup"><span data-stu-id="67ce4-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-140">True si l’historique des conversations est activé.</span><span class="sxs-lookup"><span data-stu-id="67ce4-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="67ce4-141">Faux si l’historique des conversations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="67ce4-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="67ce4-142">Pour les salles:</span><span class="sxs-lookup"><span data-stu-id="67ce4-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-143">Valeur.</span><span class="sxs-lookup"><span data-stu-id="67ce4-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-144">filePost</span><span class="sxs-lookup"><span data-stu-id="67ce4-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="67ce4-145">bit</span><span class="sxs-lookup"><span data-stu-id="67ce4-145">bit</span></span></p></td>
<td><p><span data-ttu-id="67ce4-146">Pour les catégories:</span><span class="sxs-lookup"><span data-stu-id="67ce4-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-147">True si les téléchargements de fichiers sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="67ce4-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="67ce4-148">False si les téléchargements de fichiers ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="67ce4-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="67ce4-149">Pour les salles:</span><span class="sxs-lookup"><span data-stu-id="67ce4-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-150">Valeur.</span><span class="sxs-lookup"><span data-stu-id="67ce4-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-151">désactivé</span><span class="sxs-lookup"><span data-stu-id="67ce4-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="67ce4-152">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-153">True si la salle de conversation est désactivée.</span><span class="sxs-lookup"><span data-stu-id="67ce4-153">True if the chat room is disabled.</span></span> <span data-ttu-id="67ce4-154">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="67ce4-154">Applies only to chat rooms.</span></span> <span data-ttu-id="67ce4-155">(Faux pour les catégories.)</span><span class="sxs-lookup"><span data-stu-id="67ce4-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-156">fonctionnement</span><span class="sxs-lookup"><span data-stu-id="67ce4-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="67ce4-157">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-158">Comportement (recherché dans la table EnumValue):</span><span class="sxs-lookup"><span data-stu-id="67ce4-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-159">4: normal (salles de conversation normales).</span><span class="sxs-lookup"><span data-stu-id="67ce4-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="67ce4-160">5: Auditorium (salles de conversation d’Auditorium; seuls les présentateurs peuvent collaborer).</span><span class="sxs-lookup"><span data-stu-id="67ce4-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="67ce4-161">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="67ce4-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-162">notoriété</span><span class="sxs-lookup"><span data-stu-id="67ce4-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="67ce4-163">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-164">Visibility (recherché sur la table EnumValue):</span><span class="sxs-lookup"><span data-stu-id="67ce4-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="67ce4-165">2: privé</span><span class="sxs-lookup"><span data-stu-id="67ce4-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="67ce4-166">3: étendue</span><span class="sxs-lookup"><span data-stu-id="67ce4-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="67ce4-167">6: ouvrir</span><span class="sxs-lookup"><span data-stu-id="67ce4-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="67ce4-168">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="67ce4-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-169">siopID</span><span class="sxs-lookup"><span data-stu-id="67ce4-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-170">GUID</span><span class="sxs-lookup"><span data-stu-id="67ce4-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-171">GUID du complément si un complément est associé à cette salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="67ce4-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="67ce4-172">(Les catégories n’ont pas de compléments.)</span><span class="sxs-lookup"><span data-stu-id="67ce4-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="67ce4-173">Les informations de complément sont recherchées dans la table SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="67ce4-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="67ce4-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="67ce4-175">ent, non null</span><span class="sxs-lookup"><span data-stu-id="67ce4-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-176">ID de l’élément principal qui a créé ce nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="67ce4-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="67ce4-178">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-179">Horodatage de la création du nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="67ce4-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="67ce4-181">ent, non null</span><span class="sxs-lookup"><span data-stu-id="67ce4-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-182">ID de l’entité de l’utilisateur qui a effectué la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="67ce4-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="67ce4-184">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="67ce4-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="67ce4-185">Horodatage de la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="67ce4-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="67ce4-187">DateHeure</span><span class="sxs-lookup"><span data-stu-id="67ce4-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="67ce4-188">Heure de la dernière opération de purge (la suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) qui ont affecté ce nœud.</span><span class="sxs-lookup"><span data-stu-id="67ce4-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="67ce4-189">Ce mode est utilisé par le mécanisme de mise à jour du cache interne du service de conversation.</span><span class="sxs-lookup"><span data-stu-id="67ce4-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="67ce4-190">Permettent</span><span class="sxs-lookup"><span data-stu-id="67ce4-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67ce4-191">Colonne</span><span class="sxs-lookup"><span data-stu-id="67ce4-191">Column</span></span></th>
<th><span data-ttu-id="67ce4-192">Description</span><span class="sxs-lookup"><span data-stu-id="67ce4-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-193">ID</span><span class="sxs-lookup"><span data-stu-id="67ce4-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-194">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="67ce4-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-195">fonctionnement</span><span class="sxs-lookup"><span data-stu-id="67ce4-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="67ce4-196">Clé étrangère avec recherche dans la table tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="67ce4-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-197">notoriété</span><span class="sxs-lookup"><span data-stu-id="67ce4-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="67ce4-198">Clé étrangère avec recherche dans la table tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="67ce4-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ce4-199">Parent</span><span class="sxs-lookup"><span data-stu-id="67ce4-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-200">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="67ce4-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ce4-201">siopID</span><span class="sxs-lookup"><span data-stu-id="67ce4-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="67ce4-202">Clé étrangère avec recherche dans la table tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="67ce4-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

