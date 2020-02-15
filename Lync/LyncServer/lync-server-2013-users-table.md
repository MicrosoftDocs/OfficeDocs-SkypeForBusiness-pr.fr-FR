---
title: 'Lync Server 2013 : tableau utilisateurs'
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
ms.openlocfilehash: 67663afbd9e5b61b1b24478e003db91c5be511e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="104d6-102">Table users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="104d6-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="104d6-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="104d6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="104d6-104">La table users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="104d6-104">The Users table is a supporting table.</span></span> <span data-ttu-id="104d6-105">Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="104d6-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="104d6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="104d6-106">Column</span></span></th>
<th><span data-ttu-id="104d6-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="104d6-107">Data Type</span></span></th>
<th><span data-ttu-id="104d6-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="104d6-108">Key/Index</span></span></th>
<th><span data-ttu-id="104d6-109">Détails</span><span class="sxs-lookup"><span data-stu-id="104d6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="104d6-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="104d6-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="104d6-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="104d6-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="104d6-112">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="104d6-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="104d6-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="104d6-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="104d6-114">int</span><span class="sxs-lookup"><span data-stu-id="104d6-114">int</span></span></p></td>
<td><p><span data-ttu-id="104d6-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="104d6-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="104d6-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="104d6-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="104d6-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="104d6-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="104d6-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="104d6-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="104d6-119">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="104d6-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="104d6-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="104d6-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="104d6-121">int</span><span class="sxs-lookup"><span data-stu-id="104d6-121">int</span></span></p></td>
<td><p><span data-ttu-id="104d6-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="104d6-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="104d6-123">ID de client de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="104d6-123">This user’s Tenant ID.</span></span> <span data-ttu-id="104d6-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="104d6-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="104d6-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="104d6-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="104d6-126">int</span><span class="sxs-lookup"><span data-stu-id="104d6-126">int</span></span></p></td>
<td><p><span data-ttu-id="104d6-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="104d6-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="104d6-128">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="104d6-128">This user’s URI type.</span></span> <span data-ttu-id="104d6-129">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="104d6-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

