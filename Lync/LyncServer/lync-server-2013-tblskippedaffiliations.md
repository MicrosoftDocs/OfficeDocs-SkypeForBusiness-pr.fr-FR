---
title: 'Lync Server 2013 : tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 510f9559091395665019dad699f346f26e81b1ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="36098-102">tblSkippedAffiliations dans Server 2013</span><span class="sxs-lookup"><span data-stu-id="36098-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36098-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="36098-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="36098-104">tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).</span><span class="sxs-lookup"><span data-stu-id="36098-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="36098-105">Celles</span><span class="sxs-lookup"><span data-stu-id="36098-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36098-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="36098-106">Column</span></span></th>
<th><span data-ttu-id="36098-107">Type</span><span class="sxs-lookup"><span data-stu-id="36098-107">Type</span></span></th>
<th><span data-ttu-id="36098-108">Description</span><span class="sxs-lookup"><span data-stu-id="36098-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36098-109">prinID</span><span class="sxs-lookup"><span data-stu-id="36098-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="36098-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="36098-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36098-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="36098-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36098-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="36098-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="36098-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="36098-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="36098-114">Chaîne identifiant l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="36098-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="36098-115">Le format est : GUID : {0} URI : {1} &gt; ID :{2}</span><span class="sxs-lookup"><span data-stu-id="36098-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36098-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="36098-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="36098-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="36098-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36098-118">ID de l’objet principal qui a mis à jour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="36098-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="36098-119">Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="36098-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="36098-120">Permettent</span><span class="sxs-lookup"><span data-stu-id="36098-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36098-121">Colonne (s)</span><span class="sxs-lookup"><span data-stu-id="36098-121">Column(s)</span></span></th>
<th><span data-ttu-id="36098-122">Description</span><span class="sxs-lookup"><span data-stu-id="36098-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36098-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="36098-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="36098-124">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="36098-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36098-125">prinID</span><span class="sxs-lookup"><span data-stu-id="36098-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="36098-126">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="36098-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

