---
title: 'Lync Server 2013: rapport de diagnostic de la Conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="6bc76-102">Rapport de diagnostic de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bc76-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bc76-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6bc76-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6bc76-104">Le rapport de diagnostic de conférence fournit des informations sur la réussite ou l’échec de toutes les sessions de conférence.</span><span class="sxs-lookup"><span data-stu-id="6bc76-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="6bc76-105">Notez que Microsoft Lync Server distingue différentes sortes d’échecs:</span><span class="sxs-lookup"><span data-stu-id="6bc76-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="6bc76-p102">**échec attendu**. Un échec attendu est généralement une erreur au sens technique seulement. Par exemple, supposons que quelqu’un démarre une conférence, mais raccroche avant que des personnes puissent participer. Techniquement, c’est une erreur : la conférence a été lancée, mais n’a pas été achevée. Cependant, il s’agit d’une erreur à laquelle on peut s’attendre : si l’organisateur annule la conférence avant que des personnes puissent participer, on ne s’attend pas à ce que cette conférence soit achevée.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="6bc76-p103">**échec inattendu**. Un échec inattendu constitue exactement ce que son nom indique : une erreur à laquelle on ne s’attend pas, compte tenu des circonstances. Par exemple, supposons qu’une conférence ne puisse pas avoir lieu parce que la stratégie de réunion de l’organisateur n’a pas pu être récupérée. Il s’agit d’une erreur inattendue : la stratégie de réunion d’un utilisateur doit toujours pouvoir être récupérée.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="6bc76-p104">Notez que les mesures de Réussite, d’Échec attendu et d’Échec inattendu peuvent ne pas être comptabilisées dans la mesure Nombre total de sessions. Par exemple, vous pouvez voir les valeurs suivantes dans le rapport :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bc76-117">Réussites</span><span class="sxs-lookup"><span data-stu-id="6bc76-117">Successes</span></span></th>
<th><span data-ttu-id="6bc76-118">Échecs attendus</span><span class="sxs-lookup"><span data-stu-id="6bc76-118">Expected failures</span></span></th>
<th><span data-ttu-id="6bc76-119">Échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="6bc76-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="6bc76-120">Nombre total de sessions</span><span class="sxs-lookup"><span data-stu-id="6bc76-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-121">2024</span><span class="sxs-lookup"><span data-stu-id="6bc76-121">2024</span></span></p></td>
<td><p><span data-ttu-id="6bc76-122">469</span><span class="sxs-lookup"><span data-stu-id="6bc76-122">469</span></span></p></td>
<td><p><span data-ttu-id="6bc76-123">Seiz</span><span class="sxs-lookup"><span data-stu-id="6bc76-123">16</span></span></p></td>
<td><p><span data-ttu-id="6bc76-124">2521</span><span class="sxs-lookup"><span data-stu-id="6bc76-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6bc76-125">Si vous ajoutez 2 024 + 469 + 16, vous obtenez un total de 2 509 sessions alors que la colonne Nombre total de sessions indique 2 521 sessions.</span><span class="sxs-lookup"><span data-stu-id="6bc76-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="6bc76-126">Les 12 sessions « manquantes » sont celles que le système n’a pas pu catégoriser comme réussies ou non.</span><span class="sxs-lookup"><span data-stu-id="6bc76-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="6bc76-127">Ce peut arriver parfois quand un produit tiers introduit un nouveau code de diagnostic qui n’est pas connu de surveiller le serveur.</span><span class="sxs-lookup"><span data-stu-id="6bc76-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="6bc76-128">Dans ce cas, les appels effectués à l’aide de ce produit et reportant ce code de diagnostic ne peuvent pas toujours être catégorisés en tant que réussite, échec attendu ou échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="6bc76-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="6bc76-129">Accès au rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="6bc76-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="6bc76-130">Le rapport des de diagnostic de conférence est accessible à partir de la page d’accueil des Rapports de suivi.</span><span class="sxs-lookup"><span data-stu-id="6bc76-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="6bc76-131">Vous pouvez accéder au [rapport de distribution des échecs dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) en cliquant sur l’une des mesures suivantes:</span><span class="sxs-lookup"><span data-stu-id="6bc76-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="6bc76-132">Nombre d’échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="6bc76-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="6bc76-133">Nombre d’échecs attendus</span><span class="sxs-lookup"><span data-stu-id="6bc76-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="6bc76-134">Utilisation optimale du rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="6bc76-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="6bc76-135">Le rapport de diagnostic de conférence inclut une série de graphiques.</span><span class="sxs-lookup"><span data-stu-id="6bc76-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="6bc76-136">Chaque colonne de graphique constitue un lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="6bc76-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="6bc76-137">Si vous cliquez sur une colonne, vous accédez au rapport de [distribution des échecs dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) pour cette période et ce type de conférence.</span><span class="sxs-lookup"><span data-stu-id="6bc76-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6bc76-138">Filtres</span><span class="sxs-lookup"><span data-stu-id="6bc76-138">Filters</span></span>

