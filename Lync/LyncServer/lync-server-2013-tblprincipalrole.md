---
title: 'Lync Server 2013 : tblPrincipalRole'
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
ms.openlocfilehash: 76dda06baa4e5fab51ca44586f7f8fce00860695
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523611"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="04ccb-102">tblPrincipalRole dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04ccb-102">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04ccb-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="04ccb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="04ccb-104">La table tblPrincipalRole contient les rôles explicites affectés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="04ccb-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="04ccb-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="04ccb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ccb-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="04ccb-106">Column</span></span></th>
<th><span data-ttu-id="04ccb-107">Type</span><span class="sxs-lookup"><span data-stu-id="04ccb-107">Type</span></span></th>
<th><span data-ttu-id="04ccb-108">Description</span><span class="sxs-lookup"><span data-stu-id="04ccb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ccb-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="04ccb-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="04ccb-110">entier, non null</span><span class="sxs-lookup"><span data-stu-id="04ccb-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04ccb-111">ID du nœud auquel le rôle s’applique.</span><span class="sxs-lookup"><span data-stu-id="04ccb-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ccb-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="04ccb-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="04ccb-113">entier, non null</span><span class="sxs-lookup"><span data-stu-id="04ccb-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04ccb-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="04ccb-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ccb-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="04ccb-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="04ccb-116">entier, non null</span><span class="sxs-lookup"><span data-stu-id="04ccb-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04ccb-117">ID du type de rôle (d’après tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="04ccb-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ccb-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="04ccb-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="04ccb-119">entier, non null</span><span class="sxs-lookup"><span data-stu-id="04ccb-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="04ccb-120">ID du principal qui a mis à jour cette entrée en dernier.</span><span class="sxs-lookup"><span data-stu-id="04ccb-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="04ccb-121">Keys</span><span class="sxs-lookup"><span data-stu-id="04ccb-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ccb-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="04ccb-122">Column</span></span></th>
<th><span data-ttu-id="04ccb-123">Description</span><span class="sxs-lookup"><span data-stu-id="04ccb-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ccb-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="04ccb-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="04ccb-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="04ccb-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ccb-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="04ccb-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="04ccb-127">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="04ccb-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ccb-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="04ccb-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="04ccb-129">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="04ccb-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ccb-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="04ccb-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="04ccb-131">Clé étrangère avec recherche dans la table tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="04ccb-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

