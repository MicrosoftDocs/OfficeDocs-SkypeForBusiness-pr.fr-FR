---
title: 'Lync Server 2013 : tblPrincipalMembers'
description: 'Lync Server 2013 : tblPrincipalMembers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bbb8be0b83d09b1bd54ea98655558581e6df834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573180"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="7a605-103">tblPrincipalMembers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a605-103">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a605-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7a605-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7a605-105">tblPrincipalMembers contient des appartenances aux principaux.</span><span class="sxs-lookup"><span data-stu-id="7a605-105">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="7a605-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="7a605-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a605-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a605-107">Column</span></span></th>
<th><span data-ttu-id="7a605-108">Type</span><span class="sxs-lookup"><span data-stu-id="7a605-108">Type</span></span></th>
<th><span data-ttu-id="7a605-109">Description</span><span class="sxs-lookup"><span data-stu-id="7a605-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a605-110">prinID</span><span class="sxs-lookup"><span data-stu-id="7a605-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="7a605-111">int, non null</span><span class="sxs-lookup"><span data-stu-id="7a605-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7a605-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="7a605-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a605-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="7a605-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="7a605-114">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="7a605-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="7a605-115">Nom unique d’un membre.</span><span class="sxs-lookup"><span data-stu-id="7a605-115">Distinguished name of a member.</span></span> <span data-ttu-id="7a605-116">Un membre ne doit pas nécessairement être un principal (dans la table tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="7a605-116">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7a605-117">Keys</span><span class="sxs-lookup"><span data-stu-id="7a605-117">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a605-118">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a605-118">Column</span></span></th>
<th><span data-ttu-id="7a605-119">Description</span><span class="sxs-lookup"><span data-stu-id="7a605-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a605-120">&lt;prinID, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="7a605-120">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="7a605-121">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="7a605-121">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a605-122">prinID</span><span class="sxs-lookup"><span data-stu-id="7a605-122">prinID</span></span></p></td>
<td><p><span data-ttu-id="7a605-123">Clé étrangère avec recherche dans tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="7a605-123">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

