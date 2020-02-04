---
title: 'Lync Server 2013 : Table User'
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="2a9b2-102">Table User dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a9b2-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a9b2-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2a9b2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2a9b2-104">La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2a9b2-105">Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a9b2-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2a9b2-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2a9b2-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2a9b2-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a9b2-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2a9b2-111">int</span><span class="sxs-lookup"><span data-stu-id="2a9b2-111">int</span></span></p></td>
<td><p><span data-ttu-id="2a9b2-112">Principal</span><span class="sxs-lookup"><span data-stu-id="2a9b2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2a9b2-113">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a9b2-114"><strong>SPAMMEUR</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="2a9b2-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2a9b2-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2a9b2-116">Différent</span><span class="sxs-lookup"><span data-stu-id="2a9b2-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="2a9b2-117">Chaîne d’URI.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a9b2-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="2a9b2-119">int</span><span class="sxs-lookup"><span data-stu-id="2a9b2-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a9b2-120">1 est un type d’URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="2a9b2-121">2 est l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="2a9b2-122">4 est un URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="2a9b2-123">8 est un URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a9b2-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2a9b2-125">int</span><span class="sxs-lookup"><span data-stu-id="2a9b2-125">int</span></span></p></td>
<td><p><span data-ttu-id="2a9b2-126">Externes</span><span class="sxs-lookup"><span data-stu-id="2a9b2-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a9b2-127">Client de l’utilisateur, référencé dans la table locataire.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a9b2-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2a9b2-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2a9b2-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a9b2-130">Horodatage le plus récent lorsque l’utilisateur avait un appel audio médiocre.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a9b2-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="2a9b2-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="2a9b2-132">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2a9b2-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a9b2-133">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="2a9b2-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

