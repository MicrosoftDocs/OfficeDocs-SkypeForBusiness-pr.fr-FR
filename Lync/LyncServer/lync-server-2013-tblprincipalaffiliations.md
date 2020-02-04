---
title: 'Lync Server 2013 : tblPrincipalAffiliations'
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
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="81d66-102">tblPrincipalAffiliations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81d66-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d66-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="81d66-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="81d66-104">tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances aux emplacements, y compris les groupes de sécurité des services de domaine Active Directory (AD FS) dans les conteneurs Active Directory, dans les domaines.</span><span class="sxs-lookup"><span data-stu-id="81d66-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="81d66-105">Celles</span><span class="sxs-lookup"><span data-stu-id="81d66-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d66-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="81d66-106">Column</span></span></th>
<th><span data-ttu-id="81d66-107">Type</span><span class="sxs-lookup"><span data-stu-id="81d66-107">Type</span></span></th>
<th><span data-ttu-id="81d66-108">Description</span><span class="sxs-lookup"><span data-stu-id="81d66-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d66-109">principalID</span><span class="sxs-lookup"><span data-stu-id="81d66-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="81d66-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="81d66-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d66-111">ID du principal affilié.</span><span class="sxs-lookup"><span data-stu-id="81d66-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d66-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="81d66-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="81d66-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="81d66-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d66-114">ID de l’objet principal qui représente l’affiliation.</span><span class="sxs-lookup"><span data-stu-id="81d66-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="81d66-115">Chaque identité (à l’exception des types d’utilisateur système) possède également une auto-affiliation.</span><span class="sxs-lookup"><span data-stu-id="81d66-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d66-116">index</span><span class="sxs-lookup"><span data-stu-id="81d66-116">index</span></span></p></td>
<td><p><span data-ttu-id="81d66-117">ent, non null</span><span class="sxs-lookup"><span data-stu-id="81d66-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d66-118">Index.</span><span class="sxs-lookup"><span data-stu-id="81d66-118">Index.</span></span> <span data-ttu-id="81d66-119">La valeur de auto-affiliations est-1, et pour les autres affiliations, elle augmente séquentiellement de 1 dans &lt;chaque principalID,&gt; compartiment affiliationId.</span><span class="sxs-lookup"><span data-stu-id="81d66-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d66-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="81d66-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="81d66-121">ent, non null</span><span class="sxs-lookup"><span data-stu-id="81d66-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d66-122">Principal ayant effectué la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="81d66-122">Principal that did the latest update.</span></span> <span data-ttu-id="81d66-123">Il s’agit généralement de la méthode de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81d66-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="81d66-124">Permettent</span><span class="sxs-lookup"><span data-stu-id="81d66-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d66-125">Celles</span><span class="sxs-lookup"><span data-stu-id="81d66-125">Columns</span></span></th>
<th><span data-ttu-id="81d66-126">Description</span><span class="sxs-lookup"><span data-stu-id="81d66-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d66-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="81d66-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="81d66-128">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="81d66-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d66-129">principalID</span><span class="sxs-lookup"><span data-stu-id="81d66-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="81d66-130">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="81d66-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d66-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="81d66-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="81d66-132">Clé étrangère avec recherche dans la table tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="81d66-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

