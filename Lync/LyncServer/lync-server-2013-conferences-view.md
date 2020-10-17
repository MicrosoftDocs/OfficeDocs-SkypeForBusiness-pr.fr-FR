---
title: 'Lync Server 2013 : affichage des conférences'
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
ms.openlocfilehash: c5412f57c2dc355b7063faaf6c50eda31b9240bc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529221"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="c89df-102">Vue des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c89df-102">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c89df-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c89df-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c89df-104">L’affichage des conférences fournit des informations relatives aux conférences.</span><span class="sxs-lookup"><span data-stu-id="c89df-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="c89df-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c89df-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c89df-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="c89df-106">Column</span></span></th>
<th><span data-ttu-id="c89df-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="c89df-107">Data Type</span></span></th>
<th><span data-ttu-id="c89df-108">Détails</span><span class="sxs-lookup"><span data-stu-id="c89df-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c89df-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c89df-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c89df-111">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="c89df-111">Time of session request.</span></span> <span data-ttu-id="c89df-112">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="c89df-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c89df-113">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c89df-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89df-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-115">int</span><span class="sxs-lookup"><span data-stu-id="c89df-115">int</span></span></p></td>
<td><p><span data-ttu-id="c89df-116">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="c89df-116">ID number to identify the session.</span></span> <span data-ttu-id="c89df-117">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="c89df-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c89df-118">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c89df-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89df-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c89df-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c89df-121">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89df-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c89df-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c89df-124">Type de l’URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-124">Type of the conference URI.</span></span> <span data-ttu-id="c89df-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c89df-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89df-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-127">unique</span><span class="sxs-lookup"><span data-stu-id="c89df-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c89df-p105">Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceUri, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="c89df-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89df-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c89df-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="c89df-132">Heure de début de la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89df-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-134">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c89df-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="c89df-135">Heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89df-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c89df-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c89df-138">URI de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89df-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c89df-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c89df-141">Type de l’URI de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="c89df-142">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c89df-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89df-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c89df-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c89df-145">Locataire de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="c89df-146">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c89df-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89df-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c89df-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c89df-149">Nom de domaine complet du pool ayant hébergé la conférence.</span><span class="sxs-lookup"><span data-stu-id="c89df-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89df-150"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="c89df-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c89df-151">type</span><span class="sxs-lookup"><span data-stu-id="c89df-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="c89df-p108">Masque de bits qui contient les attributs de la conférence. Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c89df-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="c89df-154">0X01 – Synthetic Transaction</span><span class="sxs-lookup"><span data-stu-id="c89df-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

