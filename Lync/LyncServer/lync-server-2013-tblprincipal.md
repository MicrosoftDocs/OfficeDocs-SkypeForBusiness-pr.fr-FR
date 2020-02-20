---
title: 'Lync Server 2013 : tblPrincipal'
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
ms.openlocfilehash: 4894cc1e27ce2692f0afee57fafd0025cbafebc8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="f5a2c-102">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5a2c-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5a2c-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f5a2c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f5a2c-104">tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="f5a2c-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f5a2c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5a2c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f5a2c-106">Column</span></span></th>
<th><span data-ttu-id="f5a2c-107">Type</span><span class="sxs-lookup"><span data-stu-id="f5a2c-107">Type</span></span></th>
<th><span data-ttu-id="f5a2c-108">Description</span><span class="sxs-lookup"><span data-stu-id="f5a2c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f5a2c-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-111">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f5a2c-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-113">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-114">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-114">Principal GUID.</span></span> <span data-ttu-id="f5a2c-115">Elle est largement utilisée comme clé primaire de remplacement car sa signification passe à l’espace des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="f5a2c-116">(Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="f5a2c-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-118">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p102">ID de principal. Le modèle SIP est utilisé pour les utilisateurs et ma-grp est utilisé pour presque tout le reste.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-121">prinName</span><span class="sxs-lookup"><span data-stu-id="f5a2c-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p103">Nom commun. Utilisé uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="f5a2c-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-126">Nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p104">Nom complet. Utilisé uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="f5a2c-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p105">Nom de société. Utilisé uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="f5a2c-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p106">Adresse de messagerie. Utilisée uniquement par les types d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f5a2c-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-138">nvarchar(384)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p107">Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Peut être Null pour les types qui ne sont pas des objets Active Directory (tels que les utilisateurs système).</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f5a2c-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-p108">Nom d’utilisateur principal (UPN) de l’utilisateur. Utilisé uniquement par les types d’utilisateurs réguliers.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="f5a2c-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-146">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f5a2c-147">0 : le principal est actif.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="f5a2c-148">1 : le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="f5a2c-149">2 : le principal est supprimé car l’objet AD associé a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="f5a2c-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-151">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-152">Type de principal (tiré de la table tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="f5a2c-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="f5a2c-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-154">Int</span><span class="sxs-lookup"><span data-stu-id="f5a2c-154">Int</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-155">Assignation de pool Lync pour le principal.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="f5a2c-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-157">Int</span><span class="sxs-lookup"><span data-stu-id="f5a2c-157">Int</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-158">Valeur de stratégie de serveur de conversation permanente pour l’utilisateur, si la stratégie de type de balise est présente.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="f5a2c-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-160">int</span><span class="sxs-lookup"><span data-stu-id="f5a2c-160">int</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-161">ID de principal du créateur.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="f5a2c-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-163">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-164">Horodatage de la création.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f5a2c-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-166">int</span><span class="sxs-lookup"><span data-stu-id="f5a2c-166">int</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-167">ID du principal ayant effectué la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="f5a2c-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-169">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-170">Horodatage de la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="f5a2c-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-172">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="f5a2c-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-173">Date et heure de la dernière actualisation de synchronisation Active Directory pour le principal.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f5a2c-174">Keys</span><span class="sxs-lookup"><span data-stu-id="f5a2c-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5a2c-175">Colonne</span><span class="sxs-lookup"><span data-stu-id="f5a2c-175">Column</span></span></th>
<th><span data-ttu-id="f5a2c-176">Description</span><span class="sxs-lookup"><span data-stu-id="f5a2c-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5a2c-177">prinID</span><span class="sxs-lookup"><span data-stu-id="f5a2c-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-178">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a2c-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="f5a2c-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="f5a2c-180">Clé étrangère avec recherche dans la table tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

