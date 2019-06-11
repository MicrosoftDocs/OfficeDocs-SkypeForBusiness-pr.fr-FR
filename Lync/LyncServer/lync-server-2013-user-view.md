---
title: 'Vue utilisateur de Lync Server 2013:'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c22bdfbf758545418a821edaba5d8aaf447b87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="2f017-102">Affichage utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f017-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f017-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2f017-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2f017-104">L’affichage utilisateur stocke les informations sur les utilisateurs qui ont participé à des appels ou des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2f017-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="2f017-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f017-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f017-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="2f017-106">Column</span></span></th>
<th><span data-ttu-id="2f017-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="2f017-107">Data Type</span></span></th>
<th><span data-ttu-id="2f017-108">Détails</span><span class="sxs-lookup"><span data-stu-id="2f017-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f017-109">UserId</span><span class="sxs-lookup"><span data-stu-id="2f017-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="2f017-110">int</span><span class="sxs-lookup"><span data-stu-id="2f017-110">int</span></span></p></td>
<td><p><span data-ttu-id="2f017-111">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f017-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f017-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="2f017-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="2f017-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2f017-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2f017-114">URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f017-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f017-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="2f017-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="2f017-116">identificateur</span><span class="sxs-lookup"><span data-stu-id="2f017-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2f017-117">Client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f017-117">Tenant of user.</span></span> <span data-ttu-id="2f017-118">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2f017-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f017-119">UriType</span><span class="sxs-lookup"><span data-stu-id="2f017-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="2f017-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2f017-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f017-121">Type d’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f017-121">Type of user URI.</span></span> <span data-ttu-id="2f017-122">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2f017-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

