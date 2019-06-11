---
title: 'Lync Server 2013 : Table Media'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8b3aaff56e782307f3146fdcee7d4410340198
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="b6d9c-102">Table Media dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6d9c-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6d9c-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b6d9c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b6d9c-104">Chaque enregistrement représente un type de média utilisé dans une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="b6d9c-105">Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6d9c-106">La table multimédia ne doit pas être utilisée pour calculer la durée du média pour une session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="b6d9c-107">Ce tableau contient les détails de signalisation d’échange de médias dans une session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="b6d9c-108">L’échange de média est effectué par la demande d’invitation, et la durée de StartTime indique l’heure d’envoi de l’invitation. La durée d’invitation ne correspond pas nécessairement à l’heure de début du média, car le contenu multimédia ne démarre qu’après que la session de la session a été acceptée.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="b6d9c-109">Le heure_fin correspond généralement à l’heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="b6d9c-110">Colonne</span><span class="sxs-lookup"><span data-stu-id="b6d9c-110">Column</span></span></th>
<th><span data-ttu-id="b6d9c-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="b6d9c-111">Data Type</span></span></th>
<th><span data-ttu-id="b6d9c-112">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="b6d9c-112">Key/Index</span></span></th>
<th><span data-ttu-id="b6d9c-113">Détails</span><span class="sxs-lookup"><span data-stu-id="b6d9c-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6d9c-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6d9c-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6d9c-115">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b6d9c-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-116">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b6d9c-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-117">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-117">Time of session request.</span></span> <span data-ttu-id="b6d9c-118">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b6d9c-119">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b6d9c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6d9c-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b6d9c-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b6d9c-121">int</span><span class="sxs-lookup"><span data-stu-id="b6d9c-121">int</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-122">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b6d9c-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-123">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-123">ID number to identify the session.</span></span> <span data-ttu-id="b6d9c-124">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b6d9c-125">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b6d9c-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6d9c-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="b6d9c-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6d9c-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6d9c-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-128">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="b6d9c-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-129">Numéro unique identifiant ce type de média.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-129">Unique number identifying this media type.</span></span> <span data-ttu-id="b6d9c-130">Pour plus d’informations, reportez-vous <a href="lync-server-2013-medialist-table.md">à la table de médiane dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b6d9c-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6d9c-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6d9c-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6d9c-132">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b6d9c-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-133">Principal</span><span class="sxs-lookup"><span data-stu-id="b6d9c-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6d9c-134">Il s’agit du temps d’envoi d’une demande de média et non de l’heure de début réelle du média.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="b6d9c-135"><strong>StartTime</strong> inclut le temps de configuration de la session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6d9c-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6d9c-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6d9c-137">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b6d9c-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6d9c-138">Il s’agit de l’heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="b6d9c-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

