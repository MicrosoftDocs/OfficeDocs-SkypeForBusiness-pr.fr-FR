---
title: 'Lync Server 2013 : affichage des conférences'
description: 'Lync Server 2013 : affichage des conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561580"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="11df4-103">Vue des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11df4-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11df4-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="11df4-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="11df4-105">L’affichage des conférences fournit des informations relatives aux conférences.</span><span class="sxs-lookup"><span data-stu-id="11df4-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="11df4-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11df4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11df4-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="11df4-107">Column</span></span></th>
<th><span data-ttu-id="11df4-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="11df4-108">Data Type</span></span></th>
<th><span data-ttu-id="11df4-109">Détails</span><span class="sxs-lookup"><span data-stu-id="11df4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11df4-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11df4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="11df4-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="11df4-112">Time of session request.</span></span> <span data-ttu-id="11df4-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="11df4-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="11df4-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11df4-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11df4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-116">int</span><span class="sxs-lookup"><span data-stu-id="11df4-116">int</span></span></p></td>
<td><p><span data-ttu-id="11df4-117">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="11df4-117">ID number to identify the session.</span></span> <span data-ttu-id="11df4-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="11df4-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="11df4-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11df4-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11df4-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="11df4-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="11df4-122">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11df4-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11df4-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11df4-125">Type de l’URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-125">Type of the conference URI.</span></span> <span data-ttu-id="11df4-126">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11df4-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11df4-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-128">unique</span><span class="sxs-lookup"><span data-stu-id="11df4-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="11df4-p105">Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceUri, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="11df4-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11df4-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-132">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11df4-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="11df4-133">Heure de début de la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11df4-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-135">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11df4-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="11df4-136">Heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11df4-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="11df4-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="11df4-139">URI de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11df4-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11df4-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11df4-142">Type de l’URI de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="11df4-143">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11df4-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11df4-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11df4-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11df4-146">Locataire de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="11df4-147">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11df4-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11df4-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11df4-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11df4-150">Nom de domaine complet du pool ayant hébergé la conférence.</span><span class="sxs-lookup"><span data-stu-id="11df4-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11df4-151"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="11df4-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="11df4-152">type</span><span class="sxs-lookup"><span data-stu-id="11df4-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="11df4-p108">Masque de bits qui contient les attributs de la conférence. Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="11df4-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="11df4-155">0X01 – Synthetic Transaction</span><span class="sxs-lookup"><span data-stu-id="11df4-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

