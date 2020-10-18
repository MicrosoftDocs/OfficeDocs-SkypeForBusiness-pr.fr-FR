---
title: 'Lync Server 2013 : tblPrincipalMemberDifference'
description: 'Lync Server 2013 : tblPrincipalMemberDifference.'
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
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573220"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="f1001-103">tblPrincipalMemberDifference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1001-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1001-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f1001-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f1001-105">tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les dernières étapes de synchronisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f1001-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="f1001-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="f1001-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1001-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="f1001-107">Column</span></span></th>
<th><span data-ttu-id="f1001-108">Type</span><span class="sxs-lookup"><span data-stu-id="f1001-108">Type</span></span></th>
<th><span data-ttu-id="f1001-109">Description</span><span class="sxs-lookup"><span data-stu-id="f1001-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1001-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f1001-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f1001-111">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="f1001-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f1001-112">GUID principal du groupe qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="f1001-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1001-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="f1001-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="f1001-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1001-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f1001-115">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="f1001-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1001-116">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="f1001-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="f1001-117">bit, non null</span><span class="sxs-lookup"><span data-stu-id="f1001-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f1001-p101">False si le membre a été ajouté. True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="f1001-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f1001-120">Clé</span><span class="sxs-lookup"><span data-stu-id="f1001-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1001-121">Colonne</span><span class="sxs-lookup"><span data-stu-id="f1001-121">Column</span></span></th>
<th><span data-ttu-id="f1001-122">Description</span><span class="sxs-lookup"><span data-stu-id="f1001-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1001-123">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="f1001-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="f1001-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f1001-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