<span data-ttu-id="6bc76-p108">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de diagnostic de conférence vous permet de filtrer les éléments tels que le type de conférence mené (par exemple, une conférence Focus) pour le serveur Edge utilisé dans la conférence. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6bc76-143">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic de conférence.</span><span class="sxs-lookup"><span data-stu-id="6bc76-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="6bc76-144">Filtres du rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="6bc76-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bc76-145">Nom</span><span class="sxs-lookup"><span data-stu-id="6bc76-145">Name</span></span></th>
<th><span data-ttu-id="6bc76-146">Description</span><span class="sxs-lookup"><span data-stu-id="6bc76-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-147"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-p109">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6bc76-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6bc76-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6bc76-p110">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6bc76-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6bc76-153">7/7/2012</span></span></p>
<p><span data-ttu-id="6bc76-154">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="6bc76-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6bc76-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6bc76-155">7/3/2012</span></span></p>
<p><span data-ttu-id="6bc76-156">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="6bc76-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bc76-157"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-p111">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6bc76-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6bc76-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6bc76-p112">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6bc76-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6bc76-163">7/7/2012</span></span></p>
<p><span data-ttu-id="6bc76-164">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="6bc76-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6bc76-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6bc76-165">7/3/2012</span></span></p>
<p><span data-ttu-id="6bc76-166">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="6bc76-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-167"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-p113">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6bc76-170">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="6bc76-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6bc76-171">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="6bc76-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6bc76-172">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="6bc76-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6bc76-173">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="6bc76-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="6bc76-174">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6bc76-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="6bc76-175">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="6bc76-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bc76-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-p115">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-180"><strong>Sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-p116">Indique le type de session de conférence. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="6bc76-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6bc76-183">[Tous]</span><span class="sxs-lookup"><span data-stu-id="6bc76-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="6bc76-184">Sessions Focus</span><span class="sxs-lookup"><span data-stu-id="6bc76-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="6bc76-185">Toutes les sessions MCU</span><span class="sxs-lookup"><span data-stu-id="6bc76-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="6bc76-186">Conférence par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="6bc76-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="6bc76-187">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="6bc76-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="6bc76-188">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="6bc76-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6bc76-189">Mesures</span><span class="sxs-lookup"><span data-stu-id="6bc76-189">Metrics</span></span>

<span data-ttu-id="6bc76-190">Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic de conférence pour chaque type de session de conférence.</span><span class="sxs-lookup"><span data-stu-id="6bc76-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="6bc76-191">Mesures du rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="6bc76-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bc76-192">Nom</span><span class="sxs-lookup"><span data-stu-id="6bc76-192">Name</span></span></th>
<th><span data-ttu-id="6bc76-193">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="6bc76-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6bc76-194">Description</span><span class="sxs-lookup"><span data-stu-id="6bc76-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-195"><strong>Nombre de réussites</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-196">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-196">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-197">Nombre total de conférences réussies.</span><span class="sxs-lookup"><span data-stu-id="6bc76-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bc76-198"><strong>Pourcentage de réussite</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-199">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-199">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-p117">Pourcentage de conférences qui se sont déroulées sans problème majeur. Calculé en divisant le nombre de réussites par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-202"><strong>Nombre d’échecs attendus</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-203">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-203">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-204">Nombre total de conférences pour lesquelles &quot;un échec&quot; inattendu s’est produit.</span><span class="sxs-lookup"><span data-stu-id="6bc76-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="6bc76-p118">Un échec attendu est un échec auquel il faut s’attendre. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, il faut s’attendre à ce que tout appel émis vers cet utilisateur échoue.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bc76-207"><strong>Pourcentage d’échec attendu</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-208">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-208">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-p119">Pourcentage de conférences qui ont rencontré une erreur attendue. Calculé en divisant le nombre d’échecs attendus par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-211"><strong>Nombre d’échecs inattendus</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-212">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-212">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-213">Nombre total de conférences pour lesquelles &quot;un échec&quot; inattendu s’est produit.</span><span class="sxs-lookup"><span data-stu-id="6bc76-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="6bc76-p120">Un échec inattendu est un échec qui se produit alors que le système semble intègre. Par exemple, un appel ne doit pas être coupé si l’appelant est mis en attente. Dans le cas contraire, ce problème est considéré comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bc76-217"><strong>Pourcentage d’échec inattendu</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-218">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-218">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-p121">Pourcentage de conférences qui ont rencontré une erreur inattendue. Calculé en divisant le nombre d’échecs inattendus par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="6bc76-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bc76-221"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="6bc76-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="6bc76-222">Non</span><span class="sxs-lookup"><span data-stu-id="6bc76-222">No</span></span></p></td>
<td><p><span data-ttu-id="6bc76-223">Nombre total de conférences, incluant les conférences qui ont réussi et celles qui ont échoué (à la fois les échecs attendus et les échecs inattendus), ainsi que les conférences qui n’appartiennent à aucune catégorie.</span><span class="sxs-lookup"><span data-stu-id="6bc76-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

