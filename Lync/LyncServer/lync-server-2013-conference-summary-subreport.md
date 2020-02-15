---
title: 'Lync Server 2013 : sous-rapport de synthèse de conférence'
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
ms.openlocfilehash: d2c31c614298112b91874882df1e4945845b74bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="52616-102">Sous-rapport de synthèse de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52616-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52616-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="52616-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="52616-p101">Le sous-rapport de synthèse de conférence fournit une vision générale des sessions de conférence ayant échoué. Ces échecs de session sont répartis par type de session : sessions Focus et les sessions MCU.</span><span class="sxs-lookup"><span data-stu-id="52616-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="52616-106">Filtres</span><span class="sxs-lookup"><span data-stu-id="52616-106">Filters</span></span>

<span data-ttu-id="52616-p102">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le sous-rapport de synthèse de conférence.</span><span class="sxs-lookup"><span data-stu-id="52616-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="52616-109">Filtres du sous-rapport de synthèse de conférence</span><span class="sxs-lookup"><span data-stu-id="52616-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52616-110">Nom</span><span class="sxs-lookup"><span data-stu-id="52616-110">Name</span></span></th>
<th><span data-ttu-id="52616-111">Description</span><span class="sxs-lookup"><span data-stu-id="52616-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52616-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="52616-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-p103">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="52616-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="52616-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="52616-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="52616-p104">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="52616-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="52616-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="52616-118">7/7/2012</span></span></p>
<p><span data-ttu-id="52616-119">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="52616-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="52616-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="52616-120">7/3/2012</span></span></p>
<p><span data-ttu-id="52616-121">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="52616-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52616-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="52616-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-p105">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="52616-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="52616-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="52616-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="52616-p106">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="52616-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="52616-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="52616-128">7/7/2012</span></span></p>
<p><span data-ttu-id="52616-129">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="52616-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="52616-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="52616-130">7/3/2012</span></span></p>
<p><span data-ttu-id="52616-131">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="52616-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52616-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="52616-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-p107">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="52616-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="52616-136">Mesures</span><span class="sxs-lookup"><span data-stu-id="52616-136">Metrics</span></span>

<span data-ttu-id="52616-137">Le tableau suivant répertorie les informations fournies dans le sous-rapport de synthèse de conférence.</span><span class="sxs-lookup"><span data-stu-id="52616-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="52616-138">Mesures du sous-rapport de synthèse de conférence</span><span class="sxs-lookup"><span data-stu-id="52616-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52616-139">Nom</span><span class="sxs-lookup"><span data-stu-id="52616-139">Name</span></span></th>
<th><span data-ttu-id="52616-140">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="52616-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="52616-141">Description</span><span class="sxs-lookup"><span data-stu-id="52616-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52616-142"><strong>Nombre total de conférences</strong></span><span class="sxs-lookup"><span data-stu-id="52616-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-143">Non</span><span class="sxs-lookup"><span data-stu-id="52616-143">No</span></span></p></td>
<td><p><span data-ttu-id="52616-144">Nombre total de conférences ayant eu lieu.</span><span class="sxs-lookup"><span data-stu-id="52616-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52616-145"><strong>Nombre total de sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="52616-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-146">Non</span><span class="sxs-lookup"><span data-stu-id="52616-146">No</span></span></p></td>
<td><p><span data-ttu-id="52616-p108">Nombre total de sessions de conférence. Une seule conférence peut avoir plusieurs sessions : par exemple, elle peut inclure à la fois une session Focus et une session MCU.</span><span class="sxs-lookup"><span data-stu-id="52616-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52616-149"><strong>Taux d’échec global des sessions</strong></span><span class="sxs-lookup"><span data-stu-id="52616-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-150">Non</span><span class="sxs-lookup"><span data-stu-id="52616-150">No</span></span></p></td>
<td><p><span data-ttu-id="52616-151">Pourcentage de tous les échecs de conférence.</span><span class="sxs-lookup"><span data-stu-id="52616-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52616-152"><strong>Sessions Focus</strong></span><span class="sxs-lookup"><span data-stu-id="52616-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-153">Non</span><span class="sxs-lookup"><span data-stu-id="52616-153">No</span></span></p></td>
<td><p><span data-ttu-id="52616-154">Nombre total de sessions Focus.</span><span class="sxs-lookup"><span data-stu-id="52616-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52616-155"><strong>Taux d’échec Focus</strong></span><span class="sxs-lookup"><span data-stu-id="52616-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-156">Non</span><span class="sxs-lookup"><span data-stu-id="52616-156">No</span></span></p></td>
<td><p><span data-ttu-id="52616-157">Pourcentage d’échec des sessions Focus.</span><span class="sxs-lookup"><span data-stu-id="52616-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52616-158">Sessions MCU</span><span class="sxs-lookup"><span data-stu-id="52616-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="52616-159">Non</span><span class="sxs-lookup"><span data-stu-id="52616-159">No</span></span></p></td>
<td><p><span data-ttu-id="52616-160">Nombre total de sessions MCU.</span><span class="sxs-lookup"><span data-stu-id="52616-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52616-161"><strong>Taux d’échec MCU</strong></span><span class="sxs-lookup"><span data-stu-id="52616-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-162">Non</span><span class="sxs-lookup"><span data-stu-id="52616-162">No</span></span></p></td>
<td><p><span data-ttu-id="52616-163">Pourcentage d’échec des sessions MCU.</span><span class="sxs-lookup"><span data-stu-id="52616-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52616-164"><strong>Sessions MCU par modalité</strong></span><span class="sxs-lookup"><span data-stu-id="52616-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-165">Non</span><span class="sxs-lookup"><span data-stu-id="52616-165">No</span></span></p></td>
<td><p><span data-ttu-id="52616-166">Nombre total de sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="52616-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52616-167"><strong>Taux d’échec par modalité</strong></span><span class="sxs-lookup"><span data-stu-id="52616-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="52616-168">Non</span><span class="sxs-lookup"><span data-stu-id="52616-168">No</span></span></p></td>
<td><p><span data-ttu-id="52616-169">Pourcentage d’échec des sessions MCU, groupées par modalité (par exemple, les conférences de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="52616-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

