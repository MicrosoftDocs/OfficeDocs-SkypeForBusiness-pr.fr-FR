---
title: 'Lync Server 2013 : table utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98a34028ebec126c8d5fc5ec838a22180ccb0fa7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="27997-102">Table user dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27997-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27997-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="27997-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="27997-p101">La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27997-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27997-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="27997-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="27997-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="27997-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="27997-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="27997-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="27997-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="27997-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27997-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="27997-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="27997-111">int</span><span class="sxs-lookup"><span data-stu-id="27997-111">int</span></span></p></td>
<td><p><span data-ttu-id="27997-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="27997-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="27997-113">Nombre unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27997-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27997-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="27997-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="27997-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27997-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="27997-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="27997-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="27997-117">Chaîne URI.</span><span class="sxs-lookup"><span data-stu-id="27997-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27997-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="27997-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="27997-119">int</span><span class="sxs-lookup"><span data-stu-id="27997-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27997-120">1 est type URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="27997-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="27997-121">2 est URI d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27997-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="27997-122">4 est URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="27997-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="27997-123">8 est URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="27997-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27997-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="27997-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="27997-125">int</span><span class="sxs-lookup"><span data-stu-id="27997-125">int</span></span></p></td>
<td><p><span data-ttu-id="27997-126">Etranger</span><span class="sxs-lookup"><span data-stu-id="27997-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="27997-127">Locataire de l’utilisateur, référencé depuis la table de locataires.</span><span class="sxs-lookup"><span data-stu-id="27997-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27997-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="27997-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27997-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="27997-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27997-130">Horodatage le plus récent du moment où l’utilisateur avait un appel de mauvaise qualité audio.</span><span class="sxs-lookup"><span data-stu-id="27997-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27997-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="27997-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="27997-132">DateHeure</span><span class="sxs-lookup"><span data-stu-id="27997-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27997-133">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="27997-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

