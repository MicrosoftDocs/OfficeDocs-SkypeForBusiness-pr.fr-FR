---
title: 'Lync Server 2013 : Table Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="e4c84-102">Table Users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c84-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4c84-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e4c84-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e4c84-104">La table users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e4c84-104">The Users table is a supporting table.</span></span> <span data-ttu-id="e4c84-105">Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e4c84-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4c84-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e4c84-106">Column</span></span></th>
<th><span data-ttu-id="e4c84-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="e4c84-107">Data Type</span></span></th>
<th><span data-ttu-id="e4c84-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="e4c84-108">Key/Index</span></span></th>
<th><span data-ttu-id="e4c84-109">Détails</span><span class="sxs-lookup"><span data-stu-id="e4c84-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4c84-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e4c84-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e4c84-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e4c84-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4c84-112">Horodatage pour un usage interne.</span><span class="sxs-lookup"><span data-stu-id="e4c84-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c84-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e4c84-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e4c84-114">int</span><span class="sxs-lookup"><span data-stu-id="e4c84-114">int</span></span></p></td>
<td><p><span data-ttu-id="e4c84-115">Principal</span><span class="sxs-lookup"><span data-stu-id="e4c84-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4c84-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e4c84-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c84-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e4c84-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e4c84-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e4c84-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4c84-119">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e4c84-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c84-120"><strong>IDClient</strong></span><span class="sxs-lookup"><span data-stu-id="e4c84-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="e4c84-121">int</span><span class="sxs-lookup"><span data-stu-id="e4c84-121">int</span></span></p></td>
<td><p><span data-ttu-id="e4c84-122">Externes</span><span class="sxs-lookup"><span data-stu-id="e4c84-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e4c84-123">ID de client de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e4c84-123">This user’s Tenant ID.</span></span> <span data-ttu-id="e4c84-124">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e4c84-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c84-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e4c84-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e4c84-126">int</span><span class="sxs-lookup"><span data-stu-id="e4c84-126">int</span></span></p></td>
<td><p><span data-ttu-id="e4c84-127">Externes</span><span class="sxs-lookup"><span data-stu-id="e4c84-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e4c84-128">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e4c84-128">This user’s URI type.</span></span> <span data-ttu-id="e4c84-129">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e4c84-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

