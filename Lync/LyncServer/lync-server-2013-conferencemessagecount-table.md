---
title: 'Lync Server 2013 : table ConferenceMessageCount'
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
ms.openlocfilehash: e13f45936f210085361624a0d884f507a88e0d35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="24f0b-102">Table ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24f0b-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24f0b-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="24f0b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="24f0b-104">Chaque enregistrement de cette table représente un utilisateur dans une conférence par messagerie instantanée et indique le nombre de messages envoyés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24f0b-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="24f0b-105">Chaque conférence est représentée par plusieurs enregistrements dans cette table ; un enregistrement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24f0b-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24f0b-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="24f0b-106">Column</span></span></th>
<th><span data-ttu-id="24f0b-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="24f0b-107">Data Type</span></span></th>
<th><span data-ttu-id="24f0b-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="24f0b-108">Key/Index</span></span></th>
<th><span data-ttu-id="24f0b-109">Détails</span><span class="sxs-lookup"><span data-stu-id="24f0b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24f0b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="24f0b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24f0b-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="24f0b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="24f0b-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="24f0b-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="24f0b-113">Heure de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="24f0b-113">Time of conference instance.</span></span> <span data-ttu-id="24f0b-114">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="24f0b-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="24f0b-115">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="24f0b-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24f0b-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="24f0b-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="24f0b-117">int</span><span class="sxs-lookup"><span data-stu-id="24f0b-117">int</span></span></p></td>
<td><p><span data-ttu-id="24f0b-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="24f0b-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="24f0b-119">Numéro d’identification de l’instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="24f0b-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="24f0b-120">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="24f0b-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="24f0b-121">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="24f0b-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24f0b-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="24f0b-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="24f0b-123">int</span><span class="sxs-lookup"><span data-stu-id="24f0b-123">int</span></span></p></td>
<td><p><span data-ttu-id="24f0b-124">Etranger</span><span class="sxs-lookup"><span data-stu-id="24f0b-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="24f0b-125">Numéro unique identifiant cet utilisateur, référencé à partir de la <a href="lync-server-2013-users-table.md">table users dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="24f0b-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24f0b-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="24f0b-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="24f0b-127">type</span><span class="sxs-lookup"><span data-stu-id="24f0b-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="24f0b-128">Nombre de messages envoyés par cet utilisateur au cours de cette conférence.</span><span class="sxs-lookup"><span data-stu-id="24f0b-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

