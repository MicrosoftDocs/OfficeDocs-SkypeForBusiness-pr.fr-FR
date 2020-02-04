---
title: 'Lync Server 2013 : rapport de messagerie instantanée d’égal à égal'
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
ms.openlocfilehash: 359c3fad7f41d990ffdba3aa533d0d5f10456665
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="89155-102">Rapport de messagerie instantanée d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89155-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89155-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="89155-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="89155-p101">Le rapport de messagerie instantanée P2P fournit les tendances des sessions de messagerie instantanée P2P, par pool et par type d’authentification. Le rapport peut afficher le nombre total de sessions tenues pendant une période donnée (par exemple, jour par jour ou heure par heure) ou le nombre total de messages instantanés envoyés au cours de cette période.</span><span class="sxs-lookup"><span data-stu-id="89155-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="89155-106">Accès au rapport de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="89155-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="89155-107">Vous pouvez accéder au rapport de messagerie instantanée d’égal à égal uniquement en ouvrant le [rapport de synthèse des activités d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) , puis en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="89155-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="89155-108">Nombre total de sessions de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="89155-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="89155-109">Nombre total de messages de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="89155-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="89155-110">Utilisation optimale du rapport de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="89155-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="89155-p102">Par défaut, le rapport de messagerie instantanée P2P vous montre le nombre de messages par heure (ou par jour, selon vos paramètres). Vous pouvez toutefois également afficher le nombre de sessions par heure sur une journée. Pour ce faire, cliquez sur **Afficher/Masquer les paramètres** dans l’angle supérieur droit de la fenêtre Rapports, puis cliquez sur **Nombre de sessions** dans la liste **Établir un rapport par**.</span><span class="sxs-lookup"><span data-stu-id="89155-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="89155-114">Filtres</span><span class="sxs-lookup"><span data-stu-id="89155-114">Filters</span></span>

<span data-ttu-id="89155-p103">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport de messagerie instantanée P2P.</span><span class="sxs-lookup"><span data-stu-id="89155-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="89155-117">Filtres du rapport de messagerie instantanée P2P</span><span class="sxs-lookup"><span data-stu-id="89155-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89155-118">Nom</span><span class="sxs-lookup"><span data-stu-id="89155-118">Name</span></span></th>
<th><span data-ttu-id="89155-119">Description</span><span class="sxs-lookup"><span data-stu-id="89155-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89155-120"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="89155-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-p104">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="89155-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="89155-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="89155-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="89155-p105">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="89155-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="89155-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="89155-126">7/7/2012</span></span></p>
<p><span data-ttu-id="89155-127">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="89155-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="89155-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="89155-128">7/3/2012</span></span></p>
<p><span data-ttu-id="89155-129">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="89155-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89155-130"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="89155-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-p106">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="89155-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="89155-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="89155-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="89155-p107">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="89155-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="89155-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="89155-136">7/7/2012</span></span></p>
<p><span data-ttu-id="89155-137">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="89155-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="89155-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="89155-138">7/3/2012</span></span></p>
<p><span data-ttu-id="89155-139">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="89155-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89155-140"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="89155-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-p108">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="89155-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="89155-143">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="89155-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="89155-144">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="89155-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="89155-145">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="89155-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="89155-146">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="89155-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="89155-147">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="89155-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="89155-148">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="89155-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89155-149"><strong>Établir un rapport par</strong></span><span class="sxs-lookup"><span data-stu-id="89155-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-p110">Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="89155-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="89155-152">Nombre de sessions</span><span class="sxs-lookup"><span data-stu-id="89155-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="89155-153">Nombre de messages</span><span class="sxs-lookup"><span data-stu-id="89155-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="89155-154">Mesure d’une session de messagerie instantanée P2P par pool</span><span class="sxs-lookup"><span data-stu-id="89155-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="89155-155">Le tableau qui suit répertorie les informations fournies dans le rapport de messagerie instantanée P2P.</span><span class="sxs-lookup"><span data-stu-id="89155-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="89155-156">Mesure d’une session de messagerie instantanée P2P par pool</span><span class="sxs-lookup"><span data-stu-id="89155-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89155-157">Nom</span><span class="sxs-lookup"><span data-stu-id="89155-157">Name</span></span></th>
<th><span data-ttu-id="89155-158">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="89155-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="89155-159">Description</span><span class="sxs-lookup"><span data-stu-id="89155-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89155-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="89155-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-161">Non</span><span class="sxs-lookup"><span data-stu-id="89155-161">No</span></span></p></td>
<td><p><span data-ttu-id="89155-162">Nom du pool d’inscriptions ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="89155-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89155-163"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="89155-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-164">Non</span><span class="sxs-lookup"><span data-stu-id="89155-164">No</span></span></p></td>
<td><p><span data-ttu-id="89155-165">Date et heure des sessions.</span><span class="sxs-lookup"><span data-stu-id="89155-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89155-166"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="89155-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-167">Non</span><span class="sxs-lookup"><span data-stu-id="89155-167">No</span></span></p></td>
<td><p><span data-ttu-id="89155-168">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="89155-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="89155-169">Mesure d’une session de messagerie instantanée P2P par type d’authentification</span><span class="sxs-lookup"><span data-stu-id="89155-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="89155-170">Le tableau ci-dessous dresse la liste des informations fournies dans le rapport de messagerie instantanée P2P pour chaque type d’authentification utilisé par les participants dans une session P2P.</span><span class="sxs-lookup"><span data-stu-id="89155-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="89155-171">Mesure d’une session de messagerie instantanée P2P par type d’authentification</span><span class="sxs-lookup"><span data-stu-id="89155-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89155-172">Nom</span><span class="sxs-lookup"><span data-stu-id="89155-172">Name</span></span></th>
<th><span data-ttu-id="89155-173">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="89155-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="89155-174">Description</span><span class="sxs-lookup"><span data-stu-id="89155-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89155-175"><strong>Type d’authentification</strong></span><span class="sxs-lookup"><span data-stu-id="89155-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-176">Non</span><span class="sxs-lookup"><span data-stu-id="89155-176">No</span></span></p></td>
<td><p><span data-ttu-id="89155-p111">Type d’authentification utilisé par les participants de la session. Les valeurs sont généralement l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="89155-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="89155-179">Enterprise</span><span class="sxs-lookup"><span data-stu-id="89155-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="89155-180">Federated</span><span class="sxs-lookup"><span data-stu-id="89155-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="89155-181">PIC</span><span class="sxs-lookup"><span data-stu-id="89155-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89155-182"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="89155-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-183">Non</span><span class="sxs-lookup"><span data-stu-id="89155-183">No</span></span></p></td>
<td><p><span data-ttu-id="89155-184">Date et heure des sessions.</span><span class="sxs-lookup"><span data-stu-id="89155-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89155-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="89155-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="89155-186">Non</span><span class="sxs-lookup"><span data-stu-id="89155-186">No</span></span></p></td>
<td><p><span data-ttu-id="89155-187">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="89155-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

