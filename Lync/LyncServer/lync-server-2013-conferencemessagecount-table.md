---
title: 'Lync Server 2013 : table ConferenceMessageCount'
description: 'Lync Server 2013 : table ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561620"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="b3e67-103">Table ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3e67-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3e67-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b3e67-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b3e67-105">Chaque enregistrement de cette table représente un utilisateur dans une conférence par messagerie instantanée et indique le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3e67-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="b3e67-106">Chaque conférence est représentée par plusieurs enregistrements dans cette table ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3e67-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3e67-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="b3e67-107">Column</span></span></th>
<th><span data-ttu-id="b3e67-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="b3e67-108">Data Type</span></span></th>
<th><span data-ttu-id="b3e67-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="b3e67-109">Key/Index</span></span></th>
<th><span data-ttu-id="b3e67-110">Détails</span><span class="sxs-lookup"><span data-stu-id="b3e67-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3e67-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3e67-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e67-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b3e67-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3e67-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b3e67-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b3e67-114">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b3e67-114">Time of conference instance.</span></span> <span data-ttu-id="b3e67-115">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b3e67-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b3e67-116">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b3e67-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e67-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3e67-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e67-118">int</span><span class="sxs-lookup"><span data-stu-id="b3e67-118">int</span></span></p></td>
<td><p><span data-ttu-id="b3e67-119">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="b3e67-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b3e67-120">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="b3e67-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="b3e67-121">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b3e67-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="b3e67-122">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b3e67-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e67-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="b3e67-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e67-124">int</span><span class="sxs-lookup"><span data-stu-id="b3e67-124">int</span></span></p></td>
<td><p><span data-ttu-id="b3e67-125">Etranger</span><span class="sxs-lookup"><span data-stu-id="b3e67-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b3e67-126">Numéro unique identifiant cet utilisateur, référencé à partir de la <a href="lync-server-2013-users-table.md">table users dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b3e67-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e67-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b3e67-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e67-128">type</span><span class="sxs-lookup"><span data-stu-id="b3e67-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3e67-129">Nombre de messages envoyés par cet utilisateur au cours de cette conférence.</span><span class="sxs-lookup"><span data-stu-id="b3e67-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

