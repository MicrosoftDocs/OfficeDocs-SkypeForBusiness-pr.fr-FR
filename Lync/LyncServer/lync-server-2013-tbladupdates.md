---
title: 'Lync Server 2013 : tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="e1a5d-102">tblADUpdates dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1a5d-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1a5d-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e1a5d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e1a5d-104">tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les étapes ultérieures de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="e1a5d-105">Celles</span><span class="sxs-lookup"><span data-stu-id="e1a5d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1a5d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1a5d-106">Column</span></span></th>
<th><span data-ttu-id="e1a5d-107">Type</span><span class="sxs-lookup"><span data-stu-id="e1a5d-107">Type</span></span></th>
<th><span data-ttu-id="e1a5d-108">Description</span><span class="sxs-lookup"><span data-stu-id="e1a5d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1a5d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e1a5d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-111">GUID principal de l’objet qui a changé.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a5d-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="e1a5d-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-113">nvarchar (384), pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a5d-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="e1a5d-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-117">Vrai si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a5d-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="e1a5d-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-120">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a5d-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="e1a5d-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-122">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-123">Non utilisé.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a5d-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="e1a5d-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-125">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a5d-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e1a5d-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-128">DATEHEURE, pas null</span><span class="sxs-lookup"><span data-stu-id="e1a5d-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="e1a5d-129">Horodatage de la date d’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="e1a5d-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

