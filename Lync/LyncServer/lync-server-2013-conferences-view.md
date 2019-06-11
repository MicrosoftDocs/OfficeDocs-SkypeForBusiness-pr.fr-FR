---
title: 'Lync Server 2013: vue conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="794db-102">Affichage conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794db-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="794db-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="794db-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="794db-104">L’affichage conférences stocke les informations relatives aux conférences.</span><span class="sxs-lookup"><span data-stu-id="794db-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="794db-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="794db-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="794db-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="794db-106">Column</span></span></th>
<th><span data-ttu-id="794db-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="794db-107">Data Type</span></span></th>
<th><span data-ttu-id="794db-108">Détails</span><span class="sxs-lookup"><span data-stu-id="794db-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="794db-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="794db-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="794db-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="794db-111">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="794db-111">Time of session request.</span></span> <span data-ttu-id="794db-112">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="794db-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="794db-113">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="794db-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="794db-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="794db-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-115">int</span><span class="sxs-lookup"><span data-stu-id="794db-115">int</span></span></p></td>
<td><p><span data-ttu-id="794db-116">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="794db-116">ID number to identify the session.</span></span> <span data-ttu-id="794db-117">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="794db-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="794db-118">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="794db-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="794db-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="794db-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="794db-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="794db-121">URI de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="794db-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="794db-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="794db-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="794db-124">Type de l’URI de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-124">Type of the conference URI.</span></span> <span data-ttu-id="794db-125">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="794db-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="794db-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="794db-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-127">identificateur</span><span class="sxs-lookup"><span data-stu-id="794db-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="794db-128">Utilisé pour les conférences récurrentes.</span><span class="sxs-lookup"><span data-stu-id="794db-128">Used for recurring conferences.</span></span> <span data-ttu-id="794db-129">Chaque instance d’une conférence périodique a le même ConferenceUri qu’une autre ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="794db-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="794db-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="794db-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="794db-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="794db-132">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="794db-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="794db-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-134">DateHeure</span><span class="sxs-lookup"><span data-stu-id="794db-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="794db-135">Heure de fin de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="794db-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="794db-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="794db-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="794db-138">URI de l’utilisateur qui a organisé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="794db-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="794db-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="794db-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="794db-141">Type d’URI de l’utilisateur qui a organisé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="794db-142">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="794db-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="794db-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="794db-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="794db-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="794db-145">Client de l’utilisateur qui a organisé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="794db-146">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="794db-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="794db-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="794db-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="794db-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="794db-149">Nom de domaine complet du pool ayant hébergé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="794db-150"><strong>Indication</strong></span><span class="sxs-lookup"><span data-stu-id="794db-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="794db-151">type</span><span class="sxs-lookup"><span data-stu-id="794db-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="794db-152">Masque binaire qui contient les attributs de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="794db-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="794db-153">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="794db-153">Possible values are:</span></span></p>
<p><span data-ttu-id="794db-154">0X01 – transaction synthétique</span><span class="sxs-lookup"><span data-stu-id="794db-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

