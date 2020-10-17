---
title: 'Lync Server 2013 : tableau conférences'
description: 'Lync Server 2013 : tableau conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561600"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="30854-103">Tableau conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30854-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30854-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="30854-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="30854-105">Chaque enregistrement de cette table contient les détails des appels d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="30854-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30854-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="30854-106">Column</span></span></th>
<th><span data-ttu-id="30854-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="30854-107">Data Type</span></span></th>
<th><span data-ttu-id="30854-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="30854-108">Key/Index</span></span></th>
<th><span data-ttu-id="30854-109">Détails</span><span class="sxs-lookup"><span data-stu-id="30854-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30854-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="30854-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="30854-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="30854-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="30854-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="30854-113">Heure à laquelle la demande de conférence a été capturée par l’agent CDR.</span><span class="sxs-lookup"><span data-stu-id="30854-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="30854-114">Utilisé uniquement comme clé primaire pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="30854-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30854-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="30854-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-116">int</span><span class="sxs-lookup"><span data-stu-id="30854-116">int</span></span></p></td>
<td><p><span data-ttu-id="30854-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="30854-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="30854-118">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="30854-118">ID number to identify the session.</span></span> <span data-ttu-id="30854-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="30854-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30854-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="30854-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-121">int</span><span class="sxs-lookup"><span data-stu-id="30854-121">int</span></span></p></td>
<td><p><span data-ttu-id="30854-122">Etranger</span><span class="sxs-lookup"><span data-stu-id="30854-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30854-123">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="30854-123">Conference URI.</span></span> <span data-ttu-id="30854-124">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30854-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30854-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="30854-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-126">unique</span><span class="sxs-lookup"><span data-stu-id="30854-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30854-127">Utile pour les conférences périodiques ; chaque instance d’une conférence périodique a le même <strong>ConferenceUri</strong>, mais elle aura un <strong>ConfInstance</strong>différent.</span><span class="sxs-lookup"><span data-stu-id="30854-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30854-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="30854-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-129">DateHeure</span><span class="sxs-lookup"><span data-stu-id="30854-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30854-130">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="30854-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30854-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="30854-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-132">DateHeure</span><span class="sxs-lookup"><span data-stu-id="30854-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30854-133">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="30854-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30854-134"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="30854-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-135">int</span><span class="sxs-lookup"><span data-stu-id="30854-135">int</span></span></p></td>
<td><p><span data-ttu-id="30854-136">Etranger</span><span class="sxs-lookup"><span data-stu-id="30854-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30854-137">Numéro d’identification permettant d’identifier le pool dans lequel la Conférence a été capturée.</span><span class="sxs-lookup"><span data-stu-id="30854-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="30854-138">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30854-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30854-139"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="30854-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-140">Int</span><span class="sxs-lookup"><span data-stu-id="30854-140">Int</span></span></p></td>
<td><p><span data-ttu-id="30854-141">Etranger</span><span class="sxs-lookup"><span data-stu-id="30854-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="30854-142">Numéro d’identification permettant d’identifier l’URI de l’organisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="30854-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="30854-143">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="30854-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30854-144"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="30854-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-145">type</span><span class="sxs-lookup"><span data-stu-id="30854-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30854-146">Masque de bits qui contient les attributs de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="30854-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="30854-147">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="30854-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="30854-148">0X01</span><span class="sxs-lookup"><span data-stu-id="30854-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="30854-149">Fibres</span><span class="sxs-lookup"><span data-stu-id="30854-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="30854-150">Transaction</span><span class="sxs-lookup"><span data-stu-id="30854-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30854-151"><strong>Traiter</strong></span><span class="sxs-lookup"><span data-stu-id="30854-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="30854-152">légèrement</span><span class="sxs-lookup"><span data-stu-id="30854-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30854-153">Champ interne utilisé par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="30854-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="30854-154">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30854-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30854-155">\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="30854-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="30854-156">Si deux sessions commencent exactement en même temps, le SessionIdSeq est égal à 1 et l’autre à 2, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="30854-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

