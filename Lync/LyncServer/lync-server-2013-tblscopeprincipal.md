---
title: 'Lync Server 2013 : tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab3faccea0ba914ca17c9aefcd0ea112e5b58a96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="35b77-102">tblScopePrincipal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b77-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35b77-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="35b77-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="35b77-104">tblScopePrincipal contient les étendues assignées aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="35b77-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="35b77-105">Columns</span><span class="sxs-lookup"><span data-stu-id="35b77-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35b77-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="35b77-106">Column</span></span></th>
<th><span data-ttu-id="35b77-107">Type</span><span class="sxs-lookup"><span data-stu-id="35b77-107">Type</span></span></th>
<th><span data-ttu-id="35b77-108">Description</span><span class="sxs-lookup"><span data-stu-id="35b77-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35b77-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="35b77-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="35b77-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="35b77-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="35b77-111">ID du nœud auquel s’applique l’étendue.</span><span class="sxs-lookup"><span data-stu-id="35b77-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b77-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="35b77-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="35b77-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="35b77-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="35b77-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="35b77-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b77-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="35b77-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="35b77-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="35b77-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="35b77-117">Valeur True si le type d’étendue est Refuser ; False pour Autoriser.</span><span class="sxs-lookup"><span data-stu-id="35b77-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b77-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="35b77-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="35b77-119">int, non null</span><span class="sxs-lookup"><span data-stu-id="35b77-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="35b77-120">ID du principal qui a mis à jour cette entrée en dernier.</span><span class="sxs-lookup"><span data-stu-id="35b77-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="35b77-121">Keys</span><span class="sxs-lookup"><span data-stu-id="35b77-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35b77-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="35b77-122">Column</span></span></th>
<th><span data-ttu-id="35b77-123">Description</span><span class="sxs-lookup"><span data-stu-id="35b77-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35b77-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="35b77-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="35b77-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="35b77-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b77-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="35b77-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="35b77-127">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="35b77-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b77-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="35b77-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="35b77-129">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="35b77-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

