---
title: 'Lync Server 2013 : rapport vocal et vidéo d’égal-à-égal'
description: 'Lync Server 2013 : rapport vocal et vidéo d’égal-à-égal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557270"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="9b239-103">Rapport vocal et vidéo d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b239-103">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b239-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9b239-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9b239-p101">Le rapport vocal et vidéo d’égal-à-égal offre un examen détaillé de la distribution des appels vocaux et vidéo sur une période donnée (par exemple, les appels par heure ou par jour). Il vous offre également la possibilité de voir tous les appels vocaux et vidéo émis, ou de voir uniquement les appels ayant abouti ou échoué. Le rapport fournit les informations d’appels réparties dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="9b239-108">Appels par pool</span><span class="sxs-lookup"><span data-stu-id="9b239-108">Calls per pool</span></span>

  - <span data-ttu-id="9b239-109">Appels par type d’appel (par exemple, un appel Lync à Lync et un appel Lync à une personne sur le réseau RTC)</span><span class="sxs-lookup"><span data-stu-id="9b239-109">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="9b239-110">Appels par type d’accès (utilisateurs connectés au réseau interne par opposition aux utilisateurs connectés au réseau externe)</span><span class="sxs-lookup"><span data-stu-id="9b239-110">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="9b239-111">Appels par serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9b239-111">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="9b239-112">Pour accéder au rapport vocal et vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-112">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="9b239-113">Vous pouvez accéder au rapport vocal et vidéo d’égal-à-égal en ouvrant simplement le rapport de synthèse d’activité d’égal-à-égal, puis en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-113">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="9b239-114">Nombre total de sessions d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-114">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="9b239-115">Nombre total de minutes audio d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-115">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="9b239-116">Nombre total de sessions vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-116">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="9b239-117">Nombre total de minutes vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-117">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="9b239-118">Pour une utilisation optimale du rapport vocal et vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-118">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="9b239-p102">Vous pouvez filtrer le rapport vocal et vidéo d’égal-à-égal de différentes manières. Cependant, ces options de filtre sont masquées par défaut. Pour afficher les options de filtre disponibles, cliquez sur le bouton **Afficher/Masquer les paramètres** dans le coin supérieur droit de la fenêtre du rapport.</span><span class="sxs-lookup"><span data-stu-id="9b239-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9b239-122">Filtres</span><span class="sxs-lookup"><span data-stu-id="9b239-122">Filters</span></span>

