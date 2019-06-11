---
title: 'Lync Server 2013: affichage UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="54e8a-102">Affichage UserAgent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54e8a-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54e8a-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="54e8a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="54e8a-104">L’affichage UserAgent stocke les informations sur les agents utilisateur impliqués dans les sessions qui contiennent des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="54e8a-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="54e8a-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54e8a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54e8a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="54e8a-106">Column</span></span></th>
<th><span data-ttu-id="54e8a-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="54e8a-107">Data Type</span></span></th>
<th><span data-ttu-id="54e8a-108">Détails</span><span class="sxs-lookup"><span data-stu-id="54e8a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54e8a-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="54e8a-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="54e8a-110">int</span><span class="sxs-lookup"><span data-stu-id="54e8a-110">int</span></span></p></td>
<td><p><span data-ttu-id="54e8a-111">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="54e8a-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e8a-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="54e8a-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="54e8a-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e8a-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54e8a-114">Chaîne de l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="54e8a-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54e8a-115">UAType</span><span class="sxs-lookup"><span data-stu-id="54e8a-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="54e8a-116">type</span><span class="sxs-lookup"><span data-stu-id="54e8a-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="54e8a-117">Type d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="54e8a-117">Type of user agent.</span></span> <span data-ttu-id="54e8a-118">Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54e8a-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54e8a-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="54e8a-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="54e8a-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="54e8a-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="54e8a-121">Catégorie à laquelle l’agent utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="54e8a-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="54e8a-122">Par exemple, l’agent utilisateur Conferencing_Attendant_ 1.0 appartient au CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="54e8a-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

