---
title: 'Lync Server 2013 : tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baaf336013ec09b17b8e688889fdf27aa29ef644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="087a9-102">tblPrincipalMemberDifference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="087a9-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="087a9-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="087a9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="087a9-104">tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="087a9-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="087a9-105">Celles</span><span class="sxs-lookup"><span data-stu-id="087a9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="087a9-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="087a9-106">Column</span></span></th>
<th><span data-ttu-id="087a9-107">Type</span><span class="sxs-lookup"><span data-stu-id="087a9-107">Type</span></span></th>
<th><span data-ttu-id="087a9-108">Description</span><span class="sxs-lookup"><span data-stu-id="087a9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="087a9-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="087a9-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="087a9-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="087a9-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="087a9-111">GUID principal du groupe qui a changé.</span><span class="sxs-lookup"><span data-stu-id="087a9-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="087a9-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="087a9-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="087a9-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="087a9-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="087a9-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="087a9-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="087a9-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="087a9-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="087a9-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="087a9-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="087a9-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="087a9-117">False if the member was added.</span></span> <span data-ttu-id="087a9-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="087a9-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="087a9-119">Clé</span><span class="sxs-lookup"><span data-stu-id="087a9-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="087a9-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="087a9-120">Column</span></span></th>
<th><span data-ttu-id="087a9-121">Description</span><span class="sxs-lookup"><span data-stu-id="087a9-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="087a9-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="087a9-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="087a9-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="087a9-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

