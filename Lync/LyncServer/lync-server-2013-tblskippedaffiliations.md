---
title: 'Lync Server 2013 : tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="afd8f-102">tblSkippedAffiliations dans Server 2013</span><span class="sxs-lookup"><span data-stu-id="afd8f-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd8f-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="afd8f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="afd8f-104">tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="afd8f-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="afd8f-105">Celles</span><span class="sxs-lookup"><span data-stu-id="afd8f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afd8f-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="afd8f-106">Column</span></span></th>
<th><span data-ttu-id="afd8f-107">Type</span><span class="sxs-lookup"><span data-stu-id="afd8f-107">Type</span></span></th>
<th><span data-ttu-id="afd8f-108">Description</span><span class="sxs-lookup"><span data-stu-id="afd8f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afd8f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="afd8f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="afd8f-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="afd8f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="afd8f-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="afd8f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd8f-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="afd8f-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="afd8f-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="afd8f-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="afd8f-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="afd8f-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="afd8f-115">Le format est: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="afd8f-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd8f-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="afd8f-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="afd8f-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="afd8f-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="afd8f-118">ID de l’objet principal qui a mis à jour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="afd8f-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="afd8f-119">Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="afd8f-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="afd8f-120">Permettent</span><span class="sxs-lookup"><span data-stu-id="afd8f-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afd8f-121">Colonne (s)</span><span class="sxs-lookup"><span data-stu-id="afd8f-121">Column(s)</span></span></th>
<th><span data-ttu-id="afd8f-122">Description</span><span class="sxs-lookup"><span data-stu-id="afd8f-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afd8f-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="afd8f-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="afd8f-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="afd8f-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd8f-125">prinID</span><span class="sxs-lookup"><span data-stu-id="afd8f-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="afd8f-126">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="afd8f-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

