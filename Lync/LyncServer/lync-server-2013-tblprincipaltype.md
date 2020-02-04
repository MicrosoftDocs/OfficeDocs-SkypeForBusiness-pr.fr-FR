---
title: 'Lync Server 2013 : tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="51aef-102">tblPrincipalType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aef-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51aef-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="51aef-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="51aef-104">tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="51aef-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="51aef-105">Celles</span><span class="sxs-lookup"><span data-stu-id="51aef-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51aef-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="51aef-106">Column</span></span></th>
<th><span data-ttu-id="51aef-107">Type</span><span class="sxs-lookup"><span data-stu-id="51aef-107">Type</span></span></th>
<th><span data-ttu-id="51aef-108">Description%</span><span class="sxs-lookup"><span data-stu-id="51aef-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51aef-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="51aef-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="51aef-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="51aef-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="51aef-111">ID de type principal.</span><span class="sxs-lookup"><span data-stu-id="51aef-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aef-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="51aef-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="51aef-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="51aef-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="51aef-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="51aef-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51aef-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="51aef-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="51aef-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="51aef-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="51aef-117">True si le type correspond aux éléments principaux utilisés à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="51aef-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aef-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="51aef-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="51aef-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="51aef-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="51aef-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="51aef-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="51aef-121">Clé</span><span class="sxs-lookup"><span data-stu-id="51aef-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51aef-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="51aef-122">Column</span></span></th>
<th><span data-ttu-id="51aef-123">Description</span><span class="sxs-lookup"><span data-stu-id="51aef-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51aef-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="51aef-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="51aef-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="51aef-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="51aef-126">Valeurs principales</span><span class="sxs-lookup"><span data-stu-id="51aef-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51aef-127">ID</span><span class="sxs-lookup"><span data-stu-id="51aef-127">ID</span></span></th>
<th><span data-ttu-id="51aef-128">Rôle</span><span class="sxs-lookup"><span data-stu-id="51aef-128">Role</span></span></th>
<th><span data-ttu-id="51aef-129">Description</span><span class="sxs-lookup"><span data-stu-id="51aef-129">Description</span></span></th>
<th><span data-ttu-id="51aef-130">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="51aef-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51aef-131">1</span><span class="sxs-lookup"><span data-stu-id="51aef-131">1</span></span></p></td>
<td><p><span data-ttu-id="51aef-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="51aef-132">Any</span></span></p></td>
<td><p><span data-ttu-id="51aef-133">Principal générique sans type connu.</span><span class="sxs-lookup"><span data-stu-id="51aef-133">Generic principal with no known type.</span></span> <span data-ttu-id="51aef-134">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="51aef-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aef-135">deuxième</span><span class="sxs-lookup"><span data-stu-id="51aef-135">2</span></span></p></td>
<td><p><span data-ttu-id="51aef-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="51aef-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="51aef-137">Principal générique de type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="51aef-137">Generic principal of user type.</span></span> <span data-ttu-id="51aef-138">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="51aef-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="51aef-139">Oui</span><span class="sxs-lookup"><span data-stu-id="51aef-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51aef-140">3</span><span class="sxs-lookup"><span data-stu-id="51aef-140">3</span></span></p></td>
<td><p><span data-ttu-id="51aef-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="51aef-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="51aef-142">Principal générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="51aef-142">Generic principal with group semantic.</span></span> <span data-ttu-id="51aef-143">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="51aef-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aef-144">4</span><span class="sxs-lookup"><span data-stu-id="51aef-144">4</span></span></p></td>
<td><p><span data-ttu-id="51aef-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="51aef-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="51aef-146">Principal utilisé par le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="51aef-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51aef-147">5</span><span class="sxs-lookup"><span data-stu-id="51aef-147">5</span></span></p></td>
<td><p><span data-ttu-id="51aef-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="51aef-148">User</span></span></p></td>
<td><p><span data-ttu-id="51aef-149">Utilisateur ordinaire.</span><span class="sxs-lookup"><span data-stu-id="51aef-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="51aef-150">Oui</span><span class="sxs-lookup"><span data-stu-id="51aef-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aef-151">version8</span><span class="sxs-lookup"><span data-stu-id="51aef-151">8</span></span></p></td>
<td><p><span data-ttu-id="51aef-152">CD</span><span class="sxs-lookup"><span data-stu-id="51aef-152">DC</span></span></p></td>
<td><p><span data-ttu-id="51aef-153">Contrôleur de domaine Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="51aef-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51aef-154">09</span><span class="sxs-lookup"><span data-stu-id="51aef-154">9</span></span></p></td>
<td><p><span data-ttu-id="51aef-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="51aef-155">Group</span></span></p></td>
<td><p><span data-ttu-id="51aef-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51aef-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51aef-157">0,10</span><span class="sxs-lookup"><span data-stu-id="51aef-157">10</span></span></p></td>
<td><p><span data-ttu-id="51aef-158">Folder</span><span class="sxs-lookup"><span data-stu-id="51aef-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="51aef-159">Conteneur Active Directory ou unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="51aef-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="51aef-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51aef-160">See Also</span></span>


[<span data-ttu-id="51aef-161">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51aef-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

