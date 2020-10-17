---
title: 'Lync Server 2013 : sous-rapport de synthèse de conférence'
description: 'Lync Server 2013 : sous-rapport de synthèse de conférence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550690"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="5cd4b-103">Sous-rapport de synthèse de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cd4b-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cd4b-104">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="5cd4b-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="5cd4b-p101">Le sous-rapport de synthèse de conférence fournit une vision générale des sessions de conférence ayant échoué. Ces échecs de session sont répartis par type de session : sessions Focus et les sessions MCU.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="5cd4b-107">Filtres</span><span class="sxs-lookup"><span data-stu-id="5cd4b-107">Filters</span></span>

<span data-ttu-id="5cd4b-p102">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de synthèse de conférence.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="5cd4b-110">Filtres du sous-rapport de synthèse de conférence</span><span class="sxs-lookup"><span data-stu-id="5cd4b-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cd4b-111">Nom</span><span class="sxs-lookup"><span data-stu-id="5cd4b-111">Name</span></span></th>
<th><span data-ttu-id="5cd4b-112">Description</span><span class="sxs-lookup"><span data-stu-id="5cd4b-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-p103">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5cd4b-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5cd4b-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5cd4b-p104">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5cd4b-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5cd4b-119">7/7/2012</span></span></p>
<p><span data-ttu-id="5cd4b-120">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="5cd4b-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5cd4b-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5cd4b-121">7/3/2012</span></span></p>
<p><span data-ttu-id="5cd4b-122">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd4b-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-p105">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5cd4b-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5cd4b-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5cd4b-p106">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5cd4b-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5cd4b-129">7/7/2012</span></span></p>
<p><span data-ttu-id="5cd4b-130">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="5cd4b-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5cd4b-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5cd4b-131">7/3/2012</span></span></p>
<p><span data-ttu-id="5cd4b-132">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-133"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-p107">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5cd4b-137">Mesures</span><span class="sxs-lookup"><span data-stu-id="5cd4b-137">Metrics</span></span>

<span data-ttu-id="5cd4b-138">Le tableau suivant répertorie les informations fournies dans le sous-rapport de synthèse de conférence.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="5cd4b-139">Mesures du sous-rapport de synthèse de conférence</span><span class="sxs-lookup"><span data-stu-id="5cd4b-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cd4b-140">Nom</span><span class="sxs-lookup"><span data-stu-id="5cd4b-140">Name</span></span></th>
<th><span data-ttu-id="5cd4b-141">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="5cd4b-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5cd4b-142">Description</span><span class="sxs-lookup"><span data-stu-id="5cd4b-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-143"><strong>Nombre total de conférences</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-144">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-144">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-145">Nombre total de conférences ayant eu lieu.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd4b-146"><strong>Nombre total de sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-147">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-147">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-p108">Nombre total de sessions de conférence. Une seule conférence peut avoir plusieurs sessions : par exemple, elle peut inclure à la fois une session Focus et une session MCU.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-150"><strong>Taux d’échec global des sessions</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-151">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-151">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-152">Pourcentage de tous les échecs de conférence.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd4b-153"><strong>Sessions Focus</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-154">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-154">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-155">Nombre total de sessions Focus.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-156"><strong>Taux d’échec Focus</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-157">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-157">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-158">Pourcentage d’échec des sessions Focus.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd4b-159">Sessions MCU</span><span class="sxs-lookup"><span data-stu-id="5cd4b-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-160">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-160">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-161">Nombre total de sessions MCU.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-162"><strong>Taux d’échec MCU</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-163">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-163">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-164">Pourcentage d’échec des sessions MCU.</span><span class="sxs-lookup"><span data-stu-id="5cd4b-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd4b-165"><strong>Sessions MCU par modalité</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-166">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-166">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-167">Nombre total de sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="5cd4b-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd4b-168"><strong>Taux d’échec par modalité</strong></span><span class="sxs-lookup"><span data-stu-id="5cd4b-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd4b-169">Non</span><span class="sxs-lookup"><span data-stu-id="5cd4b-169">No</span></span></p></td>
<td><p><span data-ttu-id="5cd4b-170">Pourcentage d’échec des sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="5cd4b-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

