---
title: 'Lync Server 2013 : rapport de messagerie instantanée d’égal à égal'
description: 'Lync Server 2013 : rapport de messagerie instantanée d’égal à égal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac6291d0f099af8269ed15f7dc8c654ac944ed0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557290"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="fd7d5-103">Rapport de messagerie instantanée d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7d5-103">Peer-to-Peer IM Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd7d5-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fd7d5-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fd7d5-105">Le rapport de messagerie instantanée d’égal à égal fournit des informations de tendance sur les sessions de messagerie instantanée d’égal à égal, ventilées par pool et par type d’authentification.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-105">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type.</span></span> <span data-ttu-id="fd7d5-106">Le rapport peut indiquer le nombre total de sessions détenues pendant la période spécifiée (par exemple, Day-by-Day ou Hour-on-Hour) ou le nombre total de messages instantanés envoyés au cours de cette période.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-106">The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="fd7d5-107">Accès au rapport de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="fd7d5-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="fd7d5-108">Vous pouvez accéder au rapport de messagerie instantanée d’égal à égal uniquement en ouvrant le [rapport de synthèse des activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) , puis en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="fd7d5-109">Nombre total de sessions de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="fd7d5-109">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="fd7d5-110">Nombre total de messages de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="fd7d5-110">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="fd7d5-111">Utilisation optimale du rapport de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="fd7d5-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="fd7d5-112">Par défaut, le rapport de messagerie instantanée d’égal à égal vous indique le nombre de messages par heure (ou jour, selon vos paramètres).</span><span class="sxs-lookup"><span data-stu-id="fd7d5-112">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings).</span></span> <span data-ttu-id="fd7d5-113">Toutefois, vous pouvez également choisir d’afficher le jour par sessions par heure.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-113">However, you can also choose to view the day by sessions per hour.</span></span> <span data-ttu-id="fd7d5-114">Pour ce faire, cliquez sur **Masquer/afficher les paramètres** dans le coin supérieur droit de la fenêtre rapports, puis cliquez sur **nombre de sessions** dans la liste **rapport par** .</span><span class="sxs-lookup"><span data-stu-id="fd7d5-114">To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fd7d5-115">Filtres</span><span class="sxs-lookup"><span data-stu-id="fd7d5-115">Filters</span></span>

