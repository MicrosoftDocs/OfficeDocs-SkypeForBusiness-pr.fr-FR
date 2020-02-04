---
title: 'Lync Server 2013 : Table ConferenceMessageCount'
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
ms.openlocfilehash: 426ae4abca9f91fcabaedfb5a363703523d6aa94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="adc0d-102">Table ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adc0d-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adc0d-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="adc0d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="adc0d-104">Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adc0d-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="adc0d-105">Chaque conférence est représentée par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adc0d-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc0d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="adc0d-106">Column</span></span></th>
<th><span data-ttu-id="adc0d-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="adc0d-107">Data Type</span></span></th>
<th><span data-ttu-id="adc0d-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="adc0d-108">Key/Index</span></span></th>
<th><span data-ttu-id="adc0d-109">Détails</span><span class="sxs-lookup"><span data-stu-id="adc0d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc0d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="adc0d-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="adc0d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="adc0d-112">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="adc0d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="adc0d-113">Durée de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="adc0d-113">Time of conference instance.</span></span> <span data-ttu-id="adc0d-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="adc0d-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="adc0d-115">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="adc0d-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc0d-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="adc0d-117">int</span><span class="sxs-lookup"><span data-stu-id="adc0d-117">int</span></span></p></td>
<td><p><span data-ttu-id="adc0d-118">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="adc0d-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="adc0d-119">Numéro d’identification pour identifier l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="adc0d-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="adc0d-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="adc0d-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="adc0d-121">Pour plus d’informations, voir le <a href="lync-server-2013-conferences-table.md">tableau conférences dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="adc0d-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc0d-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="adc0d-123">int</span><span class="sxs-lookup"><span data-stu-id="adc0d-123">int</span></span></p></td>
<td><p><span data-ttu-id="adc0d-124">Externes</span><span class="sxs-lookup"><span data-stu-id="adc0d-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="adc0d-125">Numéro unique identifiant cet utilisateur, référencé dans la <a href="lync-server-2013-users-table.md">table utilisateurs de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="adc0d-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc0d-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="adc0d-127">type</span><span class="sxs-lookup"><span data-stu-id="adc0d-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="adc0d-128">Nombre de messages envoyés par cet utilisateur au cours de cette conférence.</span><span class="sxs-lookup"><span data-stu-id="adc0d-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

