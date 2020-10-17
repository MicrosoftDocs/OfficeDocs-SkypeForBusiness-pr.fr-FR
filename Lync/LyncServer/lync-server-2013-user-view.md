---
title: 'Lync Server 2013 : affichage utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f978b6acaa1cdfdf6abf2d768c1fb679af260a63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530151"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="70ecf-102">Affichage utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70ecf-102">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70ecf-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="70ecf-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="70ecf-104">La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="70ecf-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="70ecf-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70ecf-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ecf-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="70ecf-106">Column</span></span></th>
<th><span data-ttu-id="70ecf-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="70ecf-107">Data Type</span></span></th>
<th><span data-ttu-id="70ecf-108">Détails</span><span class="sxs-lookup"><span data-stu-id="70ecf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ecf-109">UserId</span><span class="sxs-lookup"><span data-stu-id="70ecf-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="70ecf-110">int</span><span class="sxs-lookup"><span data-stu-id="70ecf-110">int</span></span></p></td>
<td><p><span data-ttu-id="70ecf-111">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70ecf-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ecf-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="70ecf-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="70ecf-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="70ecf-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="70ecf-114">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70ecf-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ecf-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="70ecf-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="70ecf-116">unique</span><span class="sxs-lookup"><span data-stu-id="70ecf-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="70ecf-117">Client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70ecf-117">Tenant of user.</span></span> <span data-ttu-id="70ecf-118">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="70ecf-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ecf-119">UriType</span><span class="sxs-lookup"><span data-stu-id="70ecf-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="70ecf-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="70ecf-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70ecf-121">Type de l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70ecf-121">Type of user URI.</span></span> <span data-ttu-id="70ecf-122">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="70ecf-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

