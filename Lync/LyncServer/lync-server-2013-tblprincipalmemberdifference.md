---
title: 'Lync Server 2013 : tblPrincipalMemberDifference'
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
ms.openlocfilehash: 0ca8ccc9c60bdd608992dc3daf085568d34bee69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="402df-102">tblPrincipalMemberDifference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="402df-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="402df-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="402df-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="402df-104">tblPrincipalMemberDifference contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les dernières étapes de synchronisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="402df-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="402df-105">Columns</span><span class="sxs-lookup"><span data-stu-id="402df-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="402df-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="402df-106">Column</span></span></th>
<th><span data-ttu-id="402df-107">Type</span><span class="sxs-lookup"><span data-stu-id="402df-107">Type</span></span></th>
<th><span data-ttu-id="402df-108">Description</span><span class="sxs-lookup"><span data-stu-id="402df-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="402df-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="402df-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="402df-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="402df-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="402df-111">GUID principal du groupe qui a été modifié.</span><span class="sxs-lookup"><span data-stu-id="402df-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="402df-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="402df-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="402df-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="402df-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="402df-114">Nom unique du membre.</span><span class="sxs-lookup"><span data-stu-id="402df-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="402df-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="402df-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="402df-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="402df-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="402df-p101">False si le membre a été ajouté. True si le membre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="402df-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="402df-119">Clé</span><span class="sxs-lookup"><span data-stu-id="402df-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="402df-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="402df-120">Column</span></span></th>
<th><span data-ttu-id="402df-121">Description</span><span class="sxs-lookup"><span data-stu-id="402df-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="402df-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="402df-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="402df-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="402df-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

