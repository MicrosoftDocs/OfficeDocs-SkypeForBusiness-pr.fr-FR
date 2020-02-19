---
title: 'Lync Server 2013 : rapport vocal et vidéo d’égal-à-égal'
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
ms.openlocfilehash: 880104d0809b0135c74c72a80eefb7d4bb0ed709
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="c8d14-102">Rapport vocal et vidéo d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8d14-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8d14-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c8d14-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c8d14-p101">Le rapport vocal et vidéo d’égal-à-égal offre un examen détaillé de la distribution des appels vocaux et vidéo sur une période donnée (par exemple, les appels par heure ou par jour). Il vous offre également la possibilité de voir tous les appels vocaux et vidéo émis, ou de voir uniquement les appels ayant abouti ou échoué. Le rapport fournit les informations d’appels réparties dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="c8d14-107">Appels par pool</span><span class="sxs-lookup"><span data-stu-id="c8d14-107">Calls per pool</span></span>

  - <span data-ttu-id="c8d14-108">Appels par type d’appel (par exemple, un appel Lync à Lync et un appel Lync à une personne sur le réseau RTC)</span><span class="sxs-lookup"><span data-stu-id="c8d14-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="c8d14-109">Appels par type d’accès (utilisateurs connectés au réseau interne par opposition aux utilisateurs connectés au réseau externe)</span><span class="sxs-lookup"><span data-stu-id="c8d14-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="c8d14-110">Appels par serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c8d14-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="c8d14-111">Pour accéder au rapport vocal et vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="c8d14-112">Vous pouvez accéder au rapport vocal et vidéo d’égal-à-égal en ouvrant simplement le rapport de synthèse d’activité d’égal-à-égal, puis en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="c8d14-113">Nombre total de sessions d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="c8d14-114">Nombre total de minutes audio d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="c8d14-115">Nombre total de sessions vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="c8d14-116">Nombre total de minutes vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="c8d14-117">Pour une utilisation optimale du rapport vocal et vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="c8d14-p102">Vous pouvez filtrer le rapport vocal et vidéo d’égal-à-égal de différentes manières. Cependant, ces options de filtre sont masquées par défaut. Pour afficher les options de filtre disponibles, cliquez sur le bouton **Afficher/Masquer les paramètres** dans le coin supérieur droit de la fenêtre du rapport.</span><span class="sxs-lookup"><span data-stu-id="c8d14-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c8d14-121">Filtres</span><span class="sxs-lookup"><span data-stu-id="c8d14-121">Filters</span></span>

