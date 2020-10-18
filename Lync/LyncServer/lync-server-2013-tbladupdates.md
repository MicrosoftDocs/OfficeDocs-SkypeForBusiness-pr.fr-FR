---
title: 'Lync Server 2013 : tblADUpdates'
description: 'Lync Server 2013 : tblADUpdates.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573680"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="2e9bc-103">tblADUpdates dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9bc-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e9bc-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2e9bc-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2e9bc-105">tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="2e9bc-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="2e9bc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e9bc-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="2e9bc-107">Column</span></span></th>
<th><span data-ttu-id="2e9bc-108">Type</span><span class="sxs-lookup"><span data-stu-id="2e9bc-108">Type</span></span></th>
<th><span data-ttu-id="2e9bc-109">Description</span><span class="sxs-lookup"><span data-stu-id="2e9bc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e9bc-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2e9bc-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-111">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-112">GUID de principal de l’objet qui a changé.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9bc-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="2e9bc-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-114">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-115">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e9bc-116">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="2e9bc-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-117">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-118">True si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9bc-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="2e9bc-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-120">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-121">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e9bc-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="2e9bc-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-123">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-124">Inutilisé.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e9bc-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="2e9bc-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-126">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-127">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e9bc-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2e9bc-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-129">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="2e9bc-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2e9bc-130">Horodatage de l’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="2e9bc-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

