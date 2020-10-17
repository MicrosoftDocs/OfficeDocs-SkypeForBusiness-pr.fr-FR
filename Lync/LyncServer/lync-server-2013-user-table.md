---
title: 'Lync Server 2013 : table utilisateur'
description: 'Lync Server 2013 : table utilisateur.'
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
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558900"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="0718c-103">Table user dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0718c-103">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0718c-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0718c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0718c-p101">La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0718c-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0718c-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0718c-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0718c-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0718c-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0718c-111"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-111"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0718c-112">int</span><span class="sxs-lookup"><span data-stu-id="0718c-112">int</span></span></p></td>
<td><p><span data-ttu-id="0718c-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="0718c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="0718c-114">Nombre unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0718c-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0718c-115"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-115"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0718c-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0718c-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0718c-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="0718c-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="0718c-118">Chaîne URI.</span><span class="sxs-lookup"><span data-stu-id="0718c-118">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0718c-119"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-119"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="0718c-120">int</span><span class="sxs-lookup"><span data-stu-id="0718c-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0718c-121">1 est type URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="0718c-121">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="0718c-122">2 est URI d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0718c-122">2 is user URI.</span></span></p>
<p><span data-ttu-id="0718c-123">4 est URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="0718c-123">4 is conference URI.</span></span></p>
<p><span data-ttu-id="0718c-124">8 est URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="0718c-124">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0718c-125"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-125"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0718c-126">int</span><span class="sxs-lookup"><span data-stu-id="0718c-126">int</span></span></p></td>
<td><p><span data-ttu-id="0718c-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="0718c-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0718c-128">Locataire de l’utilisateur, référencé depuis la table de locataires.</span><span class="sxs-lookup"><span data-stu-id="0718c-128">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0718c-129"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-129"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0718c-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0718c-130">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0718c-131">Horodatage le plus récent du moment où l’utilisateur avait un appel de mauvaise qualité audio.</span><span class="sxs-lookup"><span data-stu-id="0718c-131">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0718c-132"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="0718c-132"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="0718c-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0718c-133">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0718c-134">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="0718c-134">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

