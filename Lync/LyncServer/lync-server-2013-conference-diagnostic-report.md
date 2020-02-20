---
title: 'Lync Server 2013 : rapport de diagnostic de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e735193d75e0e8b5f23376844a712ce0e87d106
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="bafad-102">Rapport de diagnostic de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bafad-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bafad-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="bafad-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="bafad-104">Le rapport de diagnostic de conférence fournit des informations sur la réussite et l’échec de toutes les sessions de conférence.</span><span class="sxs-lookup"><span data-stu-id="bafad-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="bafad-105">Notez que Microsoft Lync Server différencie les différents types de défaillances :</span><span class="sxs-lookup"><span data-stu-id="bafad-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="bafad-106">**Échec attendu**.</span><span class="sxs-lookup"><span data-stu-id="bafad-106">**Expected failure**.</span></span> <span data-ttu-id="bafad-107">Un échec attendu est en général un échec considéré comme strictement technique.</span><span class="sxs-lookup"><span data-stu-id="bafad-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="bafad-108">Par exemple, supposons qu’un utilisateur démarre une conférence mais raccroche avant que quiconque puisse s’y joindre.</span><span class="sxs-lookup"><span data-stu-id="bafad-108">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="bafad-109">Techniquement, c’est une erreur : la Conférence a été lancée, mais n’a pas été terminée.</span><span class="sxs-lookup"><span data-stu-id="bafad-109">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="bafad-110">Toutefois, cela peut se produire : si l’organisateur annule la Conférence avant que tout le monde ne puisse participer, vous ne vous attendez pas à ce que la Conférence soit terminée.</span><span class="sxs-lookup"><span data-stu-id="bafad-110">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="bafad-111">**Échec inattendu**.</span><span class="sxs-lookup"><span data-stu-id="bafad-111">**Unexpected failure**.</span></span> <span data-ttu-id="bafad-112">Comme son nom l’indique, une erreur inattendue est une erreur que vous  n’attendiez pas selon les circonstances.</span><span class="sxs-lookup"><span data-stu-id="bafad-112">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="bafad-113">Par exemple, supposons qu’une conférence n’a pas pu être maintenue car la stratégie de réunion de l’organisateur n’a pas pu être récupérée.</span><span class="sxs-lookup"><span data-stu-id="bafad-113">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="bafad-114">Il s’agit d’une erreur inattendue : après tout, vous devriez toujours pouvoir récupérer la stratégie de réunion d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bafad-114">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="bafad-115">Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions.</span><span class="sxs-lookup"><span data-stu-id="bafad-115">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="bafad-116">Par exemple, vous pouvez voir les valeurs suivantes dans le rapport :</span><span class="sxs-lookup"><span data-stu-id="bafad-116">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bafad-117">Réussites</span><span class="sxs-lookup"><span data-stu-id="bafad-117">Successes</span></span></th>
<th><span data-ttu-id="bafad-118">Échecs attendus</span><span class="sxs-lookup"><span data-stu-id="bafad-118">Expected failures</span></span></th>
<th><span data-ttu-id="bafad-119">Échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="bafad-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="bafad-120">Total des sessions</span><span class="sxs-lookup"><span data-stu-id="bafad-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bafad-121">2024</span><span class="sxs-lookup"><span data-stu-id="bafad-121">2024</span></span></p></td>
<td><p><span data-ttu-id="bafad-122">469</span><span class="sxs-lookup"><span data-stu-id="bafad-122">469</span></span></p></td>
<td><p><span data-ttu-id="bafad-123">16 </span><span class="sxs-lookup"><span data-stu-id="bafad-123">16</span></span></p></td>
<td><p><span data-ttu-id="bafad-124">2521</span><span class="sxs-lookup"><span data-stu-id="bafad-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bafad-125">Si vous ajoutez 2024 + 469 + 16, vous obtenez un total de 2 509 sessions et pourtant, la colonne nombre total de sessions affiche un total de 2 521 sessions.</span><span class="sxs-lookup"><span data-stu-id="bafad-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="bafad-126">Les 12 sessions « manquantes » pour les sessions que le système n’a pas pu catégoriser comme réussies ou infructueuses.</span><span class="sxs-lookup"><span data-stu-id="bafad-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="bafad-127">C’est parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="bafad-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="bafad-128">Lorsque cela arrive, les appels effectués à l’aide de ce produit, et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.</span><span class="sxs-lookup"><span data-stu-id="bafad-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="bafad-129">Accès au rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="bafad-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="bafad-130">Le rapport de diagnostic de conférence est accessible à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="bafad-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="bafad-131">Vous pouvez accéder au [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="bafad-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="bafad-132">Volume d’échecs inattendus</span><span class="sxs-lookup"><span data-stu-id="bafad-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="bafad-133">Volume d’échecs attendus</span><span class="sxs-lookup"><span data-stu-id="bafad-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="bafad-134">Utilisation optimale du rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="bafad-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="bafad-135">Le rapport de diagnostic de conférence inclut une série de graphiques.</span><span class="sxs-lookup"><span data-stu-id="bafad-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="bafad-136">Chacune des colonnes affichées dans le graphique est un lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="bafad-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="bafad-137">Si vous cliquez sur une colonne, vous accédez au rapport de [répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) pendant cette période de temps et ce type de conférence.</span><span class="sxs-lookup"><span data-stu-id="bafad-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bafad-138">Filtres</span><span class="sxs-lookup"><span data-stu-id="bafad-138">Filters</span></span>

<span data-ttu-id="bafad-139">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="bafad-139">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="bafad-140">Par exemple, le rapport de diagnostic de conférence vous permet de filtrer des éléments tels que le type de conférence en cours (par exemple, une conférence basée sur le focus) ou par le serveur Edge utilisé dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="bafad-140">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="bafad-141">Vous pouvez également choisir le mode de groupement des données.</span><span class="sxs-lookup"><span data-stu-id="bafad-141">You can also choose how data should be grouped.</span></span> <span data-ttu-id="bafad-142">Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="bafad-142">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="bafad-143">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de diagnostic de conférence.</span><span class="sxs-lookup"><span data-stu-id="bafad-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="bafad-144">Filtres du rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="bafad-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bafad-145">Nom</span><span class="sxs-lookup"><span data-stu-id="bafad-145">Name</span></span></th>
<th><span data-ttu-id="bafad-146">Description</span><span class="sxs-lookup"><span data-stu-id="bafad-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bafad-147"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-p109">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="bafad-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="bafad-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bafad-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bafad-p110">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="bafad-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bafad-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bafad-153">7/7/2012</span></span></p>
<p><span data-ttu-id="bafad-154">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="bafad-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bafad-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bafad-155">7/3/2012</span></span></p>
<p><span data-ttu-id="bafad-156">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="bafad-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bafad-157"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-p111">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="bafad-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="bafad-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bafad-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bafad-p112">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="bafad-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bafad-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bafad-163">7/7/2012</span></span></p>
<p><span data-ttu-id="bafad-164">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="bafad-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bafad-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bafad-165">7/3/2012</span></span></p>
<p><span data-ttu-id="bafad-166">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="bafad-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bafad-167"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-p113">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="bafad-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bafad-170">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="bafad-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bafad-171">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="bafad-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bafad-172">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="bafad-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bafad-173">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="bafad-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="bafad-p114">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="bafad-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bafad-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-p115">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="bafad-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bafad-180"><strong>Sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-181">Indique le type de session de conférence.</span><span class="sxs-lookup"><span data-stu-id="bafad-181">Indicates the type of conferencing session.</span></span> <span data-ttu-id="bafad-182">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="bafad-182">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bafad-183">Tous les</span><span class="sxs-lookup"><span data-stu-id="bafad-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="bafad-184">Sessions Focus</span><span class="sxs-lookup"><span data-stu-id="bafad-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="bafad-185">Toutes les sessions MCU</span><span class="sxs-lookup"><span data-stu-id="bafad-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="bafad-186">Conférence par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="bafad-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="bafad-187">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="bafad-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="bafad-188">Conférence A/V</span><span class="sxs-lookup"><span data-stu-id="bafad-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="bafad-189">Mesures</span><span class="sxs-lookup"><span data-stu-id="bafad-189">Metrics</span></span>

<span data-ttu-id="bafad-190">Le tableau suivant répertorie les informations fournies dans le rapport de diagnostic de conférence pour chaque type de session de conférence.</span><span class="sxs-lookup"><span data-stu-id="bafad-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="bafad-191">Mesures du rapport de diagnostic de conférence</span><span class="sxs-lookup"><span data-stu-id="bafad-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bafad-192">Nom</span><span class="sxs-lookup"><span data-stu-id="bafad-192">Name</span></span></th>
<th><span data-ttu-id="bafad-193">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="bafad-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bafad-194">Description</span><span class="sxs-lookup"><span data-stu-id="bafad-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bafad-195"><strong>Volume d’opération réussie</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-196">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-196">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-197">Nombre total de conférences réussies.</span><span class="sxs-lookup"><span data-stu-id="bafad-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bafad-198"><strong>Pourcentage d’opération réussie</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-199">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-199">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-200">Pourcentage de conférences qui ont rencontré des problèmes importants.</span><span class="sxs-lookup"><span data-stu-id="bafad-200">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="bafad-201">Calculé en divisant le volume des opérations réussies par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="bafad-201">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bafad-202"><strong>Volume d’échec attendu</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-203">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-203">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-204">Nombre total de conférences pour lesquelles &quot;une défaillance&quot; attendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="bafad-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="bafad-p118">Un échec attendu est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.</span><span class="sxs-lookup"><span data-stu-id="bafad-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bafad-207"><strong>Pourcentage d’échec attendu</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-208">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-208">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-209">Pourcentage de conférences ayant rencontré une erreur attendue.</span><span class="sxs-lookup"><span data-stu-id="bafad-209">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="bafad-210">Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="bafad-210">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bafad-211"><strong>Volume d’échec inattendu</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-212">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-212">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-213">Nombre total de conférences pour lesquelles &quot;une défaillance&quot; inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="bafad-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="bafad-p120">Un échec inattendu se produit dans un système sain. Par exemple, un appel ne doit pas se terminer si l’appelant l’a mis en attente. Le cas échéant, cela serait marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="bafad-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bafad-217"><strong>Pourcentage d’échec inattendu</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-218">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-218">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-219">Pourcentage de conférences ayant rencontré une erreur inattendue.</span><span class="sxs-lookup"><span data-stu-id="bafad-219">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="bafad-220">Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</span><span class="sxs-lookup"><span data-stu-id="bafad-220">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bafad-221"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="bafad-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="bafad-222">Non</span><span class="sxs-lookup"><span data-stu-id="bafad-222">No</span></span></p></td>
<td><p><span data-ttu-id="bafad-223">Nombre total de conférences, y compris les conférences réussies, les conférences ayant échoué (échecs attendus et échecs inattendus) et les conférences non classées.</span><span class="sxs-lookup"><span data-stu-id="bafad-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

