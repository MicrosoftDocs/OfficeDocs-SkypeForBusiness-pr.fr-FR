---
title: 'Lync Server 2013 : vue conférences'
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
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="6cf63-102">Affichage conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cf63-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cf63-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6cf63-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6cf63-104">L’affichage conférences stocke les informations relatives aux conférences.</span><span class="sxs-lookup"><span data-stu-id="6cf63-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="6cf63-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cf63-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cf63-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="6cf63-106">Column</span></span></th>
<th><span data-ttu-id="6cf63-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="6cf63-107">Data Type</span></span></th>
<th><span data-ttu-id="6cf63-108">Détails</span><span class="sxs-lookup"><span data-stu-id="6cf63-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cf63-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="6cf63-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="6cf63-111">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="6cf63-111">Time of session request.</span></span> <span data-ttu-id="6cf63-112">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="6cf63-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="6cf63-113">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6cf63-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf63-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-115">int</span><span class="sxs-lookup"><span data-stu-id="6cf63-115">int</span></span></p></td>
<td><p><span data-ttu-id="6cf63-116">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="6cf63-116">ID number to identify the session.</span></span> <span data-ttu-id="6cf63-117">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="6cf63-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="6cf63-118">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6cf63-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cf63-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6cf63-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6cf63-121">URI de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf63-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6cf63-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6cf63-124">Type de l’URI de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-124">Type of the conference URI.</span></span> <span data-ttu-id="6cf63-125">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6cf63-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cf63-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-127">identificateur</span><span class="sxs-lookup"><span data-stu-id="6cf63-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6cf63-128">Utilisé pour les conférences récurrentes.</span><span class="sxs-lookup"><span data-stu-id="6cf63-128">Used for recurring conferences.</span></span> <span data-ttu-id="6cf63-129">Chaque instance d’une conférence périodique a le même ConferenceUri qu’une autre ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="6cf63-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf63-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="6cf63-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="6cf63-132">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cf63-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-134">DateHeure</span><span class="sxs-lookup"><span data-stu-id="6cf63-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="6cf63-135">Heure de fin de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf63-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6cf63-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6cf63-138">URI de l’utilisateur qui a organisé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cf63-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6cf63-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6cf63-141">Type d’URI de l’utilisateur qui a organisé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="6cf63-142">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6cf63-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf63-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6cf63-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6cf63-145">Client de l’utilisateur qui a organisé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="6cf63-146">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6cf63-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cf63-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6cf63-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6cf63-149">Nom de domaine complet du pool ayant hébergé la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf63-150"><strong>Indication</strong></span><span class="sxs-lookup"><span data-stu-id="6cf63-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="6cf63-151">type</span><span class="sxs-lookup"><span data-stu-id="6cf63-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="6cf63-152">Masque binaire qui contient les attributs de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6cf63-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="6cf63-153">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="6cf63-153">Possible values are:</span></span></p>
<p><span data-ttu-id="6cf63-154">0X01 – transaction synthétique</span><span class="sxs-lookup"><span data-stu-id="6cf63-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