<span data-ttu-id="fd7d5-116">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-116">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="fd7d5-117">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de messagerie instantanée d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-117">The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="fd7d5-118">Filtres de rapport de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="fd7d5-118">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd7d5-119">Nom</span><span class="sxs-lookup"><span data-stu-id="fd7d5-119">Name</span></span></th>
<th><span data-ttu-id="fd7d5-120">Description</span><span class="sxs-lookup"><span data-stu-id="fd7d5-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd7d5-121"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-p104">Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fd7d5-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fd7d5-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fd7d5-p105">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fd7d5-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fd7d5-127">7/7/2012</span></span></p>
<p><span data-ttu-id="fd7d5-128">Pour afficher les valeurs par semaine ou mois, entrez une date située n’importe où dans la semaine ou le mois (vous n’avez pas besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fd7d5-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fd7d5-129">7/3/2012</span></span></p>
<p><span data-ttu-id="fd7d5-130">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd7d5-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-p106">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fd7d5-134">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="fd7d5-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fd7d5-p107">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fd7d5-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fd7d5-137">7/7/2012</span></span></p>
<p><span data-ttu-id="fd7d5-138">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fd7d5-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fd7d5-139">7/3/2012</span></span></p>
<p><span data-ttu-id="fd7d5-140">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd7d5-141"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-141"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-p108">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd7d5-144">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="fd7d5-144">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fd7d5-145">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="fd7d5-145">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fd7d5-146">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="fd7d5-146">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fd7d5-147">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="fd7d5-147">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="fd7d5-148">Si les dates de début et de fin dépassent le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-148">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="fd7d5-149">Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début 7/8/2012 et une date de fin 28/9/2012, les données sont affichées pour les jours 7/8/2012 12:00 AM à 7/9/2012 12:00 AM (c’est-à-dire un total de 31 jours de données pertinentes).</span><span class="sxs-lookup"><span data-stu-id="fd7d5-149">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd7d5-150"><strong>Établir un rapport par</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-150"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-p110">Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd7d5-153">Nombre de sessions</span><span class="sxs-lookup"><span data-stu-id="fd7d5-153">Session count</span></span></p></li>
<li><p><span data-ttu-id="fd7d5-154">Nombre de messages</span><span class="sxs-lookup"><span data-stu-id="fd7d5-154">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="fd7d5-155">Mesures pour une session de messagerie instantanée d’égal à égal par pool</span><span class="sxs-lookup"><span data-stu-id="fd7d5-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="fd7d5-156">Le tableau suivant répertorie les informations fournies dans le rapport de messagerie instantanée d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="fd7d5-157">Mesures pour une session de messagerie instantanée d’égal à égal par pool</span><span class="sxs-lookup"><span data-stu-id="fd7d5-157">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd7d5-158">Nom</span><span class="sxs-lookup"><span data-stu-id="fd7d5-158">Name</span></span></th>
<th><span data-ttu-id="fd7d5-159">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="fd7d5-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fd7d5-160">Description</span><span class="sxs-lookup"><span data-stu-id="fd7d5-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd7d5-161"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-161"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-162">Non</span><span class="sxs-lookup"><span data-stu-id="fd7d5-162">No</span></span></p></td>
<td><p><span data-ttu-id="fd7d5-163">Nom du pool de serveurs d’inscriptions ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-163">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd7d5-164"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-164"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-165">Non</span><span class="sxs-lookup"><span data-stu-id="fd7d5-165">No</span></span></p></td>
<td><p><span data-ttu-id="fd7d5-166">Date et heure des sessions.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-166">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd7d5-167"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-167"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-168">Non</span><span class="sxs-lookup"><span data-stu-id="fd7d5-168">No</span></span></p></td>
<td><p><span data-ttu-id="fd7d5-169">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-169">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="fd7d5-170">Mesures de la session de messagerie instantanée d’égal à égal par type d’authentification</span><span class="sxs-lookup"><span data-stu-id="fd7d5-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="fd7d5-171">Le tableau suivant répertorie les informations fournies dans le rapport de messagerie instantanée d’égal à égal pour chaque type d’authentification utilisé par les participants dans une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="fd7d5-172">Mesures de la session de messagerie instantanée d’égal à égal par type d’authentification</span><span class="sxs-lookup"><span data-stu-id="fd7d5-172">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd7d5-173">Nom</span><span class="sxs-lookup"><span data-stu-id="fd7d5-173">Name</span></span></th>
<th><span data-ttu-id="fd7d5-174">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="fd7d5-174">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fd7d5-175">Description</span><span class="sxs-lookup"><span data-stu-id="fd7d5-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd7d5-176"><strong>Type d’authentification type</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-176"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-177">Non</span><span class="sxs-lookup"><span data-stu-id="fd7d5-177">No</span></span></p></td>
<td><p><span data-ttu-id="fd7d5-178">Type d’authentification utilisé par les participants de la session.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-178">Type of authentication used by the session participants.</span></span> <span data-ttu-id="fd7d5-179">Les valeurs correspondent généralement à l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="fd7d5-179">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd7d5-180">Entreprise</span><span class="sxs-lookup"><span data-stu-id="fd7d5-180">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="fd7d5-181">Fédération</span><span class="sxs-lookup"><span data-stu-id="fd7d5-181">Federated</span></span></p></li>
<li><p><span data-ttu-id="fd7d5-182">PIC</span><span class="sxs-lookup"><span data-stu-id="fd7d5-182">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd7d5-183"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-184">Non</span><span class="sxs-lookup"><span data-stu-id="fd7d5-184">No</span></span></p></td>
<td><p><span data-ttu-id="fd7d5-185">Date et heure des sessions.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-185">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd7d5-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="fd7d5-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="fd7d5-187">Non</span><span class="sxs-lookup"><span data-stu-id="fd7d5-187">No</span></span></p></td>
<td><p><span data-ttu-id="fd7d5-188">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="fd7d5-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

