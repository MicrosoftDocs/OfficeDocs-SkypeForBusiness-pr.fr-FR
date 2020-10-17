---
title: 'Lync Server 2013 : vue UserAgent'
description: 'Lync Server 2013 : vue UserAgent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9fc5ef2ec01b50f3714dca3690d0844286baaef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558860"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="3aac1-103">Vue UserAgent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3aac1-103">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aac1-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3aac1-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3aac1-105">L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3aac1-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="3aac1-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3aac1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3aac1-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="3aac1-107">Column</span></span></th>
<th><span data-ttu-id="3aac1-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="3aac1-108">Data Type</span></span></th>
<th><span data-ttu-id="3aac1-109">Détails</span><span class="sxs-lookup"><span data-stu-id="3aac1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3aac1-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="3aac1-110">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="3aac1-111">int</span><span class="sxs-lookup"><span data-stu-id="3aac1-111">int</span></span></p></td>
<td><p><span data-ttu-id="3aac1-112">Numéro unique qui identifie cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3aac1-112">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aac1-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="3aac1-113">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="3aac1-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aac1-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aac1-115">Chaîne d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3aac1-115">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aac1-116">UAType</span><span class="sxs-lookup"><span data-stu-id="3aac1-116">UAType</span></span></p></td>
<td><p><span data-ttu-id="3aac1-117">type</span><span class="sxs-lookup"><span data-stu-id="3aac1-117">smallint</span></span></p></td>
<td><p><span data-ttu-id="3aac1-118">Type d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3aac1-118">Type of user agent.</span></span> <span data-ttu-id="3aac1-119">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragent-table.md">table UserAgent dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3aac1-119">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aac1-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="3aac1-120">UACategory</span></span></p></td>
<td><p><span data-ttu-id="3aac1-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3aac1-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3aac1-p103">Catégorie à laquelle appartient l’agent utilisateur. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient au standard automatique de conférence (CAA) UACategory.</span><span class="sxs-lookup"><span data-stu-id="3aac1-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

