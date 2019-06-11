---
title: 'Lync Server 2013 : tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="66192-102">tblScopePrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66192-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66192-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="66192-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="66192-104">tblScopePrincipal contient les étendues attribuées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="66192-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="66192-105">Celles</span><span class="sxs-lookup"><span data-stu-id="66192-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66192-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="66192-106">Column</span></span></th>
<th><span data-ttu-id="66192-107">Type</span><span class="sxs-lookup"><span data-stu-id="66192-107">Type</span></span></th>
<th><span data-ttu-id="66192-108">Description</span><span class="sxs-lookup"><span data-stu-id="66192-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66192-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="66192-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="66192-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="66192-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="66192-111">ID du nœud auquel s’applique l’étendue.</span><span class="sxs-lookup"><span data-stu-id="66192-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66192-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="66192-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="66192-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="66192-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="66192-114">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="66192-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66192-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="66192-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="66192-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="66192-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="66192-117">True si le type d’étendue est Deny; False si Allow.</span><span class="sxs-lookup"><span data-stu-id="66192-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66192-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="66192-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="66192-119">ent, non null</span><span class="sxs-lookup"><span data-stu-id="66192-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="66192-120">ID de l’élément principal qui a mis à jour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="66192-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="66192-121">Permettent</span><span class="sxs-lookup"><span data-stu-id="66192-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66192-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="66192-122">Column</span></span></th>
<th><span data-ttu-id="66192-123">Description</span><span class="sxs-lookup"><span data-stu-id="66192-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66192-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="66192-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="66192-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="66192-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66192-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="66192-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="66192-127">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="66192-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66192-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="66192-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="66192-129">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="66192-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

