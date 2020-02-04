---
title: 'Lync Server 2013 : rapport de synthèse de diagnostic des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="5db7f-102">Rapport de synthèse de diagnostic des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db7f-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db7f-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="5db7f-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="5db7f-p101">Le rapport de synthèse de diagnostic des appels fournit une vue d’ensemble des sessions de conférence et des sessions P2P ayant échoué. Ce rapport comprend le taux d’échecs général pour ces deux types de sessions, et détaille les informations par type de modalité de session :</span><span class="sxs-lookup"><span data-stu-id="5db7f-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="5db7f-106">Messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="5db7f-106">Instant messaging</span></span>

  - <span data-ttu-id="5db7f-107">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="5db7f-107">Application sharing</span></span>

  - <span data-ttu-id="5db7f-108">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="5db7f-108">File transfer</span></span>

  - <span data-ttu-id="5db7f-109">Audio</span><span class="sxs-lookup"><span data-stu-id="5db7f-109">Audio</span></span>

  - <span data-ttu-id="5db7f-110">Vidéo</span><span class="sxs-lookup"><span data-stu-id="5db7f-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="5db7f-111">Accès au rapport de synthèse de diagnostic des appels</span><span class="sxs-lookup"><span data-stu-id="5db7f-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="5db7f-112">Le rapport de synthèse de diagnostic des appels est accessible à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5db7f-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="5db7f-113">Dans le rapport synthèse des diagnostics d’appel, vous pouvez accéder au [rapport de diagnostic d’activité d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) en cliquant sur l’indice du taux d’échec dans la section synthèse de la session d’égal à égal du rapport.</span><span class="sxs-lookup"><span data-stu-id="5db7f-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="5db7f-114">Vous pouvez également accéder au [rapport de diagnostic de conférence dans Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) en cliquant sur l’une des mesures de conférences suivantes :</span><span class="sxs-lookup"><span data-stu-id="5db7f-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="5db7f-115">Taux d’échec de session global</span><span class="sxs-lookup"><span data-stu-id="5db7f-115">Overall session failure rate</span></span>

  - <span data-ttu-id="5db7f-116">Taux d’échec de focus</span><span class="sxs-lookup"><span data-stu-id="5db7f-116">Focus failure rate</span></span>

  - <span data-ttu-id="5db7f-117">Taux d’échec MCU</span><span class="sxs-lookup"><span data-stu-id="5db7f-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="5db7f-118">Utilisation efficace du rapport de synthèse de diagnostic des appels</span><span class="sxs-lookup"><span data-stu-id="5db7f-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="5db7f-119">Le rapport synthèse des diagnostics de l’appel inclut des graphiques qui comparent les taux d’échec pour les différentes modalités d’utilisation dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5db7f-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5db7f-120">Les colonnes de ces graphiques sont réellement des hyperliens. par exemple, si vous cliquez sur la colonne de messagerie instantanée pour les sessions d’égal à égal, vous découvrirez une instance du [rapport de diagnostic d’activité d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un rapport contenant des informations supplémentaires sur l’ensemble des sessions de messagerie instantanée incluses dans le rapport de synthèse des Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="5db7f-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5db7f-121">Filtres</span><span class="sxs-lookup"><span data-stu-id="5db7f-121">Filters</span></span>

