---
title: 'Lync Server 2013 : tblPrincipalInvites'
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
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="f5c4b-102">tblPrincipalInvites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5c4b-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c4b-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f5c4b-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f5c4b-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.</span><span class="sxs-lookup"><span data-stu-id="f5c4b-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="f5c4b-105">Celles</span><span class="sxs-lookup"><span data-stu-id="f5c4b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5c4b-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f5c4b-106">Column</span></span></th>
<th><span data-ttu-id="f5c4b-107">Type</span><span class="sxs-lookup"><span data-stu-id="f5c4b-107">Type</span></span></th>
<th><span data-ttu-id="f5c4b-108">Description</span><span class="sxs-lookup"><span data-stu-id="f5c4b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5c4b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f5c4b-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="f5c4b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="f5c4b-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c4b-112">invID</span><span class="sxs-lookup"><span data-stu-id="f5c4b-112">invID</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="f5c4b-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-114">Numéro séquentiel unique (par ID principal) généré à partir de la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="f5c4b-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c4b-115">ID</span><span class="sxs-lookup"><span data-stu-id="f5c4b-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-116">ent, non null</span><span class="sxs-lookup"><span data-stu-id="f5c4b-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="f5c4b-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c4b-118">Created</span><span class="sxs-lookup"><span data-stu-id="f5c4b-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-119">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="f5c4b-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-120">Heure de création</span><span class="sxs-lookup"><span data-stu-id="f5c4b-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f5c4b-121">Permettent</span><span class="sxs-lookup"><span data-stu-id="f5c4b-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5c4b-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="f5c4b-122">Column</span></span></th>
<th><span data-ttu-id="f5c4b-123">Description</span><span class="sxs-lookup"><span data-stu-id="f5c4b-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5c4b-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="f5c4b-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f5c4b-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c4b-126">prinID</span><span class="sxs-lookup"><span data-stu-id="f5c4b-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-127">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="f5c4b-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c4b-128">ID</span><span class="sxs-lookup"><span data-stu-id="f5c4b-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f5c4b-129">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="f5c4b-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

