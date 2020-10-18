---
title: 'Lync Server 2013 : tblPrincipalMeta'
description: 'Lync Server 2013 : tblPrincipalMeta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573640"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="b0f91-103">tblPrincipalMeta dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0f91-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0f91-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b0f91-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b0f91-105">tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0f91-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="b0f91-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="b0f91-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0f91-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="b0f91-107">Column</span></span></th>
<th><span data-ttu-id="b0f91-108">Type</span><span class="sxs-lookup"><span data-stu-id="b0f91-108">Type</span></span></th>
<th><span data-ttu-id="b0f91-109">Description</span><span class="sxs-lookup"><span data-stu-id="b0f91-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0f91-110">prinID</span><span class="sxs-lookup"><span data-stu-id="b0f91-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="b0f91-111">int, non null</span><span class="sxs-lookup"><span data-stu-id="b0f91-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0f91-112">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="b0f91-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f91-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="b0f91-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="b0f91-114">bit, non null</span><span class="sxs-lookup"><span data-stu-id="b0f91-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b0f91-115">True si les affiliations de principaux doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="b0f91-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f91-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="b0f91-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="b0f91-117">bit, non null</span><span class="sxs-lookup"><span data-stu-id="b0f91-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b0f91-118">True si les attributs de principaux doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="b0f91-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f91-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="b0f91-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="b0f91-120">bit, non null</span><span class="sxs-lookup"><span data-stu-id="b0f91-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b0f91-121">True si le principal doit être supprimé.</span><span class="sxs-lookup"><span data-stu-id="b0f91-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f91-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="b0f91-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="b0f91-123">int</span><span class="sxs-lookup"><span data-stu-id="b0f91-123">int</span></span></p></td>
<td><p><span data-ttu-id="b0f91-124">Nombre de tentatives d’actualisation à partir des services AD DS ayant eu lieu jusqu’à maintenant.</span><span class="sxs-lookup"><span data-stu-id="b0f91-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f91-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="b0f91-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="b0f91-126">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b0f91-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0f91-p101">Horodatage de la dernière tentative d’actualisation du principal. Peut être null si aucune actualisation n’a encore été tentée.</span><span class="sxs-lookup"><span data-stu-id="b0f91-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f91-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="b0f91-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="b0f91-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b0f91-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0f91-p102">Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation supplémentaire n’a été planifiée.</span><span class="sxs-lookup"><span data-stu-id="b0f91-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b0f91-133">Keys</span><span class="sxs-lookup"><span data-stu-id="b0f91-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0f91-134">Colonne</span><span class="sxs-lookup"><span data-stu-id="b0f91-134">Column</span></span></th>
<th><span data-ttu-id="b0f91-135">Description</span><span class="sxs-lookup"><span data-stu-id="b0f91-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0f91-136">prinID</span><span class="sxs-lookup"><span data-stu-id="b0f91-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="b0f91-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b0f91-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f91-138">prinID</span><span class="sxs-lookup"><span data-stu-id="b0f91-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="b0f91-139">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b0f91-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

