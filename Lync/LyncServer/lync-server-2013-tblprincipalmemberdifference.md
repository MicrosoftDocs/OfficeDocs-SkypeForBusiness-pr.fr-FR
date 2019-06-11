---
title: 'Lync Server 2013 : tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5db403431c182e3f5bb8e7a3fabaa04cd2a94d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="f85f6-102">tblPrincipalMemberDifference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f85f6-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f85f6-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f85f6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f85f6-104">tblPrincipalMemberDifference contient les modifications d’appartenance au groupe (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f85f6-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="f85f6-105">Celles</span><span class="sxs-lookup"><span data-stu-id="f85f6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f85f6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f85f6-106">Column</span></span></th>
<th><span data-ttu-id="f85f6-107">Type</span><span class="sxs-lookup"><span data-stu-id="f85f6-107">Type</span></span></th>
<th><span data-ttu-id="f85f6-108">Description</span><span class="sxs-lookup"><span data-stu-id="f85f6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f85f6-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f85f6-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f85f6-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="f85f6-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f85f6-111">GUID principal du groupe qui a changé.</span><span class="sxs-lookup"><span data-stu-id="f85f6-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85f6-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="f85f6-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="f85f6-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f85f6-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f85f6-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="f85f6-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85f6-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="f85f6-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="f85f6-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="f85f6-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f85f6-117">False si le membre a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="f85f6-117">False if the member was added.</span></span> <span data-ttu-id="f85f6-118">True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="f85f6-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f85f6-119">Clé</span><span class="sxs-lookup"><span data-stu-id="f85f6-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f85f6-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="f85f6-120">Column</span></span></th>
<th><span data-ttu-id="f85f6-121">Description</span><span class="sxs-lookup"><span data-stu-id="f85f6-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f85f6-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="f85f6-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="f85f6-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f85f6-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

