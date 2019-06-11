---
title: 'Lync Server 2013 : Table Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6acc63c2271b5ab58e168d0f0f662c6cb3653aac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="3b64d-102">Table Users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b64d-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b64d-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3b64d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3b64d-104">La table users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3b64d-104">The Users table is a supporting table.</span></span> <span data-ttu-id="3b64d-105">Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3b64d-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b64d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="3b64d-106">Column</span></span></th>
<th><span data-ttu-id="3b64d-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="3b64d-107">Data Type</span></span></th>
<th><span data-ttu-id="3b64d-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="3b64d-108">Key/Index</span></span></th>
<th><span data-ttu-id="3b64d-109">Détails</span><span class="sxs-lookup"><span data-stu-id="3b64d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b64d-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3b64d-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3b64d-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3b64d-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b64d-112">Horodatage pour un usage interne.</span><span class="sxs-lookup"><span data-stu-id="3b64d-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b64d-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3b64d-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3b64d-114">int</span><span class="sxs-lookup"><span data-stu-id="3b64d-114">int</span></span></p></td>
<td><p><span data-ttu-id="3b64d-115">Principal</span><span class="sxs-lookup"><span data-stu-id="3b64d-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="3b64d-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b64d-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b64d-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="3b64d-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3b64d-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3b64d-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3b64d-119">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b64d-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b64d-120"><strong>IDClient</strong></span><span class="sxs-lookup"><span data-stu-id="3b64d-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="3b64d-121">int</span><span class="sxs-lookup"><span data-stu-id="3b64d-121">int</span></span></p></td>
<td><p><span data-ttu-id="3b64d-122">Externes</span><span class="sxs-lookup"><span data-stu-id="3b64d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3b64d-123">ID de client de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b64d-123">This user’s Tenant ID.</span></span> <span data-ttu-id="3b64d-124">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b64d-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b64d-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3b64d-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3b64d-126">int</span><span class="sxs-lookup"><span data-stu-id="3b64d-126">int</span></span></p></td>
<td><p><span data-ttu-id="3b64d-127">Externes</span><span class="sxs-lookup"><span data-stu-id="3b64d-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3b64d-128">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b64d-128">This user’s URI type.</span></span> <span data-ttu-id="3b64d-129">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3b64d-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

