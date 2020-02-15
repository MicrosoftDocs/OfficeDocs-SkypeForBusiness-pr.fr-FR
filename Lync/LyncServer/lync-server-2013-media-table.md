---
title: 'Lync Server 2013 : table Media'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3d96a7d08a71b63c71c76617e78ebf1df605a52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="11a31-102">Table Media dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11a31-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11a31-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="11a31-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="11a31-p101">Chaque enregistrement représente un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="11a31-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11a31-p102">La table Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette table contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement lorsque le destinataire de la session accepte la session. EndTime signifie généralement l’heure de fin de cette session.</span><span class="sxs-lookup"><span data-stu-id="11a31-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11a31-110">Colonne</span><span class="sxs-lookup"><span data-stu-id="11a31-110">Column</span></span></th>
<th><span data-ttu-id="11a31-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="11a31-111">Data Type</span></span></th>
<th><span data-ttu-id="11a31-112">Clé/index</span><span class="sxs-lookup"><span data-stu-id="11a31-112">Key/Index</span></span></th>
<th><span data-ttu-id="11a31-113">Détails</span><span class="sxs-lookup"><span data-stu-id="11a31-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11a31-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="11a31-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11a31-115">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11a31-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="11a31-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="11a31-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="11a31-117">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="11a31-117">Time of session request.</span></span> <span data-ttu-id="11a31-118">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="11a31-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="11a31-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11a31-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11a31-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="11a31-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="11a31-121">int</span><span class="sxs-lookup"><span data-stu-id="11a31-121">int</span></span></p></td>
<td><p><span data-ttu-id="11a31-122">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="11a31-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="11a31-123">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="11a31-123">ID number to identify the session.</span></span> <span data-ttu-id="11a31-124">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="11a31-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="11a31-125">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11a31-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11a31-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="11a31-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="11a31-127">entier très petit</span><span class="sxs-lookup"><span data-stu-id="11a31-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="11a31-128">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="11a31-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="11a31-129">Numéro unique d’identification de ce type de média.</span><span class="sxs-lookup"><span data-stu-id="11a31-129">Unique number identifying this media type.</span></span> <span data-ttu-id="11a31-130">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialist-table.md">table médial dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11a31-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11a31-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="11a31-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11a31-132">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11a31-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="11a31-133">Primaire</span><span class="sxs-lookup"><span data-stu-id="11a31-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="11a31-p106">Heure d’envoi de la demande multimédia, et non pas heure réelle du début du média. <strong>StartTime</strong> inclut l’heure de configuration de la session.</span><span class="sxs-lookup"><span data-stu-id="11a31-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11a31-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="11a31-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11a31-137">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11a31-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11a31-138">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="11a31-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

