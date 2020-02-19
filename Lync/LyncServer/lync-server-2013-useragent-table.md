---
title: 'Lync Server 2013 : table UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 041db946d80226f626b7248f604f1b3fa00a7ffc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="32860-102">Table UserAgent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32860-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32860-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="32860-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="32860-104">La table UserAgent est une table de prise en charge qui stocke la liste des différents agents utilisateurs qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="32860-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="32860-105">Chaque enregistrement de la table représente un agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="32860-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32860-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="32860-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="32860-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="32860-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="32860-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="32860-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="32860-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="32860-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32860-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="32860-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="32860-111">int</span><span class="sxs-lookup"><span data-stu-id="32860-111">int</span></span></p></td>
<td><p><span data-ttu-id="32860-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="32860-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="32860-113">Numéro unique qui identifie cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32860-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32860-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="32860-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="32860-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32860-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32860-116">Uniques</span><span class="sxs-lookup"><span data-stu-id="32860-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="32860-117">Chaîne de l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32860-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32860-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="32860-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="32860-119">type</span><span class="sxs-lookup"><span data-stu-id="32860-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="32860-120">1 est un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="32860-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="32860-121">2 est un serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="32860-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="32860-122">4 est Lync.</span><span class="sxs-lookup"><span data-stu-id="32860-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="32860-123">8 est un téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="32860-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="32860-124">16 est la console Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="32860-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="32860-125">32 est l’outil de validation du déploiement (DVT).</span><span class="sxs-lookup"><span data-stu-id="32860-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="32860-126">64 est Lync sur les ordinateurs Macintosh.</span><span class="sxs-lookup"><span data-stu-id="32860-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="32860-127">128 est Office Communications Server 2007 R2 attendant.</span><span class="sxs-lookup"><span data-stu-id="32860-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="32860-128">256 est le service d’annonce de conférence.</span><span class="sxs-lookup"><span data-stu-id="32860-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="32860-129">512 est le standard automatique de conférence.</span><span class="sxs-lookup"><span data-stu-id="32860-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="32860-130">1024 est une application Response Group.</span><span class="sxs-lookup"><span data-stu-id="32860-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="32860-131">2048 est en dehors du contrôle vocal.</span><span class="sxs-lookup"><span data-stu-id="32860-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