<span data-ttu-id="c8d14-p103">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport vocal et vidéo d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="c8d14-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="c8d14-124">Filtres du rapport vocal et vidéo d’égal-à-égal</span><span class="sxs-lookup"><span data-stu-id="c8d14-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d14-125">Nom</span><span class="sxs-lookup"><span data-stu-id="c8d14-125">Name</span></span></th>
<th><span data-ttu-id="c8d14-126">Description</span><span class="sxs-lookup"><span data-stu-id="c8d14-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-p104">Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c8d14-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c8d14-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c8d14-p105">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c8d14-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c8d14-133">7/7/2012</span></span></p>
<p><span data-ttu-id="c8d14-134">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c8d14-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c8d14-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c8d14-135">7/3/2012</span></span></p>
<p><span data-ttu-id="c8d14-136">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c8d14-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-p106">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c8d14-140">07/07/2012 13h</span><span class="sxs-lookup"><span data-stu-id="c8d14-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c8d14-p107">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c8d14-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c8d14-143">7/7/2012</span></span></p>
<p><span data-ttu-id="c8d14-144">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="c8d14-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c8d14-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c8d14-145">7/3/2012</span></span></p>
<p><span data-ttu-id="c8d14-146">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="c8d14-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-p108">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8d14-150">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="c8d14-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c8d14-151">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="c8d14-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c8d14-152">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="c8d14-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c8d14-153">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="c8d14-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c8d14-p109">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="c8d14-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-156"><strong>Type de média</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-p110">Indique le type de média utilisé dans la session. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8d14-159">Les deux</span><span class="sxs-lookup"><span data-stu-id="c8d14-159">Both</span></span></p></li>
<li><p><span data-ttu-id="c8d14-160">Audio</span><span class="sxs-lookup"><span data-stu-id="c8d14-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="c8d14-161">Vidéo</span><span class="sxs-lookup"><span data-stu-id="c8d14-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-162"><strong>Distribution des appels</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-p111">Indique la réussite ou l’échec de la session. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8d14-165">Tous les</span><span class="sxs-lookup"><span data-stu-id="c8d14-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="c8d14-166">Appels ayant abouti</span><span class="sxs-lookup"><span data-stu-id="c8d14-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="c8d14-167">Appels n’ayant pas abouti</span><span class="sxs-lookup"><span data-stu-id="c8d14-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-168"><strong>Établir un rapport par</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-p112">Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8d14-171">Nombre de sessions</span><span class="sxs-lookup"><span data-stu-id="c8d14-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="c8d14-172">Minutes d’appel</span><span class="sxs-lookup"><span data-stu-id="c8d14-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="c8d14-173">Mesures de l’activité vocale et vidéo d’égal à égal par pool</span><span class="sxs-lookup"><span data-stu-id="c8d14-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="c8d14-174">Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque pool.</span><span class="sxs-lookup"><span data-stu-id="c8d14-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="c8d14-175">Mesures de l’activité vocale et vidéo d’égal à égal par pool</span><span class="sxs-lookup"><span data-stu-id="c8d14-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d14-176">Nom</span><span class="sxs-lookup"><span data-stu-id="c8d14-176">Name</span></span></th>
<th><span data-ttu-id="c8d14-177">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c8d14-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8d14-178">Description</span><span class="sxs-lookup"><span data-stu-id="c8d14-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-180">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-180">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-181">Nom du pool de serveurs d’inscriptions ou du serveur Edge utilisé pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="c8d14-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-182"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-183">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-183">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-184">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="c8d14-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-186">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-186">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-187">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="c8d14-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="c8d14-188">Mesures de l’activité vocale et vidéo d’égal à égal par type d’appel</span><span class="sxs-lookup"><span data-stu-id="c8d14-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="c8d14-189">Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque type d’appel émis.</span><span class="sxs-lookup"><span data-stu-id="c8d14-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="c8d14-190">Mesures de l’activité vocale et vidéo d’égal à égal par type d’appel</span><span class="sxs-lookup"><span data-stu-id="c8d14-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d14-191">Nom</span><span class="sxs-lookup"><span data-stu-id="c8d14-191">Name</span></span></th>
<th><span data-ttu-id="c8d14-192">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c8d14-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8d14-193">Description</span><span class="sxs-lookup"><span data-stu-id="c8d14-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-194"><strong>Type d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-195">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-195">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-p113">Indique le type d’appel émis. Les valeurs correspondent à l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8d14-198">UC à UC</span><span class="sxs-lookup"><span data-stu-id="c8d14-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="c8d14-199">UC-RTC</span><span class="sxs-lookup"><span data-stu-id="c8d14-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="c8d14-200">RTC à UC</span><span class="sxs-lookup"><span data-stu-id="c8d14-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="c8d14-201">RTC à PSTN</span><span class="sxs-lookup"><span data-stu-id="c8d14-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-202"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-203">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-203">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-204">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="c8d14-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-206">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-206">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-207">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="c8d14-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="c8d14-208">Mesures de l’activité vocale et vidéo d’égal à égal par type d’accès</span><span class="sxs-lookup"><span data-stu-id="c8d14-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="c8d14-209">Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque type d’accès réseau.</span><span class="sxs-lookup"><span data-stu-id="c8d14-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="c8d14-210">Mesures de l’activité vocale et vidéo d’égal à égal par type d’accès</span><span class="sxs-lookup"><span data-stu-id="c8d14-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d14-211">Nom</span><span class="sxs-lookup"><span data-stu-id="c8d14-211">Name</span></span></th>
<th><span data-ttu-id="c8d14-212">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c8d14-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8d14-213">Description</span><span class="sxs-lookup"><span data-stu-id="c8d14-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-214"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-215">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-215">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-p114">Indique si les clients étaient connectés au réseau interne ou au réseau externe au moment de passer l’appel. Les valeurs correspondent généralement à l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8d14-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c8d14-218">Interne</span><span class="sxs-lookup"><span data-stu-id="c8d14-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="c8d14-219">Externe</span><span class="sxs-lookup"><span data-stu-id="c8d14-219">External</span></span></p></li>
<li><p><span data-ttu-id="c8d14-220">Mixte</span><span class="sxs-lookup"><span data-stu-id="c8d14-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-221"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-222">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-222">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-223">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="c8d14-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-225">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-225">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-226">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="c8d14-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="c8d14-227">Mesures de l’activité vocale et vidéo d’égal à égal par serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c8d14-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="c8d14-228">Le tableau suivant répertorie les informations fournies dans le rapport vocal et vidéo d’égal-à-égal pour chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c8d14-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="c8d14-229">Mesures de l’activité vocale et vidéo d’égal à égal par serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c8d14-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d14-230">Nom</span><span class="sxs-lookup"><span data-stu-id="c8d14-230">Name</span></span></th>
<th><span data-ttu-id="c8d14-231">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="c8d14-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c8d14-232">Description</span><span class="sxs-lookup"><span data-stu-id="c8d14-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-233"><strong>Serveur de médiation</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-234">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-234">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-235">Nom du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c8d14-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d14-236"><strong>Date/Heure</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-237">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-237">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-238">Date et heure auxquelles l’appel s’est produit.</span><span class="sxs-lookup"><span data-stu-id="c8d14-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d14-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="c8d14-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d14-240">Non</span><span class="sxs-lookup"><span data-stu-id="c8d14-240">No</span></span></p></td>
<td><p><span data-ttu-id="c8d14-241">Nombre total de sessions ou de messages.</span><span class="sxs-lookup"><span data-stu-id="c8d14-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

