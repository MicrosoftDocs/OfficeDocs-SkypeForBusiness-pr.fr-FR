---
title: 'Lync Server 2013 : tableau conférences'
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
ms.openlocfilehash: ef5e8811ad4b0adaccd8964e2f0bca718ca531e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529261"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="cbdaa-102">Tableau conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbdaa-102">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbdaa-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cbdaa-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cbdaa-104">Chaque enregistrement de cette table contient les détails des appels d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbdaa-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="cbdaa-105">Column</span></span></th>
<th><span data-ttu-id="cbdaa-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="cbdaa-106">Data Type</span></span></th>
<th><span data-ttu-id="cbdaa-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="cbdaa-107">Key/Index</span></span></th>
<th><span data-ttu-id="cbdaa-108">Détails</span><span class="sxs-lookup"><span data-stu-id="cbdaa-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbdaa-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="cbdaa-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="cbdaa-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-112">Heure à laquelle la demande de conférence a été capturée par l’agent CDR.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="cbdaa-113">Utilisé uniquement comme clé primaire pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdaa-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-115">int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-115">int</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="cbdaa-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-117">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-117">ID number to identify the session.</span></span> <span data-ttu-id="cbdaa-118">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdaa-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-120">int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-120">int</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-121">Etranger</span><span class="sxs-lookup"><span data-stu-id="cbdaa-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-122">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-122">Conference URI.</span></span> <span data-ttu-id="cbdaa-123">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbdaa-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdaa-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-125">unique</span><span class="sxs-lookup"><span data-stu-id="cbdaa-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cbdaa-126">Utile pour les conférences périodiques ; chaque instance d’une conférence périodique a le même <strong>ConferenceUri</strong>, mais elle aura un <strong>ConfInstance</strong>différent.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdaa-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-128">DateHeure</span><span class="sxs-lookup"><span data-stu-id="cbdaa-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cbdaa-129">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdaa-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="cbdaa-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cbdaa-132">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdaa-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-134">int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-134">int</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-135">Etranger</span><span class="sxs-lookup"><span data-stu-id="cbdaa-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-136">Numéro d’identification permettant d’identifier le pool dans lequel la Conférence a été capturée.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="cbdaa-137">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbdaa-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdaa-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-139">Int</span><span class="sxs-lookup"><span data-stu-id="cbdaa-139">Int</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-140">Etranger</span><span class="sxs-lookup"><span data-stu-id="cbdaa-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbdaa-141">Numéro d’identification permettant d’identifier l’URI de l’organisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="cbdaa-142">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbdaa-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdaa-143"><strong>Indicateur</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-144">type</span><span class="sxs-lookup"><span data-stu-id="cbdaa-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdaa-145">Masque de bits qui contient les attributs de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="cbdaa-146">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbdaa-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbdaa-147">0X01</span><span class="sxs-lookup"><span data-stu-id="cbdaa-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="cbdaa-148">Fibres</span><span class="sxs-lookup"><span data-stu-id="cbdaa-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="cbdaa-149">Transaction</span><span class="sxs-lookup"><span data-stu-id="cbdaa-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdaa-150"><strong>Traiter</strong></span><span class="sxs-lookup"><span data-stu-id="cbdaa-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdaa-151">légèrement</span><span class="sxs-lookup"><span data-stu-id="cbdaa-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdaa-152">Champ interne utilisé par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="cbdaa-153">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cbdaa-154">\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="cbdaa-155">Si deux sessions commencent exactement en même temps, le SessionIdSeq est égal à 1 et l’autre à 2, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="cbdaa-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

