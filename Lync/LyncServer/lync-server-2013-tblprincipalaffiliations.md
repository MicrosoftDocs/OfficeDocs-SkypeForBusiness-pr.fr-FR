---
title: 'Lync Server 2013 : tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec2ef70b70ff496852a753a9e15a38f80de1509b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523741"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="b0165-102">tblPrincipalAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0165-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0165-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b0165-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b0165-104">tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances aux emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.</span><span class="sxs-lookup"><span data-stu-id="b0165-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="b0165-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="b0165-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0165-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="b0165-106">Column</span></span></th>
<th><span data-ttu-id="b0165-107">Type</span><span class="sxs-lookup"><span data-stu-id="b0165-107">Type</span></span></th>
<th><span data-ttu-id="b0165-108">Description</span><span class="sxs-lookup"><span data-stu-id="b0165-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0165-109">principalID</span><span class="sxs-lookup"><span data-stu-id="b0165-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="b0165-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="b0165-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0165-111">ID du principal affilié.</span><span class="sxs-lookup"><span data-stu-id="b0165-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0165-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b0165-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b0165-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="b0165-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0165-p101">ID du principal représentant l’affiliation. Chaque principal (sauf system-user-types) possède également une auto-affiliation.</span><span class="sxs-lookup"><span data-stu-id="b0165-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0165-116">Index</span><span class="sxs-lookup"><span data-stu-id="b0165-116">index</span></span></p></td>
<td><p><span data-ttu-id="b0165-117">int, non null</span><span class="sxs-lookup"><span data-stu-id="b0165-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0165-118">Évaluer.</span><span class="sxs-lookup"><span data-stu-id="b0165-118">Index.</span></span> <span data-ttu-id="b0165-119">La valeur des auto-affiliations est-1, et pour les autres affiliations, elle augmente de manière séquentielle de 1 au sein de chaque &lt; principalID, affiliationId &gt; Bucket.</span><span class="sxs-lookup"><span data-stu-id="b0165-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0165-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="b0165-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="b0165-121">int, non null</span><span class="sxs-lookup"><span data-stu-id="b0165-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0165-p103">Principal qui a effectué la mise à jour la plus récente. Il s’agit généralement de 1, ce qui signifie Active Directory Sync.</span><span class="sxs-lookup"><span data-stu-id="b0165-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b0165-124">Keys</span><span class="sxs-lookup"><span data-stu-id="b0165-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0165-125">Colonnes</span><span class="sxs-lookup"><span data-stu-id="b0165-125">Columns</span></span></th>
<th><span data-ttu-id="b0165-126">Description</span><span class="sxs-lookup"><span data-stu-id="b0165-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0165-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="b0165-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b0165-128">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b0165-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0165-129">principalID</span><span class="sxs-lookup"><span data-stu-id="b0165-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="b0165-130">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b0165-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0165-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b0165-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b0165-132">Clé étrangère avec recherche dans la table tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b0165-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

