---
title: 'Lync Server 2013 : tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="2f4c7-102">tblPrincipalRole dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f4c7-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f4c7-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2f4c7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2f4c7-104">tblPrincipalRole contient des rôles explicites attribués aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="2f4c7-105">Celles</span><span class="sxs-lookup"><span data-stu-id="2f4c7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f4c7-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="2f4c7-106">Column</span></span></th>
<th><span data-ttu-id="2f4c7-107">Type</span><span class="sxs-lookup"><span data-stu-id="2f4c7-107">Type</span></span></th>
<th><span data-ttu-id="2f4c7-108">Description</span><span class="sxs-lookup"><span data-stu-id="2f4c7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f4c7-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="2f4c7-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="2f4c7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-111">ID du nœud auquel le rôle s’applique.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f4c7-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="2f4c7-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="2f4c7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f4c7-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="2f4c7-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="2f4c7-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-117">ID du type de rôle (de tblRoleType)</span><span class="sxs-lookup"><span data-stu-id="2f4c7-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f4c7-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="2f4c7-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-119">ent, non null</span><span class="sxs-lookup"><span data-stu-id="2f4c7-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-120">ID de l’élément principal qui a mis à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2f4c7-121">Permettent</span><span class="sxs-lookup"><span data-stu-id="2f4c7-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f4c7-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="2f4c7-122">Column</span></span></th>
<th><span data-ttu-id="2f4c7-123">Description</span><span class="sxs-lookup"><span data-stu-id="2f4c7-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f4c7-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="2f4c7-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f4c7-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="2f4c7-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-127">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f4c7-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="2f4c7-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-129">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f4c7-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="2f4c7-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="2f4c7-131">Clé étrangère avec recherche dans la table tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="2f4c7-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

