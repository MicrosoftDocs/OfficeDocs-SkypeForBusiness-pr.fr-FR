---
title: 'Lync Server 2013: rapport d’activité de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="86492-102">Rapport d’activité de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86492-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86492-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="86492-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="86492-104">Le rapport des activités de conférence vous permet de répondre facilement à des questions telles que : combien y a-t-il de conférences organisées chaque jour et à quel moments ces conférences sont-elles organisées ?</span><span class="sxs-lookup"><span data-stu-id="86492-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="86492-105">Ce genre d’information n’est pas seulement utile en tant que tel, il peut également permettre de résoudre des problèmes.</span><span class="sxs-lookup"><span data-stu-id="86492-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="86492-106">Par exemple, imaginons que des utilisateurs se plaignent de la lenteur du réseau en milieu de journée.</span><span class="sxs-lookup"><span data-stu-id="86492-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="86492-107">Un bref coup d’œil sur les rapports d’activité de conférence peut suggérer une raison possible: beaucoup plus de conférences sont prévues entre les heures de 10:00 AM et 2:00 PM à tout moment.</span><span class="sxs-lookup"><span data-stu-id="86492-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="86492-108">Si la lenteur du réseau engendre des problèmes, vous pouvez encourager les utilisateurs à replanifier certaines de leurs conférences à un moment de la journée où le trafic est moins important.</span><span class="sxs-lookup"><span data-stu-id="86492-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="86492-109">Accès au rapport des activités de conférence</span><span class="sxs-lookup"><span data-stu-id="86492-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="86492-110">Le rapport d’activité de conférence est accessible à partir du [rapport de synthèse de conférences dans Lync Server 2013](lync-server-2013-conference-summary-report.md) en cliquant sur l’une des mesures suivantes:</span><span class="sxs-lookup"><span data-stu-id="86492-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="86492-111">Nombre total de conférences</span><span class="sxs-lookup"><span data-stu-id="86492-111">Total conferences</span></span>

  - <span data-ttu-id="86492-112">Nombre total de participants</span><span class="sxs-lookup"><span data-stu-id="86492-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="86492-113">Utilisation optimale du rapport des activités de conférence</span><span class="sxs-lookup"><span data-stu-id="86492-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="86492-p102">Par défaut, le rapport des activités de conférence indique le nombre total de conférences pour une période spécifiée (par exemple, le nombre total de conférences par jour ou le nombre total de conférences par heure pour une journée). Cependant, vous pouvez choisir d’afficher également le nombre total de participants pour cette même période ou le nombre total de minutes de participant. Pour ce faire, cliquez sur le bouton Afficher/Masquer les paramètres pour afficher les options de filtrage, puis en sélectionner une dans la liste déroulante Établir un rapport par :</span><span class="sxs-lookup"><span data-stu-id="86492-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="86492-117">Nombre de participants</span><span class="sxs-lookup"><span data-stu-id="86492-117">Participant count</span></span>

  - <span data-ttu-id="86492-118">Minutes de participant</span><span class="sxs-lookup"><span data-stu-id="86492-118">Participant minutes</span></span>

  - <span data-ttu-id="86492-119">Nombre de conférences</span><span class="sxs-lookup"><span data-stu-id="86492-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="86492-120">Filtres</span><span class="sxs-lookup"><span data-stu-id="86492-120">Filters</span></span>

