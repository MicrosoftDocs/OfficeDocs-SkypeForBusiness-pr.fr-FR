---
title: 'Lync Server 2013 : Table Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="3ae09-102">Table Conferences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ae09-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ae09-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3ae09-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3ae09-104">Chaque enregistrement de cette table contient les détails des appels sur une conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ae09-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="3ae09-105">Column</span></span></th>
<th><span data-ttu-id="3ae09-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="3ae09-106">Data Type</span></span></th>
<th><span data-ttu-id="3ae09-107">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="3ae09-107">Key/Index</span></span></th>
<th><span data-ttu-id="3ae09-108">Détails</span><span class="sxs-lookup"><span data-stu-id="3ae09-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ae09-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3ae09-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="3ae09-111">Principal</span><span class="sxs-lookup"><span data-stu-id="3ae09-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ae09-112">Temps d’acquisition de la demande de conférence par l’agent CDR.</span><span class="sxs-lookup"><span data-stu-id="3ae09-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="3ae09-113">Utilisé uniquement comme clé primaire pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae09-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-115">int</span><span class="sxs-lookup"><span data-stu-id="3ae09-115">int</span></span></p></td>
<td><p><span data-ttu-id="3ae09-116">Principal</span><span class="sxs-lookup"><span data-stu-id="3ae09-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ae09-117">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="3ae09-117">ID number to identify the session.</span></span> <span data-ttu-id="3ae09-118">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae09-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-120">int</span><span class="sxs-lookup"><span data-stu-id="3ae09-120">int</span></span></p></td>
<td><p><span data-ttu-id="3ae09-121">Externes</span><span class="sxs-lookup"><span data-stu-id="3ae09-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3ae09-122">URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-122">Conference URI.</span></span> <span data-ttu-id="3ae09-123">Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3ae09-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae09-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-125">identificateur</span><span class="sxs-lookup"><span data-stu-id="3ae09-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae09-126">Utile pour les conférences récurrentes; chaque instance d’une conférence périodique a le même <strong>ConferenceUri</strong>, mais aura un autre <strong>ConfInstance</strong>.</span><span class="sxs-lookup"><span data-stu-id="3ae09-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae09-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-128">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3ae09-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae09-129">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae09-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-131">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3ae09-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3ae09-132">Heure de début de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae09-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-134">int</span><span class="sxs-lookup"><span data-stu-id="3ae09-134">int</span></span></p></td>
<td><p><span data-ttu-id="3ae09-135">Externes</span><span class="sxs-lookup"><span data-stu-id="3ae09-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3ae09-136">Numéro d’identification identifiant le regroupement dans lequel la Conférence a été capturée.</span><span class="sxs-lookup"><span data-stu-id="3ae09-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="3ae09-137">Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3ae09-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae09-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-139">Ent</span><span class="sxs-lookup"><span data-stu-id="3ae09-139">Int</span></span></p></td>
<td><p><span data-ttu-id="3ae09-140">Externes</span><span class="sxs-lookup"><span data-stu-id="3ae09-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3ae09-141">Numéro d’identification identifiant l’URI organisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="3ae09-142">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3ae09-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae09-143"><strong>Indication</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-144">type</span><span class="sxs-lookup"><span data-stu-id="3ae09-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae09-145">Masque binaire qui contient les attributs de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="3ae09-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="3ae09-146">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="3ae09-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ae09-147">0X01</span><span class="sxs-lookup"><span data-stu-id="3ae09-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="3ae09-148">Synthetic</span><span class="sxs-lookup"><span data-stu-id="3ae09-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="3ae09-149">Transaction</span><span class="sxs-lookup"><span data-stu-id="3ae09-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae09-150"><strong>Formé</strong></span><span class="sxs-lookup"><span data-stu-id="3ae09-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="3ae09-151">bit</span><span class="sxs-lookup"><span data-stu-id="3ae09-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ae09-152">Champ interne utilisé par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="3ae09-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="3ae09-153">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ae09-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3ae09-154">\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="3ae09-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="3ae09-155">S’il s’agit d’une session à partir de la même heure, le SessionIdSeq d’une personne sera 1, et pour l’autre, sera égale à 2, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="3ae09-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

