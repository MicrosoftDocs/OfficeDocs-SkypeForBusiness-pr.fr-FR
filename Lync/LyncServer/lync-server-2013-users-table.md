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
ms.openlocfilehash: 18d3afde02d93848c656a08617f08dcb55dc4a9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="31acd-102">Table users dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31acd-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31acd-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="31acd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="31acd-104">La table users est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="31acd-104">The Users table is a supporting table.</span></span> <span data-ttu-id="31acd-105">Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="31acd-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31acd-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="31acd-106">Column</span></span></th>
<th><span data-ttu-id="31acd-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="31acd-107">Data Type</span></span></th>
<th><span data-ttu-id="31acd-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="31acd-108">Key/Index</span></span></th>
<th><span data-ttu-id="31acd-109">Détails</span><span class="sxs-lookup"><span data-stu-id="31acd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31acd-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="31acd-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="31acd-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="31acd-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="31acd-112">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="31acd-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31acd-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="31acd-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="31acd-114">int</span><span class="sxs-lookup"><span data-stu-id="31acd-114">int</span></span></p></td>
<td><p><span data-ttu-id="31acd-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="31acd-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="31acd-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31acd-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31acd-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="31acd-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="31acd-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31acd-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="31acd-119">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31acd-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31acd-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="31acd-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="31acd-121">int</span><span class="sxs-lookup"><span data-stu-id="31acd-121">int</span></span></p></td>
<td><p><span data-ttu-id="31acd-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="31acd-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="31acd-123">ID de client de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31acd-123">This user’s Tenant ID.</span></span> <span data-ttu-id="31acd-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="31acd-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31acd-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="31acd-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="31acd-126">int</span><span class="sxs-lookup"><span data-stu-id="31acd-126">int</span></span></p></td>
<td><p><span data-ttu-id="31acd-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="31acd-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="31acd-128">Type d’URI de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31acd-128">This user’s URI type.</span></span> <span data-ttu-id="31acd-129">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="31acd-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

