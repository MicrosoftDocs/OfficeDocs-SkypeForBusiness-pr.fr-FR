---
title: 'Lync Server 2013 : tblPrincipalType'
description: 'Lync Server 2013 : tblPrincipalType.'
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
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549860"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="a5887-103">tblPrincipalType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5887-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5887-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a5887-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a5887-105">La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a5887-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="a5887-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="a5887-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5887-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="a5887-107">Column</span></span></th>
<th><span data-ttu-id="a5887-108">Type</span><span class="sxs-lookup"><span data-stu-id="a5887-108">Type</span></span></th>
<th><span data-ttu-id="a5887-109">Description</span><span class="sxs-lookup"><span data-stu-id="a5887-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5887-110">ptypeID</span><span class="sxs-lookup"><span data-stu-id="a5887-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="a5887-111">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="a5887-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a5887-112">ID de type Principal.</span><span class="sxs-lookup"><span data-stu-id="a5887-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5887-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="a5887-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="a5887-114">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="a5887-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a5887-115">Description du type.</span><span class="sxs-lookup"><span data-stu-id="a5887-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5887-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="a5887-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="a5887-117">bit, non null</span><span class="sxs-lookup"><span data-stu-id="a5887-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="a5887-118">Vrai si le type correspond aux principaux qui sont utilisés pour des fonctions internes.</span><span class="sxs-lookup"><span data-stu-id="a5887-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5887-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="a5887-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="a5887-120">bit, non null</span><span class="sxs-lookup"><span data-stu-id="a5887-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="a5887-121">Vrai si le type est un type utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a5887-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a5887-122">Clé</span><span class="sxs-lookup"><span data-stu-id="a5887-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5887-123">Colonne</span><span class="sxs-lookup"><span data-stu-id="a5887-123">Column</span></span></th>
<th><span data-ttu-id="a5887-124">Description</span><span class="sxs-lookup"><span data-stu-id="a5887-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5887-125">ptypeID</span><span class="sxs-lookup"><span data-stu-id="a5887-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="a5887-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a5887-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="a5887-127">Valeurs principales</span><span class="sxs-lookup"><span data-stu-id="a5887-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5887-128">ID</span><span class="sxs-lookup"><span data-stu-id="a5887-128">ID</span></span></th>
<th><span data-ttu-id="a5887-129">Role</span><span class="sxs-lookup"><span data-stu-id="a5887-129">Role</span></span></th>
<th><span data-ttu-id="a5887-130">Description</span><span class="sxs-lookup"><span data-stu-id="a5887-130">Description</span></span></th>
<th><span data-ttu-id="a5887-131">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="a5887-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5887-132">0,1</span><span class="sxs-lookup"><span data-stu-id="a5887-132">1</span></span></p></td>
<td><p><span data-ttu-id="a5887-133">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="a5887-133">Any</span></span></p></td>
<td><p><span data-ttu-id="a5887-p101">Principal générique sans type connu. Inutilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a5887-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5887-136">n°2</span><span class="sxs-lookup"><span data-stu-id="a5887-136">2</span></span></p></td>
<td><p><span data-ttu-id="a5887-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="a5887-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="a5887-p102">Principal générique de type utilisateur. Inutilisé dans table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a5887-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="a5887-140">Oui</span><span class="sxs-lookup"><span data-stu-id="a5887-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5887-141">3</span><span class="sxs-lookup"><span data-stu-id="a5887-141">3</span></span></p></td>
<td><p><span data-ttu-id="a5887-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="a5887-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="a5887-p103">Principal générique avec sémantique de groupe. Inutilisé dans table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="a5887-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5887-145">4 </span><span class="sxs-lookup"><span data-stu-id="a5887-145">4</span></span></p></td>
<td><p><span data-ttu-id="a5887-146">SystemUser</span><span class="sxs-lookup"><span data-stu-id="a5887-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="a5887-147">Principal utilisé en interne par le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="a5887-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5887-148">5 </span><span class="sxs-lookup"><span data-stu-id="a5887-148">5</span></span></p></td>
<td><p><span data-ttu-id="a5887-149">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="a5887-149">User</span></span></p></td>
<td><p><span data-ttu-id="a5887-150">Utilisateur régulier.</span><span class="sxs-lookup"><span data-stu-id="a5887-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="a5887-151">Oui</span><span class="sxs-lookup"><span data-stu-id="a5887-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5887-152">8 </span><span class="sxs-lookup"><span data-stu-id="a5887-152">8</span></span></p></td>
<td><p><span data-ttu-id="a5887-153">DC</span><span class="sxs-lookup"><span data-stu-id="a5887-153">DC</span></span></p></td>
<td><p><span data-ttu-id="a5887-154">Contrôleur de domaine des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5887-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5887-155">9 </span><span class="sxs-lookup"><span data-stu-id="a5887-155">9</span></span></p></td>
<td><p><span data-ttu-id="a5887-156">Groupe</span><span class="sxs-lookup"><span data-stu-id="a5887-156">Group</span></span></p></td>
<td><p><span data-ttu-id="a5887-157">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5887-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5887-158">10 </span><span class="sxs-lookup"><span data-stu-id="a5887-158">10</span></span></p></td>
<td><p><span data-ttu-id="a5887-159">Folder</span><span class="sxs-lookup"><span data-stu-id="a5887-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="a5887-160">Conteneur ou unité d’organisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5887-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a5887-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5887-161">See Also</span></span>


[<span data-ttu-id="a5887-162">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5887-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

