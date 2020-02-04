---
title: 'Lync Server 2013 : tblNode'
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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="45d6b-102">tblNode dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45d6b-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45d6b-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="45d6b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="45d6b-104">tblNode contient l’arborescence d’objets (avec des nœuds de catégorie ou de salle de conversation) qui est gérée dans le panneau de configuration et les applets de commande d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45d6b-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="45d6b-105">Celles</span><span class="sxs-lookup"><span data-stu-id="45d6b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45d6b-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="45d6b-106">Column</span></span></th>
<th><span data-ttu-id="45d6b-107">Type</span><span class="sxs-lookup"><span data-stu-id="45d6b-107">Type</span></span></th>
<th><span data-ttu-id="45d6b-108">Description</span><span class="sxs-lookup"><span data-stu-id="45d6b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-109">ID</span><span class="sxs-lookup"><span data-stu-id="45d6b-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="45d6b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-111">ID de nœud (numéro unique).</span><span class="sxs-lookup"><span data-stu-id="45d6b-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="45d6b-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="45d6b-113">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-114">GUID du nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-115">Parent</span><span class="sxs-lookup"><span data-stu-id="45d6b-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-116">int</span><span class="sxs-lookup"><span data-stu-id="45d6b-116">int</span></span></p></td>
<td><p><span data-ttu-id="45d6b-117">ID de nœud du parent.</span><span class="sxs-lookup"><span data-stu-id="45d6b-117">Node ID of parent.</span></span> <span data-ttu-id="45d6b-118">Le nœud racine (avec l’ID 1) s’intègre également en tant que parent.</span><span class="sxs-lookup"><span data-stu-id="45d6b-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="45d6b-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="45d6b-120">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-121">True si le nœud est une catégorie.</span><span class="sxs-lookup"><span data-stu-id="45d6b-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="45d6b-122">Faux si le nœud est une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="45d6b-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="45d6b-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="45d6b-124">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-125">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="45d6b-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="45d6b-127">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-128">Description du nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-129">inviter</span><span class="sxs-lookup"><span data-stu-id="45d6b-129">invite</span></span></p></td>
<td><p><span data-ttu-id="45d6b-130">bit</span><span class="sxs-lookup"><span data-stu-id="45d6b-130">bit</span></span></p></td>
<td><p><span data-ttu-id="45d6b-131">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="45d6b-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-132">True si les invitations sont activées.</span><span class="sxs-lookup"><span data-stu-id="45d6b-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="45d6b-133">Faux si les invitations sont désdésactivées.</span><span class="sxs-lookup"><span data-stu-id="45d6b-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="45d6b-134">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="45d6b-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-135">Faux si les invitations sont désactivées (ignore la catégorie parent).</span><span class="sxs-lookup"><span data-stu-id="45d6b-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="45d6b-136">NULL si le paramètre d’invitations est hérité de la catégorie parent.</span><span class="sxs-lookup"><span data-stu-id="45d6b-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-137">utilisé</span><span class="sxs-lookup"><span data-stu-id="45d6b-137">logged</span></span></p></td>
<td><p><span data-ttu-id="45d6b-138">bit</span><span class="sxs-lookup"><span data-stu-id="45d6b-138">bit</span></span></p></td>
<td><p><span data-ttu-id="45d6b-139">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="45d6b-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-140">True si l’historique des conversations est activé.</span><span class="sxs-lookup"><span data-stu-id="45d6b-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="45d6b-141">Faux si l’historique des conversations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="45d6b-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="45d6b-142">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="45d6b-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-143">Valeur.</span><span class="sxs-lookup"><span data-stu-id="45d6b-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-144">filePost</span><span class="sxs-lookup"><span data-stu-id="45d6b-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="45d6b-145">bit</span><span class="sxs-lookup"><span data-stu-id="45d6b-145">bit</span></span></p></td>
<td><p><span data-ttu-id="45d6b-146">Pour les catégories :</span><span class="sxs-lookup"><span data-stu-id="45d6b-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-147">True si les téléchargements de fichiers sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="45d6b-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="45d6b-148">False si les téléchargements de fichiers ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="45d6b-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="45d6b-149">Pour les salles :</span><span class="sxs-lookup"><span data-stu-id="45d6b-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-150">Valeur.</span><span class="sxs-lookup"><span data-stu-id="45d6b-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-151">désactivé</span><span class="sxs-lookup"><span data-stu-id="45d6b-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="45d6b-152">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-153">True si la salle de conversation est désactivée.</span><span class="sxs-lookup"><span data-stu-id="45d6b-153">True if the chat room is disabled.</span></span> <span data-ttu-id="45d6b-154">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="45d6b-154">Applies only to chat rooms.</span></span> <span data-ttu-id="45d6b-155">(Faux pour les catégories.)</span><span class="sxs-lookup"><span data-stu-id="45d6b-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-156">fonctionnement</span><span class="sxs-lookup"><span data-stu-id="45d6b-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="45d6b-157">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-158">Comportement (recherché dans la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="45d6b-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-159">4 : normal (salles de conversation normales).</span><span class="sxs-lookup"><span data-stu-id="45d6b-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="45d6b-160">5 : Auditorium (salles de conversation d’Auditorium ; seuls les présentateurs peuvent collaborer).</span><span class="sxs-lookup"><span data-stu-id="45d6b-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="45d6b-161">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="45d6b-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-162">notoriété</span><span class="sxs-lookup"><span data-stu-id="45d6b-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="45d6b-163">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-164">Visibility (recherché sur la table EnumValue) :</span><span class="sxs-lookup"><span data-stu-id="45d6b-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="45d6b-165">2 : privé</span><span class="sxs-lookup"><span data-stu-id="45d6b-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="45d6b-166">3 : étendue</span><span class="sxs-lookup"><span data-stu-id="45d6b-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="45d6b-167">6 : ouvrir</span><span class="sxs-lookup"><span data-stu-id="45d6b-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="45d6b-168">S’applique uniquement aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="45d6b-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-169">siopID</span><span class="sxs-lookup"><span data-stu-id="45d6b-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-170">GUID</span><span class="sxs-lookup"><span data-stu-id="45d6b-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-171">GUID du complément si un complément est associé à cette salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="45d6b-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="45d6b-172">(Les catégories n’ont pas de compléments.)</span><span class="sxs-lookup"><span data-stu-id="45d6b-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="45d6b-173">Les informations de complément sont recherchées dans la table SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="45d6b-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="45d6b-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="45d6b-175">ent, non null</span><span class="sxs-lookup"><span data-stu-id="45d6b-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-176">ID de l’élément principal qui a créé ce nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="45d6b-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="45d6b-178">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-179">Horodatage de la création du nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="45d6b-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="45d6b-181">ent, non null</span><span class="sxs-lookup"><span data-stu-id="45d6b-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-182">ID de l’entité de l’utilisateur qui a effectué la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="45d6b-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="45d6b-184">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="45d6b-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="45d6b-185">Horodatage de la dernière mise à jour de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="45d6b-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="45d6b-187">DateHeure</span><span class="sxs-lookup"><span data-stu-id="45d6b-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="45d6b-188">Heure de la dernière opération de purge (la suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) qui ont affecté ce nœud.</span><span class="sxs-lookup"><span data-stu-id="45d6b-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="45d6b-189">Ce mode est utilisé par le mécanisme de mise à jour du cache interne du service de conversation.</span><span class="sxs-lookup"><span data-stu-id="45d6b-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="45d6b-190">Permettent</span><span class="sxs-lookup"><span data-stu-id="45d6b-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45d6b-191">Colonne</span><span class="sxs-lookup"><span data-stu-id="45d6b-191">Column</span></span></th>
<th><span data-ttu-id="45d6b-192">Description</span><span class="sxs-lookup"><span data-stu-id="45d6b-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-193">ID</span><span class="sxs-lookup"><span data-stu-id="45d6b-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-194">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="45d6b-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-195">fonctionnement</span><span class="sxs-lookup"><span data-stu-id="45d6b-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="45d6b-196">Clé étrangère avec recherche dans la table tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="45d6b-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-197">notoriété</span><span class="sxs-lookup"><span data-stu-id="45d6b-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="45d6b-198">Clé étrangère avec recherche dans la table tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="45d6b-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d6b-199">Parent</span><span class="sxs-lookup"><span data-stu-id="45d6b-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-200">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="45d6b-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d6b-201">siopID</span><span class="sxs-lookup"><span data-stu-id="45d6b-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="45d6b-202">Clé étrangère avec recherche dans la table tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="45d6b-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

