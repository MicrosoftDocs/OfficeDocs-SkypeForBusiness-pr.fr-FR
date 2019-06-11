---
title: 'Lync Server 2013 : tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9b067b9d04ecb32a3e43dbbd1f8435c00fa0c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="1ad37-102">tblPrincipalMeta dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ad37-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ad37-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1ad37-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1ad37-104">tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="1ad37-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="1ad37-105">Celles</span><span class="sxs-lookup"><span data-stu-id="1ad37-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ad37-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="1ad37-106">Column</span></span></th>
<th><span data-ttu-id="1ad37-107">Type</span><span class="sxs-lookup"><span data-stu-id="1ad37-107">Type</span></span></th>
<th><span data-ttu-id="1ad37-108">Description</span><span class="sxs-lookup"><span data-stu-id="1ad37-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ad37-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1ad37-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="1ad37-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="1ad37-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ad37-111">ID du principal.</span><span class="sxs-lookup"><span data-stu-id="1ad37-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ad37-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="1ad37-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="1ad37-113">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="1ad37-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1ad37-114">True si les affiliations principales doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="1ad37-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ad37-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="1ad37-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="1ad37-116">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="1ad37-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1ad37-117">True si les attributs principaux doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="1ad37-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ad37-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="1ad37-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="1ad37-119">bit, pas null</span><span class="sxs-lookup"><span data-stu-id="1ad37-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1ad37-120">True si l’objet principal a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="1ad37-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ad37-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="1ad37-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="1ad37-122">int</span><span class="sxs-lookup"><span data-stu-id="1ad37-122">int</span></span></p></td>
<td><p><span data-ttu-id="1ad37-123">Nombre de tentatives d’actualisation du principal à partir d’AD DS qui est déjà en passe.</span><span class="sxs-lookup"><span data-stu-id="1ad37-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ad37-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="1ad37-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="1ad37-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1ad37-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ad37-126">Horodatage de la dernière tentative d’actualisation du principal.</span><span class="sxs-lookup"><span data-stu-id="1ad37-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="1ad37-127">Il peut s’agir de la valeur null s’il n’y a pas encore de tentative d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="1ad37-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ad37-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="1ad37-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="1ad37-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1ad37-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ad37-130">Horodatage de la prochaine actualisation planifiée.</span><span class="sxs-lookup"><span data-stu-id="1ad37-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="1ad37-131">Peut être null s’il n’y a pas de planification ultérieure.</span><span class="sxs-lookup"><span data-stu-id="1ad37-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1ad37-132">Permettent</span><span class="sxs-lookup"><span data-stu-id="1ad37-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ad37-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="1ad37-133">Column</span></span></th>
<th><span data-ttu-id="1ad37-134">Description</span><span class="sxs-lookup"><span data-stu-id="1ad37-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ad37-135">prinID</span><span class="sxs-lookup"><span data-stu-id="1ad37-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="1ad37-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="1ad37-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ad37-137">prinID</span><span class="sxs-lookup"><span data-stu-id="1ad37-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="1ad37-138">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="1ad37-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

