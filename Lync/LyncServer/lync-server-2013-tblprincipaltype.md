---
title: 'Lync Server 2013 : tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="4672f-102">tblPrincipalType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4672f-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4672f-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4672f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4672f-104">tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4672f-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="4672f-105">Celles</span><span class="sxs-lookup"><span data-stu-id="4672f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4672f-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="4672f-106">Column</span></span></th>
<th><span data-ttu-id="4672f-107">Type</span><span class="sxs-lookup"><span data-stu-id="4672f-107">Type</span></span></th>
<th><span data-ttu-id="4672f-108">Description%</span><span class="sxs-lookup"><span data-stu-id="4672f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4672f-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="4672f-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="4672f-110">smallint, pas null</span><span class="sxs-lookup"><span data-stu-id="4672f-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4672f-111">ID de type principal.</span><span class="sxs-lookup"><span data-stu-id="4672f-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4672f-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="4672f-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="4672f-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="4672f-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4672f-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="4672f-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4672f-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="4672f-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="4672f-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="4672f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4672f-117">True si le type correspond aux éléments principaux utilisés à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="4672f-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4672f-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="4672f-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="4672f-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="4672f-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4672f-120">True si le type est un type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4672f-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4672f-121">Clé</span><span class="sxs-lookup"><span data-stu-id="4672f-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4672f-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="4672f-122">Column</span></span></th>
<th><span data-ttu-id="4672f-123">Description</span><span class="sxs-lookup"><span data-stu-id="4672f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4672f-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="4672f-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="4672f-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="4672f-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="4672f-126">Valeurs principales</span><span class="sxs-lookup"><span data-stu-id="4672f-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4672f-127">ID</span><span class="sxs-lookup"><span data-stu-id="4672f-127">ID</span></span></th>
<th><span data-ttu-id="4672f-128">Rôle</span><span class="sxs-lookup"><span data-stu-id="4672f-128">Role</span></span></th>
<th><span data-ttu-id="4672f-129">Description</span><span class="sxs-lookup"><span data-stu-id="4672f-129">Description</span></span></th>
<th><span data-ttu-id="4672f-130">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="4672f-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4672f-131">1</span><span class="sxs-lookup"><span data-stu-id="4672f-131">1</span></span></p></td>
<td><p><span data-ttu-id="4672f-132">Indifférente</span><span class="sxs-lookup"><span data-stu-id="4672f-132">Any</span></span></p></td>
<td><p><span data-ttu-id="4672f-133">Principal générique sans type connu.</span><span class="sxs-lookup"><span data-stu-id="4672f-133">Generic principal with no known type.</span></span> <span data-ttu-id="4672f-134">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4672f-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4672f-135">2</span><span class="sxs-lookup"><span data-stu-id="4672f-135">2</span></span></p></td>
<td><p><span data-ttu-id="4672f-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="4672f-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="4672f-137">Principal générique de type d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4672f-137">Generic principal of user type.</span></span> <span data-ttu-id="4672f-138">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4672f-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="4672f-139">Oui</span><span class="sxs-lookup"><span data-stu-id="4672f-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4672f-140">3</span><span class="sxs-lookup"><span data-stu-id="4672f-140">3</span></span></p></td>
<td><p><span data-ttu-id="4672f-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="4672f-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="4672f-142">Principal générique avec la sémantique de groupe.</span><span class="sxs-lookup"><span data-stu-id="4672f-142">Generic principal with group semantic.</span></span> <span data-ttu-id="4672f-143">Non utilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="4672f-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4672f-144">4</span><span class="sxs-lookup"><span data-stu-id="4672f-144">4</span></span></p></td>
<td><p><span data-ttu-id="4672f-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="4672f-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="4672f-146">Principal utilisé par le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="4672f-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4672f-147">5</span><span class="sxs-lookup"><span data-stu-id="4672f-147">5</span></span></p></td>
<td><p><span data-ttu-id="4672f-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="4672f-148">User</span></span></p></td>
<td><p><span data-ttu-id="4672f-149">Utilisateur ordinaire.</span><span class="sxs-lookup"><span data-stu-id="4672f-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="4672f-150">Oui</span><span class="sxs-lookup"><span data-stu-id="4672f-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4672f-151">version8</span><span class="sxs-lookup"><span data-stu-id="4672f-151">8</span></span></p></td>
<td><p><span data-ttu-id="4672f-152">CD</span><span class="sxs-lookup"><span data-stu-id="4672f-152">DC</span></span></p></td>
<td><p><span data-ttu-id="4672f-153">Contrôleur de domaine Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="4672f-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4672f-154">09</span><span class="sxs-lookup"><span data-stu-id="4672f-154">9</span></span></p></td>
<td><p><span data-ttu-id="4672f-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="4672f-155">Group</span></span></p></td>
<td><p><span data-ttu-id="4672f-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4672f-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4672f-157">0,10</span><span class="sxs-lookup"><span data-stu-id="4672f-157">10</span></span></p></td>
<td><p><span data-ttu-id="4672f-158">Folder</span><span class="sxs-lookup"><span data-stu-id="4672f-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="4672f-159">Conteneur Active Directory ou unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="4672f-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4672f-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4672f-160">See Also</span></span>


[<span data-ttu-id="4672f-161">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4672f-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