<span data-ttu-id="5db7f-p104">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse de diagnostic des appels vous permet de filtrer selon des éléments tels que le pool de serveurs d’inscriptions ou le serveur Edge utilisé dans la session. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="5db7f-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="5db7f-126">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de diagnostic des appels.</span><span class="sxs-lookup"><span data-stu-id="5db7f-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="5db7f-127">Filtres de rapport de synthèse de diagnostic des appels</span><span class="sxs-lookup"><span data-stu-id="5db7f-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5db7f-128">Nom</span><span class="sxs-lookup"><span data-stu-id="5db7f-128">Name</span></span></th>
<th><span data-ttu-id="5db7f-129">Description</span><span class="sxs-lookup"><span data-stu-id="5db7f-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-130"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="5db7f-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5db7f-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5db7f-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5db7f-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="5db7f-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5db7f-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5db7f-136">7/7/2012</span></span></p>
<p><span data-ttu-id="5db7f-137">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="5db7f-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5db7f-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5db7f-138">7/3/2012</span></span></p>
<p><span data-ttu-id="5db7f-139">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="5db7f-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db7f-140"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="5db7f-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5db7f-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5db7f-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5db7f-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="5db7f-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5db7f-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5db7f-146">7/7/2012</span></span></p>
<p><span data-ttu-id="5db7f-147">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="5db7f-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5db7f-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5db7f-148">7/3/2012</span></span></p>
<p><span data-ttu-id="5db7f-149">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="5db7f-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-150"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-p109">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5db7f-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5db7f-153">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="5db7f-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5db7f-154">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="5db7f-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5db7f-155">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="5db7f-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5db7f-156">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="5db7f-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5db7f-157">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="5db7f-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="5db7f-158">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="5db7f-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db7f-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-p111">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</span><span class="sxs-lookup"><span data-stu-id="5db7f-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="5db7f-163">Mesures pour les sessions P2P</span><span class="sxs-lookup"><span data-stu-id="5db7f-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="5db7f-164">Le tableau ci-dessous décrit les informations fournies dans le rapport de synthèse de diagnostic des appels pour les sessions P2P (à savoir, celles qui n’impliquent que deux participants).</span><span class="sxs-lookup"><span data-stu-id="5db7f-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="5db7f-165">Mesures pour les sessions P2P</span><span class="sxs-lookup"><span data-stu-id="5db7f-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5db7f-166">Nom</span><span class="sxs-lookup"><span data-stu-id="5db7f-166">Name</span></span></th>
<th><span data-ttu-id="5db7f-167">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="5db7f-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5db7f-168">Description</span><span class="sxs-lookup"><span data-stu-id="5db7f-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-169"><strong>Nombre total de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-170">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-170">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-171">Nombre total de sessions P2P ayant eu lieu.</span><span class="sxs-lookup"><span data-stu-id="5db7f-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db7f-172"><strong>Taux d’échec</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-173">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-173">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-p112">Pourcentage de sessions P2P ayant échoué. Lorsque vous cliquez sur cet élément, le rapport affiche le rapport de diagnostic des activités P2P, qui fournit des informations plus détaillées sur les sessions P2P ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="5db7f-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="5db7f-176">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="5db7f-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="5db7f-177">Le tableau ci-dessous décrit les informations fournies dans le rapport de diagnostic des appels pour les sessions de conférence (à savoir, celles qui impliquent trois participants ou plus).</span><span class="sxs-lookup"><span data-stu-id="5db7f-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="5db7f-178">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="5db7f-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5db7f-179">Nom</span><span class="sxs-lookup"><span data-stu-id="5db7f-179">Name</span></span></th>
<th><span data-ttu-id="5db7f-180">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="5db7f-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5db7f-181">Description</span><span class="sxs-lookup"><span data-stu-id="5db7f-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-182"><strong>Nombre total de conférences</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-183">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-183">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-184">Nombre total de conférences ayant eu lieu.</span><span class="sxs-lookup"><span data-stu-id="5db7f-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db7f-185"><strong>Nombre total de sessions de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-186">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-186">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-187">Nombre total de sessions de conférence ayant eu lieu.</span><span class="sxs-lookup"><span data-stu-id="5db7f-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-188"><strong>Taux d’échec de session global</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-189">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-189">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-190">Pourcentage du total de sessions de conférence ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="5db7f-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db7f-191"><strong>Sessions Focus</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-192">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-192">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-193">Nombre total de sessions de conférence de focus ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="5db7f-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-194"><strong>Taux d’échec de focus</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-195">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-195">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-196">Pourcentage de sessions de conférence de focus ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="5db7f-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5db7f-197"><strong>Sessions MCU</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-198">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-198">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-199">Nombre total de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="5db7f-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5db7f-200"><strong>Taux d’échec MCU</strong></span><span class="sxs-lookup"><span data-stu-id="5db7f-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="5db7f-201">Non</span><span class="sxs-lookup"><span data-stu-id="5db7f-201">No</span></span></p></td>
<td><p><span data-ttu-id="5db7f-202">Pourcentage de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="5db7f-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

