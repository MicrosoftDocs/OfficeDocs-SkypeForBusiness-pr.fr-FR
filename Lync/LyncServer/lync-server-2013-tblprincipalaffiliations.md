---
title: 'Lync Server 2013 : tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="28fa0-102">tblPrincipalAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28fa0-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28fa0-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="28fa0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="28fa0-104">tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances aux emplacements, y compris les groupes de sécurité des services de domaine Active Directory (AD FS) dans les conteneurs Active Directory, dans les domaines.</span><span class="sxs-lookup"><span data-stu-id="28fa0-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="28fa0-105">Celles</span><span class="sxs-lookup"><span data-stu-id="28fa0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28fa0-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="28fa0-106">Column</span></span></th>
<th><span data-ttu-id="28fa0-107">Type</span><span class="sxs-lookup"><span data-stu-id="28fa0-107">Type</span></span></th>
<th><span data-ttu-id="28fa0-108">Description</span><span class="sxs-lookup"><span data-stu-id="28fa0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28fa0-109">principalID</span><span class="sxs-lookup"><span data-stu-id="28fa0-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="28fa0-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="28fa0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="28fa0-111">ID du principal affilié.</span><span class="sxs-lookup"><span data-stu-id="28fa0-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fa0-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="28fa0-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="28fa0-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="28fa0-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="28fa0-114">ID de l’objet principal qui représente l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="28fa0-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="28fa0-115">Chaque identité (à l’exception des types d’utilisateur système) possède également une auto-affiliation.</span><span class="sxs-lookup"><span data-stu-id="28fa0-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fa0-116">index</span><span class="sxs-lookup"><span data-stu-id="28fa0-116">index</span></span></p></td>
<td><p><span data-ttu-id="28fa0-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="28fa0-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="28fa0-118">Index.</span><span class="sxs-lookup"><span data-stu-id="28fa0-118">Index.</span></span> <span data-ttu-id="28fa0-119">La valeur de auto-affiliations est-1, et pour les autres affiliations, elle augmente séquentiellement de 1 dans &lt;chaque principalID,&gt; compartiment affiliationId.</span><span class="sxs-lookup"><span data-stu-id="28fa0-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fa0-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="28fa0-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="28fa0-121">ent, non null</span><span class="sxs-lookup"><span data-stu-id="28fa0-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="28fa0-122">Principal ayant effectué la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="28fa0-122">Principal that did the latest update.</span></span> <span data-ttu-id="28fa0-123">Il s’agit généralement de la méthode de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28fa0-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="28fa0-124">Permettent</span><span class="sxs-lookup"><span data-stu-id="28fa0-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28fa0-125">Celles</span><span class="sxs-lookup"><span data-stu-id="28fa0-125">Columns</span></span></th>
<th><span data-ttu-id="28fa0-126">Description</span><span class="sxs-lookup"><span data-stu-id="28fa0-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28fa0-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="28fa0-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="28fa0-128">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="28fa0-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fa0-129">principalID</span><span class="sxs-lookup"><span data-stu-id="28fa0-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="28fa0-130">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="28fa0-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fa0-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="28fa0-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="28fa0-132">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="28fa0-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

