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
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="5bea7-102">Vue des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bea7-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bea7-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5bea7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5bea7-104">L’affichage des conférences fournit des informations relatives aux conférences.</span><span class="sxs-lookup"><span data-stu-id="5bea7-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="5bea7-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bea7-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bea7-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="5bea7-106">Column</span></span></th>
<th><span data-ttu-id="5bea7-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="5bea7-107">Data Type</span></span></th>
<th><span data-ttu-id="5bea7-108">Détails</span><span class="sxs-lookup"><span data-stu-id="5bea7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bea7-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5bea7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5bea7-111">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="5bea7-111">Time of session request.</span></span> <span data-ttu-id="5bea7-112">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="5bea7-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5bea7-113">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5bea7-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bea7-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-115">int</span><span class="sxs-lookup"><span data-stu-id="5bea7-115">int</span></span></p></td>
<td><p><span data-ttu-id="5bea7-116">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="5bea7-116">ID number to identify the session.</span></span> <span data-ttu-id="5bea7-117">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="5bea7-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5bea7-118">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5bea7-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bea7-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5bea7-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5bea7-121">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bea7-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bea7-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bea7-124">Type de l’URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-124">Type of the conference URI.</span></span> <span data-ttu-id="5bea7-125">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5bea7-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bea7-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-127">unique</span><span class="sxs-lookup"><span data-stu-id="5bea7-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5bea7-p105">Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceUri, mais une valeur ConfInstance différente.</span><span class="sxs-lookup"><span data-stu-id="5bea7-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bea7-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5bea7-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="5bea7-132">Heure de début de la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bea7-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-134">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5bea7-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="5bea7-135">Heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bea7-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5bea7-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5bea7-138">URI de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bea7-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bea7-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bea7-141">Type de l’URI de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="5bea7-142">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5bea7-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bea7-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bea7-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bea7-145">Locataire de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="5bea7-146">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5bea7-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bea7-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bea7-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bea7-149">Nom de domaine complet du pool ayant hébergé la conférence.</span><span class="sxs-lookup"><span data-stu-id="5bea7-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bea7-150"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="5bea7-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5bea7-151">type</span><span class="sxs-lookup"><span data-stu-id="5bea7-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="5bea7-p108">Masque de bits qui contient les attributs de la conférence. Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5bea7-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="5bea7-154">0X01 – Synthetic Transaction</span><span class="sxs-lookup"><span data-stu-id="5bea7-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

