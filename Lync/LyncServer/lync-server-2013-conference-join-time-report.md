---
title: 'Lync Server 2013 : rapport des heures de participation aux conférences'
description: 'Lync Server 2013 : rapport de temps de participation aux conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd4aa5d21a8109a323bb953c7196f43715d51413
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542790"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="0d6bc-103">Rapport de temps de participation aux conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d6bc-103">Conference Join Time Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d6bc-104">_**Dernière modification de la rubrique :** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="0d6bc-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="0d6bc-p101">Le résumé des heures d؊’arrivée aux conférences vous permet de déterminer le temps nécessaire à vos utilisateurs pour rejoindre une conférence. Le rapport indique le temps nécessaire moyen (en millisecondes) et fournit également une répartition montrant combien d’utilisateurs ont pu rejoindre la conférence en 2 secondes ou moins, combien ont nécessité entre 2 et 5 secondes, etc.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="0d6bc-107">Accès au rapport des heures d’arrivée aux conférences</span><span class="sxs-lookup"><span data-stu-id="0d6bc-107">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="0d6bc-108">Le rapport des heures d’arrivée aux conférences est accessible à partir de la page d’accueil des Rapports de suivi.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-108">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0d6bc-109">Filtres</span><span class="sxs-lookup"><span data-stu-id="0d6bc-109">Filters</span></span>

<span data-ttu-id="0d6bc-p102">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport du temps de participation aux conférences.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="0d6bc-112">Filtres du rapport des heures d’arrivée aux conférences</span><span class="sxs-lookup"><span data-stu-id="0d6bc-112">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d6bc-113">Nom</span><span class="sxs-lookup"><span data-stu-id="0d6bc-113">Name</span></span></th>
<th><span data-ttu-id="0d6bc-114">Description</span><span class="sxs-lookup"><span data-stu-id="0d6bc-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-115"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-p103">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0d6bc-118">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0d6bc-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0d6bc-p104">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0d6bc-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0d6bc-121">7/7/2012</span></span></p>
<p><span data-ttu-id="0d6bc-122">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0d6bc-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0d6bc-123">7/3/2012</span></span></p>
<p><span data-ttu-id="0d6bc-124">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-125"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-p105">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0d6bc-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0d6bc-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0d6bc-p106">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0d6bc-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0d6bc-131">7/7/2012</span></span></p>
<p><span data-ttu-id="0d6bc-132">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0d6bc-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0d6bc-133">7/3/2012</span></span></p>
<p><span data-ttu-id="0d6bc-134">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-135"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-p107">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d6bc-138">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="0d6bc-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0d6bc-139">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="0d6bc-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0d6bc-140">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="0d6bc-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0d6bc-141">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="0d6bc-141">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0d6bc-p108">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-144"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-144"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-p109">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-148"><strong>Sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-148"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-p110">Type de session. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d6bc-151">Tous les</span><span class="sxs-lookup"><span data-stu-id="0d6bc-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="0d6bc-152">Sessions de focus (le focus est la stratégie centrale et le gestionnaire d’État pour les réunions en ligne et coordonne tous les aspects d’une conférence</span><span class="sxs-lookup"><span data-stu-id="0d6bc-152">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="0d6bc-153">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="0d6bc-153">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="0d6bc-154">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="0d6bc-154">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="0d6bc-p111">Si vous sélectionnez [Tout], total des heures d’arrivée aux conférences s’affiche en haut du rapport. Notez que ces totaux ne concernent que les conférences planifiées à l’aide de Microsoft Exchange ou Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0d6bc-157">Mesures</span><span class="sxs-lookup"><span data-stu-id="0d6bc-157">Metrics</span></span>

<span data-ttu-id="0d6bc-158">Le tableau suivant répertorie les informations fournies dans le rapport des heures d’arrivée aux conférences.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-158">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="0d6bc-159">Mesures du rapport des heures d’arrivée aux conférences</span><span class="sxs-lookup"><span data-stu-id="0d6bc-159">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d6bc-160">Nom</span><span class="sxs-lookup"><span data-stu-id="0d6bc-160">Name</span></span></th>
<th><span data-ttu-id="0d6bc-161">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="0d6bc-161">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0d6bc-162">Description</span><span class="sxs-lookup"><span data-stu-id="0d6bc-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-163"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-163"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="0d6bc-164">Le titre réel de cette mesure varie en fonction de l’intervalle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-164">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-165">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-165">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-166">Date et heure des conférences.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-166">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-167"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-167"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-168">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-168">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-169">Nombre total de sessions qui comprend les sessions ayant abouti, les sessions ayant échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-169">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-170"><strong>Moyenne (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-170"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-171">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-171">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-172">Temps moyen (en millisecondes) nécessaire aux participants pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-172">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-173"><strong>Sessions &lt; 2 secondes, volume</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-173"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-174">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-174">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-175">Nombre de participants ayant pu rejoindre la conférence en moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-175">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-176"><strong>Sessions &lt; 2 secondes, pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-176"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-177">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-177">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-178"><strong>Sessions 2-5 secondes, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-178"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-179">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-179">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-180">Nombre de participants ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-180">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-181"><strong>Sessions 2-5 secondes, Pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-181"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-182">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-182">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-183">Pourcentage du total des participants à l’appel ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-183">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-184"><strong>Sessions 5-10 secondes, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-184"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-185">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-185">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-186">Nombre de participants ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-186">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-187"><strong>Sessions 5-10 secondes, Pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-187"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-188">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-188">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-189">Pourcentage du total des participants à l’appel ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-189">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d6bc-190"><strong>Sessions &gt; 10 secondes, volume</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-190"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-191">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-191">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-192">Nombre de participants ayant nécessité plus de 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-192">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d6bc-193"><strong>Sessions &gt; 10 secondes, pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="0d6bc-193"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d6bc-194">Non</span><span class="sxs-lookup"><span data-stu-id="0d6bc-194">No</span></span></p></td>
<td><p><span data-ttu-id="0d6bc-195">Pourcentage du total des participants à l’appel ayant nécessité plus de 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="0d6bc-195">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

