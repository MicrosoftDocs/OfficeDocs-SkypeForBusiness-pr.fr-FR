---
title: 'Lync Server 2013 : tblPrincipal'
description: 'Lync Server 2013 : tblPrincipal.'
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
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547490"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="a1eca-103">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1eca-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1eca-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a1eca-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a1eca-105">tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.</span><span class="sxs-lookup"><span data-stu-id="a1eca-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="a1eca-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="a1eca-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1eca-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="a1eca-107">Column</span></span></th>
<th><span data-ttu-id="a1eca-108">Type</span><span class="sxs-lookup"><span data-stu-id="a1eca-108">Type</span></span></th>
<th><span data-ttu-id="a1eca-109">Description</span><span class="sxs-lookup"><span data-stu-id="a1eca-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-110">prinID</span><span class="sxs-lookup"><span data-stu-id="a1eca-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="a1eca-111">int, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-112">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="a1eca-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a1eca-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="a1eca-114">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-115">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="a1eca-115">Principal GUID.</span></span> <span data-ttu-id="a1eca-116">Elle est largement utilisée comme clé primaire de remplacement car sa signification passe à l’espace des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a1eca-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="a1eca-117">(Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)</span><span class="sxs-lookup"><span data-stu-id="a1eca-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="a1eca-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="a1eca-119">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p102">ID de principal. Le modèle SIP est utilisé pour les utilisateurs et ma-grp est utilisé pour presque tout le reste.</span><span class="sxs-lookup"><span data-stu-id="a1eca-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-122">prinName</span><span class="sxs-lookup"><span data-stu-id="a1eca-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="a1eca-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a1eca-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p103">Nom commun. Utilisé uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a1eca-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="a1eca-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="a1eca-127">Nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a1eca-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p104">Nom complet. Utilisé uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a1eca-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="a1eca-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="a1eca-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a1eca-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p105">Nom de société. Utilisé uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a1eca-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="a1eca-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="a1eca-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a1eca-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p106">Adresse de messagerie. Utilisée uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a1eca-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="a1eca-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="a1eca-139">nvarchar(384)</span><span class="sxs-lookup"><span data-stu-id="a1eca-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p107">Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Peut être Null pour les types qui ne sont pas des objets Active Directory (tels que les utilisateurs système).</span><span class="sxs-lookup"><span data-stu-id="a1eca-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a1eca-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="a1eca-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a1eca-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a1eca-p108">Nom d’utilisateur principal (UPN) de l’utilisateur. Utilisé uniquement par les types d’utilisateurs réguliers.</span><span class="sxs-lookup"><span data-stu-id="a1eca-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="a1eca-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="a1eca-147">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a1eca-148">0 : le principal est actif.</span><span class="sxs-lookup"><span data-stu-id="a1eca-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="a1eca-149">1 : le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="a1eca-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="a1eca-150">2 : le principal est supprimé car l’objet AD associé a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="a1eca-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="a1eca-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="a1eca-152">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-153">Type de principal (tiré de la table tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="a1eca-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="a1eca-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="a1eca-155">Int</span><span class="sxs-lookup"><span data-stu-id="a1eca-155">Int</span></span></p></td>
<td><p><span data-ttu-id="a1eca-156">Assignation de pool Lync pour le principal.</span><span class="sxs-lookup"><span data-stu-id="a1eca-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="a1eca-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="a1eca-158">Int</span><span class="sxs-lookup"><span data-stu-id="a1eca-158">Int</span></span></p></td>
<td><p><span data-ttu-id="a1eca-159">Valeur de stratégie de serveur de conversation permanente pour l’utilisateur, si la stratégie de type de balise est présente.</span><span class="sxs-lookup"><span data-stu-id="a1eca-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="a1eca-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="a1eca-161">int</span><span class="sxs-lookup"><span data-stu-id="a1eca-161">int</span></span></p></td>
<td><p><span data-ttu-id="a1eca-162">ID de principal du créateur.</span><span class="sxs-lookup"><span data-stu-id="a1eca-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="a1eca-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="a1eca-164">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-165">Horodatage de la création.</span><span class="sxs-lookup"><span data-stu-id="a1eca-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a1eca-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="a1eca-167">int</span><span class="sxs-lookup"><span data-stu-id="a1eca-167">int</span></span></p></td>
<td><p><span data-ttu-id="a1eca-168">ID du principal ayant effectué la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a1eca-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="a1eca-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="a1eca-170">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-171">Horodatage de la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a1eca-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="a1eca-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="a1eca-173">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="a1eca-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="a1eca-174">Date et heure de la dernière actualisation de synchronisation Active Directory pour le principal.</span><span class="sxs-lookup"><span data-stu-id="a1eca-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a1eca-175">Keys</span><span class="sxs-lookup"><span data-stu-id="a1eca-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1eca-176">Colonne</span><span class="sxs-lookup"><span data-stu-id="a1eca-176">Column</span></span></th>
<th><span data-ttu-id="a1eca-177">Description</span><span class="sxs-lookup"><span data-stu-id="a1eca-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1eca-178">prinID</span><span class="sxs-lookup"><span data-stu-id="a1eca-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="a1eca-179">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a1eca-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1eca-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="a1eca-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="a1eca-181">Clé étrangère avec recherche dans la table tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="a1eca-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

