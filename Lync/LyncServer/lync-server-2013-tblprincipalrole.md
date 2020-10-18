---
title: 'Lync Server 2013 : tblPrincipalRole'
description: 'Lync Server 2013 : tblPrincipalRole.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573630"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="f2f1c-103">tblPrincipalRole dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2f1c-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2f1c-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f2f1c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f2f1c-105">La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="f2f1c-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="f2f1c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2f1c-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="f2f1c-107">Column</span></span></th>
<th><span data-ttu-id="f2f1c-108">Type</span><span class="sxs-lookup"><span data-stu-id="f2f1c-108">Type</span></span></th>
<th><span data-ttu-id="f2f1c-109">Description</span><span class="sxs-lookup"><span data-stu-id="f2f1c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2f1c-110">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f2f1c-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-111">entier, non null</span><span class="sxs-lookup"><span data-stu-id="f2f1c-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-112">ID du nœud auquel le rôle s’applique.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2f1c-113">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f2f1c-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-114">entier, non null</span><span class="sxs-lookup"><span data-stu-id="f2f1c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-115">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2f1c-116">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f2f1c-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-117">entier, non null</span><span class="sxs-lookup"><span data-stu-id="f2f1c-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-118">ID du type de rôle (d’après tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="f2f1c-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2f1c-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f2f1c-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-120">entier, non null</span><span class="sxs-lookup"><span data-stu-id="f2f1c-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-121">ID du principal qui a mis à jour cette entrée en dernier.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f2f1c-122">Keys</span><span class="sxs-lookup"><span data-stu-id="f2f1c-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2f1c-123">Colonne</span><span class="sxs-lookup"><span data-stu-id="f2f1c-123">Column</span></span></th>
<th><span data-ttu-id="f2f1c-124">Description</span><span class="sxs-lookup"><span data-stu-id="f2f1c-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2f1c-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="f2f1c-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2f1c-127">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f2f1c-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-128">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2f1c-129">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f2f1c-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-130">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2f1c-131">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f2f1c-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="f2f1c-132">Clé étrangère avec recherche dans la table tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

