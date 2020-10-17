---
title: 'Lync Server 2013 : tblADUpdates'
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
ms.openlocfilehash: 27fbbc6bb2fe68c2f4bfff91b999934069548d00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509481"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="2ead0-102">tblADUpdates dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ead0-102">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ead0-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2ead0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2ead0-104">tblADUpdates contient les modifications des services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ead0-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="2ead0-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="2ead0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ead0-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="2ead0-106">Column</span></span></th>
<th><span data-ttu-id="2ead0-107">Type</span><span class="sxs-lookup"><span data-stu-id="2ead0-107">Type</span></span></th>
<th><span data-ttu-id="2ead0-108">Description</span><span class="sxs-lookup"><span data-stu-id="2ead0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ead0-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2ead0-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2ead0-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-111">GUID de principal de l’objet qui a changé.</span><span class="sxs-lookup"><span data-stu-id="2ead0-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ead0-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="2ead0-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="2ead0-113">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-114">Nom unique de l’objet.</span><span class="sxs-lookup"><span data-stu-id="2ead0-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ead0-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="2ead0-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="2ead0-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-117">True si au moins un attribut de l’objet a changé.</span><span class="sxs-lookup"><span data-stu-id="2ead0-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ead0-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="2ead0-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="2ead0-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-120">True si l’appartenance a changé.</span><span class="sxs-lookup"><span data-stu-id="2ead0-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ead0-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="2ead0-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="2ead0-122">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-123">Inutilisé.</span><span class="sxs-lookup"><span data-stu-id="2ead0-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ead0-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="2ead0-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="2ead0-125">bit, non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-126">True si l’objet a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="2ead0-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ead0-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2ead0-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2ead0-128">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="2ead0-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2ead0-129">Horodatage de l’insertion de la ligne.</span><span class="sxs-lookup"><span data-stu-id="2ead0-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

