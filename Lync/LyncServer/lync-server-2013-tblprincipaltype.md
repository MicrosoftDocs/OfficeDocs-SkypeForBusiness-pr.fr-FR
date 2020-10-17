---
title: 'Lync Server 2013 : tblPrincipalType'
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
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536321"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="61129-102">tblPrincipalType dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61129-102">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61129-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="61129-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="61129-104">La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="61129-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="61129-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="61129-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61129-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="61129-106">Column</span></span></th>
<th><span data-ttu-id="61129-107">Type</span><span class="sxs-lookup"><span data-stu-id="61129-107">Type</span></span></th>
<th><span data-ttu-id="61129-108">Description</span><span class="sxs-lookup"><span data-stu-id="61129-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61129-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="61129-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="61129-110">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="61129-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="61129-111">ID de type Principal.</span><span class="sxs-lookup"><span data-stu-id="61129-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61129-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="61129-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="61129-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="61129-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="61129-114">Description du type.</span><span class="sxs-lookup"><span data-stu-id="61129-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61129-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="61129-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="61129-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="61129-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="61129-117">Vrai si le type correspond aux principaux qui sont utilisés pour des fonctions internes.</span><span class="sxs-lookup"><span data-stu-id="61129-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61129-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="61129-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="61129-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="61129-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="61129-120">Vrai si le type est un type utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61129-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="61129-121">Clé</span><span class="sxs-lookup"><span data-stu-id="61129-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61129-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="61129-122">Column</span></span></th>
<th><span data-ttu-id="61129-123">Description</span><span class="sxs-lookup"><span data-stu-id="61129-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61129-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="61129-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="61129-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="61129-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="61129-126">Valeurs principales</span><span class="sxs-lookup"><span data-stu-id="61129-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61129-127">ID</span><span class="sxs-lookup"><span data-stu-id="61129-127">ID</span></span></th>
<th><span data-ttu-id="61129-128">Role</span><span class="sxs-lookup"><span data-stu-id="61129-128">Role</span></span></th>
<th><span data-ttu-id="61129-129">Description</span><span class="sxs-lookup"><span data-stu-id="61129-129">Description</span></span></th>
<th><span data-ttu-id="61129-130">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="61129-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61129-131">0,1</span><span class="sxs-lookup"><span data-stu-id="61129-131">1</span></span></p></td>
<td><p><span data-ttu-id="61129-132">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="61129-132">Any</span></span></p></td>
<td><p><span data-ttu-id="61129-p101">Principal générique sans type connu. Inutilisé dans la table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="61129-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61129-135">n°2</span><span class="sxs-lookup"><span data-stu-id="61129-135">2</span></span></p></td>
<td><p><span data-ttu-id="61129-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="61129-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="61129-p102">Principal générique de type utilisateur. Inutilisé dans table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="61129-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="61129-139">Oui</span><span class="sxs-lookup"><span data-stu-id="61129-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61129-140">3</span><span class="sxs-lookup"><span data-stu-id="61129-140">3</span></span></p></td>
<td><p><span data-ttu-id="61129-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="61129-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="61129-p103">Principal générique avec sémantique de groupe. Inutilisé dans table tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="61129-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61129-144">4 </span><span class="sxs-lookup"><span data-stu-id="61129-144">4</span></span></p></td>
<td><p><span data-ttu-id="61129-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="61129-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="61129-146">Principal utilisé en interne par le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="61129-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61129-147">5 </span><span class="sxs-lookup"><span data-stu-id="61129-147">5</span></span></p></td>
<td><p><span data-ttu-id="61129-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="61129-148">User</span></span></p></td>
<td><p><span data-ttu-id="61129-149">Utilisateur régulier.</span><span class="sxs-lookup"><span data-stu-id="61129-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="61129-150">Oui</span><span class="sxs-lookup"><span data-stu-id="61129-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61129-151">8 </span><span class="sxs-lookup"><span data-stu-id="61129-151">8</span></span></p></td>
<td><p><span data-ttu-id="61129-152">DC</span><span class="sxs-lookup"><span data-stu-id="61129-152">DC</span></span></p></td>
<td><p><span data-ttu-id="61129-153">Contrôleur de domaine des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61129-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61129-154">9 </span><span class="sxs-lookup"><span data-stu-id="61129-154">9</span></span></p></td>
<td><p><span data-ttu-id="61129-155">Groupe</span><span class="sxs-lookup"><span data-stu-id="61129-155">Group</span></span></p></td>
<td><p><span data-ttu-id="61129-156">Groupe de sécurité Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61129-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61129-157">10 </span><span class="sxs-lookup"><span data-stu-id="61129-157">10</span></span></p></td>
<td><p><span data-ttu-id="61129-158">Folder</span><span class="sxs-lookup"><span data-stu-id="61129-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="61129-159">Conteneur ou unité d’organisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61129-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="61129-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61129-160">See Also</span></span>


[<span data-ttu-id="61129-161">tblPrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61129-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

