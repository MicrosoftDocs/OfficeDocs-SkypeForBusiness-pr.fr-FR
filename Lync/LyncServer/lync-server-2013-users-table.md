---
title: 'Lync Server 2013 : tableau utilisateurs'
description: 'Lync Server 2013 : table users.'
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
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548630"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="908c7-103">Table users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="908c7-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="908c7-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="908c7-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="908c7-105">La table users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="908c7-105">The Users table is a supporting table.</span></span> <span data-ttu-id="908c7-106">Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="908c7-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="908c7-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="908c7-107">Column</span></span></th>
<th><span data-ttu-id="908c7-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="908c7-108">Data Type</span></span></th>
<th><span data-ttu-id="908c7-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="908c7-109">Key/Index</span></span></th>
<th><span data-ttu-id="908c7-110">Détails</span><span class="sxs-lookup"><span data-stu-id="908c7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="908c7-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="908c7-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="908c7-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="908c7-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="908c7-113">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="908c7-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="908c7-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="908c7-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="908c7-115">int</span><span class="sxs-lookup"><span data-stu-id="908c7-115">int</span></span></p></td>
<td><p><span data-ttu-id="908c7-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="908c7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="908c7-117">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="908c7-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="908c7-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="908c7-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="908c7-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="908c7-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="908c7-120">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="908c7-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="908c7-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="908c7-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="908c7-122">int</span><span class="sxs-lookup"><span data-stu-id="908c7-122">int</span></span></p></td>
<td><p><span data-ttu-id="908c7-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="908c7-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="908c7-124">ID de client de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="908c7-124">This user’s Tenant ID.</span></span> <span data-ttu-id="908c7-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="908c7-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="908c7-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="908c7-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="908c7-127">int</span><span class="sxs-lookup"><span data-stu-id="908c7-127">int</span></span></p></td>
<td><p><span data-ttu-id="908c7-128">Etranger</span><span class="sxs-lookup"><span data-stu-id="908c7-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="908c7-129">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="908c7-129">This user’s URI type.</span></span> <span data-ttu-id="908c7-130">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="908c7-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

