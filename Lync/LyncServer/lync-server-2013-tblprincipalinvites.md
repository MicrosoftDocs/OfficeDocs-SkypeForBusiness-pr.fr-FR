---
title: 'Lync Server 2013 : tblPrincipalInvites'
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
ms.openlocfilehash: 5165adf5b9cb5ddeefe80895217e6b2265784855
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="07dc7-102">tblPrincipalInvites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07dc7-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07dc7-103">_**Dernière modification de la rubrique :** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="07dc7-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="07dc7-104">tblPrincipalInvites contient des invitations pour tous les utilisateurs configurés pour l’ensemble des nœuds avec l’option d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="07dc7-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="07dc7-105">Columns</span><span class="sxs-lookup"><span data-stu-id="07dc7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07dc7-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="07dc7-106">Column</span></span></th>
<th><span data-ttu-id="07dc7-107">Type</span><span class="sxs-lookup"><span data-stu-id="07dc7-107">Type</span></span></th>
<th><span data-ttu-id="07dc7-108">Description</span><span class="sxs-lookup"><span data-stu-id="07dc7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07dc7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="07dc7-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="07dc7-110">entier, non null</span><span class="sxs-lookup"><span data-stu-id="07dc7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="07dc7-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="07dc7-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07dc7-112">invID</span><span class="sxs-lookup"><span data-stu-id="07dc7-112">invID</span></span></p></td>
<td><p><span data-ttu-id="07dc7-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="07dc7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="07dc7-114">Numéro séquentiel unique (par ID principal) généré depuis la table tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="07dc7-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07dc7-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="07dc7-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="07dc7-116">int, non null</span><span class="sxs-lookup"><span data-stu-id="07dc7-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="07dc7-117">ID de nœud (salle de conversation uniquement).</span><span class="sxs-lookup"><span data-stu-id="07dc7-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07dc7-118">Created</span><span class="sxs-lookup"><span data-stu-id="07dc7-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="07dc7-119">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="07dc7-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="07dc7-120">Heure de création.</span><span class="sxs-lookup"><span data-stu-id="07dc7-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="07dc7-121">Keys</span><span class="sxs-lookup"><span data-stu-id="07dc7-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07dc7-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="07dc7-122">Column</span></span></th>
<th><span data-ttu-id="07dc7-123">Description</span><span class="sxs-lookup"><span data-stu-id="07dc7-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07dc7-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="07dc7-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="07dc7-125">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="07dc7-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07dc7-126">prinID</span><span class="sxs-lookup"><span data-stu-id="07dc7-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="07dc7-127">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="07dc7-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07dc7-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="07dc7-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="07dc7-129">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="07dc7-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

