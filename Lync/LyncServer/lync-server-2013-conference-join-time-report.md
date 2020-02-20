---
title: 'Lync Server 2013 : rapport des heures de participation aux conférences'
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
ms.openlocfilehash: e11932d1f63e6d756b0a3a5ba1eb7b33498dac61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="c2e22-102">Rapport de temps de participation aux conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2e22-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2e22-103">_**Dernière modification de la rubrique :** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="c2e22-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="c2e22-p101">Le résumé des heures d؊’arrivée aux conférences vous permet de déterminer le temps nécessaire à vos utilisateurs pour rejoindre une conférence. Le rapport indique le temps nécessaire moyen (en millisecondes) et fournit également une répartition montrant combien d’utilisateurs ont pu rejoindre la conférence en 2 secondes ou moins, combien ont nécessité entre 2 et 5 secondes, etc.</span><span class="sxs-lookup"><span data-stu-id="c2e22-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="c2e22-106">Accès au rapport des heures d’arrivée aux conférences</span><span class="sxs-lookup"><span data-stu-id="c2e22-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="c2e22-107">Le rapport des heures d’arrivée aux conférences est accessible à partir de la page d’accueil des Rapports de suivi.</span><span class="sxs-lookup"><span data-stu-id="c2e22-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c2e22-108">Filtres</span><span class="sxs-lookup"><span data-stu-id="c2e22-108">Filters</span></span>

<span data-ttu-id="c2e22-p102">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport du temps de participation aux conférences.</span><span class="sxs-lookup"><span data-stu-id="c2e22-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="c2e22-111">Filtres du rapport des heures d’arrivée aux conférences</span><span class="sxs-lookup"><span data-stu-id="c2e22-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2e22-112">Nom</span><span class="sxs-lookup"><span data-stu-id="c2e22-112">Name</span></span></th>
<th><span data-ttu-id="c2e22-113">Description</span><span class="sxs-lookup"><span data-stu-id="c2e22-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-p103">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="c2e22-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c2e22-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c2e22-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c2e22-p104">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c2e22-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c2e22-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c2e22-120">7/7/2012</span></span></p>
<p><span data-ttu-id="c2e22-121">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c2e22-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c2e22-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c2e22-122">7/3/2012</span></span></p>
<p><span data-ttu-id="c2e22-123">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c2e22-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-p105">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c2e22-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c2e22-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c2e22-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c2e22-p106">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c2e22-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c2e22-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c2e22-130">7/7/2012</span></span></p>
<p><span data-ttu-id="c2e22-131">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c2e22-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c2e22-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c2e22-132">7/3/2012</span></span></p>
<p><span data-ttu-id="c2e22-133">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c2e22-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-134"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-p107">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c2e22-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c2e22-137">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="c2e22-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c2e22-138">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="c2e22-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c2e22-139">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="c2e22-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c2e22-140">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="c2e22-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c2e22-p108">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="c2e22-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-143"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-p109">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="c2e22-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-147"><strong>Sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-p110">Type de session. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c2e22-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c2e22-150">Tous les</span><span class="sxs-lookup"><span data-stu-id="c2e22-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="c2e22-151">Sessions de focus (le focus est la stratégie centrale et le gestionnaire d’État pour les réunions en ligne et coordonne tous les aspects d’une conférence</span><span class="sxs-lookup"><span data-stu-id="c2e22-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="c2e22-152">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="c2e22-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="c2e22-153">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="c2e22-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="c2e22-p111">Si vous sélectionnez [Tout], total des heures d’arrivée aux conférences s’affiche en haut du rapport. Notez que ces totaux ne concernent que les conférences planifiées à l’aide de Microsoft Exchange ou Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="c2e22-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c2e22-156">Mesures</span><span class="sxs-lookup"><span data-stu-id="c2e22-156">Metrics</span></span>

<span data-ttu-id="c2e22-157">Le tableau suivant répertorie les informations fournies dans le rapport des heures d’arrivée aux conférences.</span><span class="sxs-lookup"><span data-stu-id="c2e22-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="c2e22-158">Mesures du rapport des heures d’arrivée aux conférences</span><span class="sxs-lookup"><span data-stu-id="c2e22-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2e22-159">Nom</span><span class="sxs-lookup"><span data-stu-id="c2e22-159">Name</span></span></th>
<th><span data-ttu-id="c2e22-160">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c2e22-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c2e22-161">Description</span><span class="sxs-lookup"><span data-stu-id="c2e22-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-162"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="c2e22-163">Le titre réel de cette mesure varie en fonction de l’intervalle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c2e22-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="c2e22-164">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-164">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-165">Date et heure des conférences.</span><span class="sxs-lookup"><span data-stu-id="c2e22-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-166"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-167">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-167">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-168">Nombre total de sessions qui comprend les sessions ayant abouti, les sessions ayant échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</span><span class="sxs-lookup"><span data-stu-id="c2e22-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-169"><strong>Moyenne (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-170">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-170">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-171">Temps moyen (en millisecondes) nécessaire aux participants pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-172"><strong>Sessions &lt; 2 secondes, volume</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-173">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-173">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-174">Nombre de participants ayant pu rejoindre la conférence en moins de 2 secondes.</span><span class="sxs-lookup"><span data-stu-id="c2e22-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-175"><strong>Sessions &lt; 2 secondes, pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-176">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-177"><strong>Sessions 2-5 secondes, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-178">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-178">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-179">Nombre de participants ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-180"><strong>Sessions 2-5 secondes, Pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-181">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-181">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-182">Pourcentage du total des participants à l’appel ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-183"><strong>Sessions 5-10 secondes, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-184">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-184">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-185">Nombre de participants ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-186"><strong>Sessions 5-10 secondes, Pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-187">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-187">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-188">Pourcentage du total des participants à l’appel ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2e22-189"><strong>Sessions &gt; 10 secondes, volume</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-190">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-190">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-191">Nombre de participants ayant nécessité plus de 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2e22-192"><strong>Sessions &gt; 10 secondes, pourcentage</strong></span><span class="sxs-lookup"><span data-stu-id="c2e22-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c2e22-193">Non</span><span class="sxs-lookup"><span data-stu-id="c2e22-193">No</span></span></p></td>
<td><p><span data-ttu-id="c2e22-194">Pourcentage du total des participants à l’appel ayant nécessité plus de 10 secondes pour rejoindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="c2e22-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