<span data-ttu-id="9b239-p103">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport vocal et vidéo d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="9b239-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="9b239-125">Filtres du rapport vocal et vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="9b239-125">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b239-126">Nom</span><span class="sxs-lookup"><span data-stu-id="9b239-126">Name</span></span></th>
<th><span data-ttu-id="9b239-127">Description</span><span class="sxs-lookup"><span data-stu-id="9b239-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b239-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-p104">Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b239-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9b239-131">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9b239-131">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9b239-p105">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="9b239-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9b239-134">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9b239-134">7/7/2012</span></span></p>
<p><span data-ttu-id="9b239-135">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="9b239-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9b239-136">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9b239-136">7/3/2012</span></span></p>
<p><span data-ttu-id="9b239-137">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="9b239-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-p106">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b239-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9b239-141">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9b239-141">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9b239-p107">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="9b239-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9b239-144">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9b239-144">7/7/2012</span></span></p>
<p><span data-ttu-id="9b239-145">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="9b239-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9b239-146">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9b239-146">7/3/2012</span></span></p>
<p><span data-ttu-id="9b239-147">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="9b239-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b239-148"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-148"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-p108">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b239-151">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="9b239-151">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9b239-152">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="9b239-152">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9b239-153">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="9b239-153">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9b239-154">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="9b239-154">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="9b239-p109">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="9b239-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-157"><strong>Type de média</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-157"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-p110">Indique le type de média utilisé dans la session. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b239-160">Les deux</span><span class="sxs-lookup"><span data-stu-id="9b239-160">Both</span></span></p></li>
<li><p><span data-ttu-id="9b239-161">Audio</span><span class="sxs-lookup"><span data-stu-id="9b239-161">Audio</span></span></p></li>
<li><p><span data-ttu-id="9b239-162">Vidéo</span><span class="sxs-lookup"><span data-stu-id="9b239-162">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b239-163"><strong>Distribution des appels</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-163"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-p111">Indique la réussite ou l’échec de la session. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b239-166">Tous les</span><span class="sxs-lookup"><span data-stu-id="9b239-166">[All]</span></span></p></li>
<li><p><span data-ttu-id="9b239-167">Appels ayant abouti</span><span class="sxs-lookup"><span data-stu-id="9b239-167">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="9b239-168">Appels n’ayant pas abouti</span><span class="sxs-lookup"><span data-stu-id="9b239-168">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-169"><strong>Établir un rapport par</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-169"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-p112">Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b239-172">Nombre de sessions</span><span class="sxs-lookup"><span data-stu-id="9b239-172">Session count</span></span></p></li>
<li><p><span data-ttu-id="9b239-173">Minutes d’appel</span><span class="sxs-lookup"><span data-stu-id="9b239-173">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="9b239-174">Mesures de l’activité vocale et vidéo d’égal à égal par pool</span><span class="sxs-lookup"><span data-stu-id="9b239-174">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="9b239-175">Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque pool.</span><span class="sxs-lookup"><span data-stu-id="9b239-175">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="9b239-176">Mesures de l’activité vocale et vidéo d’égal à égal par pool</span><span class="sxs-lookup"><span data-stu-id="9b239-176">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b239-177">Nom</span><span class="sxs-lookup"><span data-stu-id="9b239-177">Name</span></span></th>
<th><span data-ttu-id="9b239-178">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="9b239-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9b239-179">Description</span><span class="sxs-lookup"><span data-stu-id="9b239-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b239-180"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-180"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-181">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-181">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-182">Nom du pool de serveurs d’inscriptions ou du serveur Edge utilisé pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="9b239-182">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-183"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-184">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-184">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-185">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="9b239-185">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b239-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-187">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-187">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-188">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="9b239-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="9b239-189">Mesures de l’activité vocale et vidéo d’égal à égal par type d’appel</span><span class="sxs-lookup"><span data-stu-id="9b239-189">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="9b239-190">Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque type d’appel émis.</span><span class="sxs-lookup"><span data-stu-id="9b239-190">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="9b239-191">Mesures de l’activité vocale et vidéo d’égal à égal par type d’appel</span><span class="sxs-lookup"><span data-stu-id="9b239-191">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b239-192">Nom</span><span class="sxs-lookup"><span data-stu-id="9b239-192">Name</span></span></th>
<th><span data-ttu-id="9b239-193">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="9b239-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9b239-194">Description</span><span class="sxs-lookup"><span data-stu-id="9b239-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b239-195"><strong>Type d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-195"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-196">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-196">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-p113">Indique le type d’appel émis. Les valeurs correspondent à l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b239-199">UC à UC</span><span class="sxs-lookup"><span data-stu-id="9b239-199">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="9b239-200">UC-RTC</span><span class="sxs-lookup"><span data-stu-id="9b239-200">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="9b239-201">RTC à UC</span><span class="sxs-lookup"><span data-stu-id="9b239-201">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="9b239-202">RTC à PSTN</span><span class="sxs-lookup"><span data-stu-id="9b239-202">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-203"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-203"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-204">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-204">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-205">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="9b239-205">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b239-206"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-206"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-207">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-207">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-208">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="9b239-208">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="9b239-209">Mesures de l’activité vocale et vidéo d’égal à égal par type d’accès</span><span class="sxs-lookup"><span data-stu-id="9b239-209">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="9b239-210">Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque type d’accès réseau.</span><span class="sxs-lookup"><span data-stu-id="9b239-210">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="9b239-211">Mesures de l’activité vocale et vidéo d’égal à égal par type d’accès</span><span class="sxs-lookup"><span data-stu-id="9b239-211">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b239-212">Nom</span><span class="sxs-lookup"><span data-stu-id="9b239-212">Name</span></span></th>
<th><span data-ttu-id="9b239-213">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="9b239-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9b239-214">Description</span><span class="sxs-lookup"><span data-stu-id="9b239-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b239-215"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-215"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-216">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-216">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-p114">Indique si les clients étaient connectés au réseau interne ou au réseau externe au moment de passer l’appel. Les valeurs correspondent généralement à l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b239-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b239-219">Interne</span><span class="sxs-lookup"><span data-stu-id="9b239-219">Internal</span></span></p></li>
<li><p><span data-ttu-id="9b239-220">Externe</span><span class="sxs-lookup"><span data-stu-id="9b239-220">External</span></span></p></li>
<li><p><span data-ttu-id="9b239-221">Mixte</span><span class="sxs-lookup"><span data-stu-id="9b239-221">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-222"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-222"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-223">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-223">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-224">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="9b239-224">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b239-225"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-225"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-226">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-226">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-227">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="9b239-227">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="9b239-228">Mesures de l’activité vocale et vidéo d’égal à égal par serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9b239-228">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="9b239-229">Le tableau suivant répertorie les informations fournies dans le rapport vocal et vidéo d’égal-à-égal pour chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="9b239-229">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="9b239-230">Mesures de l’activité vocale et vidéo d’égal à égal par serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9b239-230">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b239-231">Nom</span><span class="sxs-lookup"><span data-stu-id="9b239-231">Name</span></span></th>
<th><span data-ttu-id="9b239-232">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="9b239-232">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9b239-233">Description</span><span class="sxs-lookup"><span data-stu-id="9b239-233">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b239-234"><strong>Serveur de médiation</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-234"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-235">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-235">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-236">Nom du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="9b239-236">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b239-237"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-237"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-238">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-238">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-239">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="9b239-239">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b239-240"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="9b239-240"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="9b239-241">Non</span><span class="sxs-lookup"><span data-stu-id="9b239-241">No</span></span></p></td>
<td><p><span data-ttu-id="9b239-242">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="9b239-242">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

