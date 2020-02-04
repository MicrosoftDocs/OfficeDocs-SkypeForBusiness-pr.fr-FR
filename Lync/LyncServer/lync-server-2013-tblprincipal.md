---
title: 'Lync Server 2013 : tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="0baa2-102">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0baa2-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0baa2-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0baa2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0baa2-104">tblPrincipal contient l’ensemble des principaux, y compris des utilisateurs, des dossiers et des groupes.</span><span class="sxs-lookup"><span data-stu-id="0baa2-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="0baa2-105">Celles</span><span class="sxs-lookup"><span data-stu-id="0baa2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0baa2-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="0baa2-106">Column</span></span></th>
<th><span data-ttu-id="0baa2-107">Type</span><span class="sxs-lookup"><span data-stu-id="0baa2-107">Type</span></span></th>
<th><span data-ttu-id="0baa2-108">Description</span><span class="sxs-lookup"><span data-stu-id="0baa2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0baa2-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="0baa2-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="0baa2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="0baa2-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0baa2-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="0baa2-113">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-114">GUID principal.</span><span class="sxs-lookup"><span data-stu-id="0baa2-114">Principal GUID.</span></span> <span data-ttu-id="0baa2-115">Cette opération est globalement utilisée comme clé primaire alternative, car sa signification croise l’espace des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0baa2-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="0baa2-116">(Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)</span><span class="sxs-lookup"><span data-stu-id="0baa2-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="0baa2-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="0baa2-118">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-119">URI principal.</span><span class="sxs-lookup"><span data-stu-id="0baa2-119">Principal URI.</span></span> <span data-ttu-id="0baa2-120">Le schéma SIP est utilisé pour les utilisateurs et ma-GRP est utilisé pour presque tout le reste.</span><span class="sxs-lookup"><span data-stu-id="0baa2-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-121">prinName</span><span class="sxs-lookup"><span data-stu-id="0baa2-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="0baa2-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0baa2-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0baa2-123">Nom usuel.</span><span class="sxs-lookup"><span data-stu-id="0baa2-123">Common name.</span></span> <span data-ttu-id="0baa2-124">Utilisées uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0baa2-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="0baa2-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="0baa2-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0baa2-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0baa2-127">Nom d’affichage.</span><span class="sxs-lookup"><span data-stu-id="0baa2-127">Display name.</span></span> <span data-ttu-id="0baa2-128">Utilisées uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0baa2-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="0baa2-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="0baa2-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0baa2-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0baa2-131">Nom de la société.</span><span class="sxs-lookup"><span data-stu-id="0baa2-131">Company name.</span></span> <span data-ttu-id="0baa2-132">Utilisées uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0baa2-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="0baa2-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="0baa2-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0baa2-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0baa2-135">Messagerie.</span><span class="sxs-lookup"><span data-stu-id="0baa2-135">Email.</span></span> <span data-ttu-id="0baa2-136">Utilisées uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0baa2-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="0baa2-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="0baa2-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="0baa2-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="0baa2-139">Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache.</span><span class="sxs-lookup"><span data-stu-id="0baa2-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="0baa2-140">Il peut s’agir de valeurs NULL pour les types qui ne sont pas des objets Active Directory (par exemple, utilisateurs système).</span><span class="sxs-lookup"><span data-stu-id="0baa2-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="0baa2-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="0baa2-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0baa2-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0baa2-143">Nom d’utilisateur principal (UPN) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0baa2-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="0baa2-144">Utilisé uniquement par les types d’utilisateurs normaux.</span><span class="sxs-lookup"><span data-stu-id="0baa2-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="0baa2-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="0baa2-146">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0baa2-147">0 : le principal est actif.</span><span class="sxs-lookup"><span data-stu-id="0baa2-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="0baa2-148">1 : le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="0baa2-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="0baa2-149">2 : le principal est supprimé, car l’objet publicitaire associé a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="0baa2-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="0baa2-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="0baa2-151">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-152">Type principal (issu de la table tblPrincipalType)</span><span class="sxs-lookup"><span data-stu-id="0baa2-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="0baa2-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="0baa2-154">Ent</span><span class="sxs-lookup"><span data-stu-id="0baa2-154">Int</span></span></p></td>
<td><p><span data-ttu-id="0baa2-155">Attribution du pool Lync au principal.</span><span class="sxs-lookup"><span data-stu-id="0baa2-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="0baa2-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="0baa2-157">Ent</span><span class="sxs-lookup"><span data-stu-id="0baa2-157">Int</span></span></p></td>
<td><p><span data-ttu-id="0baa2-158">Valeur de la stratégie de serveur de chat permanent pour l’utilisateur, si la stratégie de type balise est présente.</span><span class="sxs-lookup"><span data-stu-id="0baa2-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="0baa2-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="0baa2-160">int</span><span class="sxs-lookup"><span data-stu-id="0baa2-160">int</span></span></p></td>
<td><p><span data-ttu-id="0baa2-161">ID principal du créateur.</span><span class="sxs-lookup"><span data-stu-id="0baa2-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="0baa2-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="0baa2-163">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-164">Horodatage de l’heure de création.</span><span class="sxs-lookup"><span data-stu-id="0baa2-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="0baa2-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="0baa2-166">int</span><span class="sxs-lookup"><span data-stu-id="0baa2-166">int</span></span></p></td>
<td><p><span data-ttu-id="0baa2-167">ID de l’entité de confiance qui a mis à jour pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="0baa2-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="0baa2-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="0baa2-169">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-170">Horodatage de la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="0baa2-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="0baa2-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="0baa2-172">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="0baa2-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="0baa2-173">Date et heure de la dernière actualisation de la synchronisation Active Directory de l’utilisateur principal.</span><span class="sxs-lookup"><span data-stu-id="0baa2-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0baa2-174">Permettent</span><span class="sxs-lookup"><span data-stu-id="0baa2-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0baa2-175">Colonne</span><span class="sxs-lookup"><span data-stu-id="0baa2-175">Column</span></span></th>
<th><span data-ttu-id="0baa2-176">Description</span><span class="sxs-lookup"><span data-stu-id="0baa2-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0baa2-177">prinID</span><span class="sxs-lookup"><span data-stu-id="0baa2-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="0baa2-178">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0baa2-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baa2-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="0baa2-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="0baa2-180">Clé étrangère avec recherche dans la table tblPrincipalType. ptypeID.</span><span class="sxs-lookup"><span data-stu-id="0baa2-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

