---
title: 'Lync Server 2013 : tblPrincipalInvites'
description: 'Lync Server 2013 : tblPrincipalInvites.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564670"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="a0862-103">tblPrincipalInvites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0862-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0862-104">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="a0862-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="a0862-105">tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="a0862-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="a0862-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="a0862-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0862-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="a0862-107">Column</span></span></th>
<th><span data-ttu-id="a0862-108">Type</span><span class="sxs-lookup"><span data-stu-id="a0862-108">Type</span></span></th>
<th><span data-ttu-id="a0862-109">Description</span><span class="sxs-lookup"><span data-stu-id="a0862-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0862-110">prinID</span><span class="sxs-lookup"><span data-stu-id="a0862-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="a0862-111">int, non null</span><span class="sxs-lookup"><span data-stu-id="a0862-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a0862-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="a0862-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0862-113">invID</span><span class="sxs-lookup"><span data-stu-id="a0862-113">invID</span></span></p></td>
<td><p><span data-ttu-id="a0862-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="a0862-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a0862-115">Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="a0862-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0862-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="a0862-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="a0862-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="a0862-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a0862-118">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="a0862-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0862-119">Created</span><span class="sxs-lookup"><span data-stu-id="a0862-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="a0862-120">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="a0862-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="a0862-121">Heure de création.</span><span class="sxs-lookup"><span data-stu-id="a0862-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a0862-122">Keys</span><span class="sxs-lookup"><span data-stu-id="a0862-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0862-123">Colonne</span><span class="sxs-lookup"><span data-stu-id="a0862-123">Column</span></span></th>
<th><span data-ttu-id="a0862-124">Description</span><span class="sxs-lookup"><span data-stu-id="a0862-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0862-125">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="a0862-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a0862-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a0862-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0862-127">prinID</span><span class="sxs-lookup"><span data-stu-id="a0862-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="a0862-128">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="a0862-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0862-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="a0862-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="a0862-130">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="a0862-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

