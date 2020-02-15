---
title: 'Lync Server 2013 : tblPrincipalMeta'
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
ms.openlocfilehash: 3a3571cd93ae5d69fa4a432035284b9a752287b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="9277c-102">tblPrincipalMeta dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9277c-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9277c-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9277c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9277c-104">tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9277c-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="9277c-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9277c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9277c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="9277c-106">Column</span></span></th>
<th><span data-ttu-id="9277c-107">Type</span><span class="sxs-lookup"><span data-stu-id="9277c-107">Type</span></span></th>
<th><span data-ttu-id="9277c-108">Description</span><span class="sxs-lookup"><span data-stu-id="9277c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9277c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9277c-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="9277c-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="9277c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9277c-111">ID de principal.</span><span class="sxs-lookup"><span data-stu-id="9277c-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9277c-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="9277c-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="9277c-113">bit, non null</span><span class="sxs-lookup"><span data-stu-id="9277c-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9277c-114">True si les affiliations de principaux doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="9277c-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9277c-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="9277c-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="9277c-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="9277c-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9277c-117">True si les attributs de principaux doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="9277c-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9277c-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="9277c-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="9277c-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="9277c-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9277c-120">True si le principal doit être supprimé.</span><span class="sxs-lookup"><span data-stu-id="9277c-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9277c-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="9277c-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="9277c-122">int</span><span class="sxs-lookup"><span data-stu-id="9277c-122">int</span></span></p></td>
<td><p><span data-ttu-id="9277c-123">Nombre de tentatives d’actualisation à partir des services AD DS ayant eu lieu jusqu’à maintenant.</span><span class="sxs-lookup"><span data-stu-id="9277c-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9277c-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="9277c-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="9277c-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9277c-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="9277c-p101">Horodatage de la dernière tentative d’actualisation du principal. Peut être null si aucune actualisation n’a encore été tentée.</span><span class="sxs-lookup"><span data-stu-id="9277c-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9277c-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="9277c-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="9277c-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9277c-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="9277c-p102">Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation supplémentaire n’a été planifiée.</span><span class="sxs-lookup"><span data-stu-id="9277c-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9277c-132">Keys</span><span class="sxs-lookup"><span data-stu-id="9277c-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9277c-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="9277c-133">Column</span></span></th>
<th><span data-ttu-id="9277c-134">Description</span><span class="sxs-lookup"><span data-stu-id="9277c-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9277c-135">prinID</span><span class="sxs-lookup"><span data-stu-id="9277c-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="9277c-136">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9277c-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9277c-137">prinID</span><span class="sxs-lookup"><span data-stu-id="9277c-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="9277c-138">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9277c-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