<span data-ttu-id="86492-p103">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport des activités de conférence.</span><span class="sxs-lookup"><span data-stu-id="86492-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="86492-123">Filtres du rapport des activités de conférence</span><span class="sxs-lookup"><span data-stu-id="86492-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86492-124">Nom</span><span class="sxs-lookup"><span data-stu-id="86492-124">Name</span></span></th>
<th><span data-ttu-id="86492-125">Description</span><span class="sxs-lookup"><span data-stu-id="86492-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86492-126"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="86492-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-p104">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="86492-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="86492-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86492-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86492-p105">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="86492-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86492-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86492-132">7/7/2012</span></span></p>
<p><span data-ttu-id="86492-133">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="86492-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86492-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86492-134">7/3/2012</span></span></p>
<p><span data-ttu-id="86492-135">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="86492-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86492-136"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="86492-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-p106">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="86492-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="86492-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86492-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86492-p107">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="86492-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86492-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86492-142">7/7/2012</span></span></p>
<p><span data-ttu-id="86492-143">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="86492-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86492-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86492-144">7/3/2012</span></span></p>
<p><span data-ttu-id="86492-145">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="86492-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86492-146"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="86492-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-p108">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="86492-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86492-149">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="86492-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="86492-150">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="86492-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="86492-151">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="86492-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="86492-152">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="86492-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="86492-153">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="86492-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="86492-154">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="86492-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86492-155"><strong>Établir un rapport par</strong></span><span class="sxs-lookup"><span data-stu-id="86492-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-p110">Indique les valeurs qu’il convient d’utiliser dans le rapport. Vous pouvez sélectionner l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="86492-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86492-158">Nombre de participants</span><span class="sxs-lookup"><span data-stu-id="86492-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="86492-159">Minutes de participant</span><span class="sxs-lookup"><span data-stu-id="86492-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="86492-160">Nombre de conférences</span><span class="sxs-lookup"><span data-stu-id="86492-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="86492-161">Mesure des conférences par pool</span><span class="sxs-lookup"><span data-stu-id="86492-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="86492-162">Le tableau qui suit répertorie les informations dans le rapport des activités de conférence pour chaque pool.</span><span class="sxs-lookup"><span data-stu-id="86492-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="86492-163">Mesure des conférences par pool</span><span class="sxs-lookup"><span data-stu-id="86492-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86492-164">Nom</span><span class="sxs-lookup"><span data-stu-id="86492-164">Name</span></span></th>
<th><span data-ttu-id="86492-165">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="86492-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="86492-166">Description</span><span class="sxs-lookup"><span data-stu-id="86492-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86492-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="86492-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-168">Non</span><span class="sxs-lookup"><span data-stu-id="86492-168">No</span></span></p></td>
<td><p><span data-ttu-id="86492-169">Nom du pool de serveurs d’inscriptions ou du serveur Edge utilisés dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="86492-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86492-170"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="86492-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-171">Non</span><span class="sxs-lookup"><span data-stu-id="86492-171">No</span></span></p></td>
<td><p><span data-ttu-id="86492-172">Date et heure auxquelles la conférence s’est tenue.</span><span class="sxs-lookup"><span data-stu-id="86492-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86492-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="86492-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-174">Non</span><span class="sxs-lookup"><span data-stu-id="86492-174">No</span></span></p></td>
<td><p><span data-ttu-id="86492-175">Nombre total de participants, nombre total de minutes par participant ou nombre total de conférences.</span><span class="sxs-lookup"><span data-stu-id="86492-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="86492-176">Mesure des conférences par type de serveur</span><span class="sxs-lookup"><span data-stu-id="86492-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="86492-177">Le tableau qui suit répertorie les informations dans le rapport des activités de conférence pour chaque type de serveur.</span><span class="sxs-lookup"><span data-stu-id="86492-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="86492-178">Mesure des conférences par type de serveur</span><span class="sxs-lookup"><span data-stu-id="86492-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86492-179">Nom</span><span class="sxs-lookup"><span data-stu-id="86492-179">Name</span></span></th>
<th><span data-ttu-id="86492-180">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="86492-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="86492-181">Description</span><span class="sxs-lookup"><span data-stu-id="86492-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86492-182"><strong>Type de serveur de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="86492-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-183">Non</span><span class="sxs-lookup"><span data-stu-id="86492-183">No</span></span></p></td>
<td><p><span data-ttu-id="86492-184">Type de serveur utilisé dans la conférence, généralement l’un des types suivants :</span><span class="sxs-lookup"><span data-stu-id="86492-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86492-185">Serveur de conférence web</span><span class="sxs-lookup"><span data-stu-id="86492-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="86492-186">Service de conférence de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="86492-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="86492-187">Service de téléconférence</span><span class="sxs-lookup"><span data-stu-id="86492-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="86492-188">Serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="86492-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="86492-189">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="86492-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86492-190"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="86492-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-191">Non</span><span class="sxs-lookup"><span data-stu-id="86492-191">No</span></span></p></td>
<td><p><span data-ttu-id="86492-192">Date et heure auxquelles la conférence s’est tenue.</span><span class="sxs-lookup"><span data-stu-id="86492-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86492-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="86492-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="86492-194">Non</span><span class="sxs-lookup"><span data-stu-id="86492-194">No</span></span></p></td>
<td><p><span data-ttu-id="86492-195">Nombre total de participants, nombre total de minutes par participant ou nombre total de conférences.</span><span class="sxs-lookup"><span data-stu-id="86492-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

