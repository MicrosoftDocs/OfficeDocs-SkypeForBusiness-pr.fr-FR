---
title: 'Lync Server 2013 : rapport de synthèse de conférence RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="2b2f5-102">Rapport de synthèse de conférence RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2f5-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b2f5-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2b2f5-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2b2f5-104">Dans Microsoft Lync Server 2013, une conférence RTC est une conférence dans laquelle au moins un participant se connecte à la partie audio à l’aide d’un téléphone RTC (réseau téléphonique commuté public).</span><span class="sxs-lookup"><span data-stu-id="2b2f5-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="2b2f5-105">(Un téléphone PSTN est une « ligne fixe », un téléphone cellulaire ou tout autre téléphone qui n’utilise pas le protocole voix sur IP.) Bien qu’appelées conférences RTC dans les rapports de surveillance, ces conférences sont peut-être plus connues sous le nom de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="2b2f5-p102">Le rapport de synthèse de conférence PSTN fournit des informations sur toutes les conférences PSTN qui ont lieu au sein de votre organisation (c’est-à-dire, toutes les conférences comportant au moins un utilisateur connecté). Ce rapport comprend des informations sur le nombre total de conférences PSTN, le nombre total de personnes ayant participé à ces conférences, et, peut-être plus important, le nombre total d’utilisateurs connectés (la mesure Nombre total de participants PSTN).</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="2b2f5-108">Accès au rapport de synthèse de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="2b2f5-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="2b2f5-p103">Le rapport de synthèse de conférence PSTN est accessible uniquement à partir de la page d’accueil Rapports de surveillance. Ce rapport n’est lié à aucun autre rapport. Vous ne pouvez pas obtenir d’informations détaillées sur les appels pour une conférence PSTN, en partie parce que les points de terminaison individuels sont responsables de l’envoi de ces informations. Les téléphones PSTN ne sont pas capables d’effectuer le suivi ou d’envoyer des informations détaillées sur les appels.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="2b2f5-113">Utilisation efficace du rapport de synthèse de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="2b2f5-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="2b2f5-114">Pour déterminer le pourcentage de toutes vos conférences qui incluent des utilisateurs de rendez-vous, comparez la valeur de la mesure nombre total de conférences RTC avec la mesure nombre total de conférences trouvées dans le [rapport de synthèse de conférence dans Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="2b2f5-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="2b2f5-p104">Si les conférences PSTN que vous vous attendiez à voir ne s’affichent pas, n’oubliez pas que la possibilité d’organiser une conférence qui autorise les utilisateurs connectés dépend de la stratégie de conférence assignée à un utilisateur : si peu d’utilisateurs sont autorisés à organiser des conférences PSTN, vous verrez peu de conférences PSTN. Vous pouvez vérifier rapidement les stratégies de conférence qui autorisent les utilisateurs à planifier des conférences PSTN en exécutant la commande suivante avec Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p104">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences. You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="2b2f5-117">Les données retournées se présentent ainsi :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="2b2f5-118">Des données semblables à ceci sont alors retournées :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2b2f5-119">Filtres</span><span class="sxs-lookup"><span data-stu-id="2b2f5-119">Filters</span></span>

<span data-ttu-id="2b2f5-p105">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse des conférences PSTN vous permet de choisir la façon dont les données doivent être groupées. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the PSTN Conference Summary Report enables you to choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2b2f5-123">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des conférences PSTN.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="2b2f5-124">Filtres du rapport de synthèse des conférences PSTN</span><span class="sxs-lookup"><span data-stu-id="2b2f5-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b2f5-125">Nom</span><span class="sxs-lookup"><span data-stu-id="2b2f5-125">Name</span></span></th>
<th><span data-ttu-id="2b2f5-126">Description</span><span class="sxs-lookup"><span data-stu-id="2b2f5-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b2f5-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2b2f5-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2b2f5-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2b2f5-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2b2f5-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2b2f5-133">7/7/2012</span></span></p>
<p><span data-ttu-id="2b2f5-134">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2b2f5-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2b2f5-135">7/3/2012</span></span></p>
<p><span data-ttu-id="2b2f5-136">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2f5-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2b2f5-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2b2f5-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2b2f5-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2b2f5-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2b2f5-143">7/7/2012</span></span></p>
<p><span data-ttu-id="2b2f5-144">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2b2f5-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2b2f5-145">7/3/2012</span></span></p>
<p><span data-ttu-id="2b2f5-146">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2f5-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p110">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b2f5-150">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="2b2f5-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2b2f5-151">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="2b2f5-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2b2f5-152">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="2b2f5-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2b2f5-153">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="2b2f5-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2b2f5-p111">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec le 7/8/2012 comme date de début et le 28/9/2012 comme date de fin, les données s’affichent pour les jours compris entre le 7/8/2012 12:00 et le 7/9/2012 12:00 (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2b2f5-156">Mesures</span><span class="sxs-lookup"><span data-stu-id="2b2f5-156">Metrics</span></span>

<span data-ttu-id="2b2f5-157">Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des conférences PSTN</span><span class="sxs-lookup"><span data-stu-id="2b2f5-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="2b2f5-158">Mesures du rapport de synthèse des conférences PSTN</span><span class="sxs-lookup"><span data-stu-id="2b2f5-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b2f5-159">Nom</span><span class="sxs-lookup"><span data-stu-id="2b2f5-159">Name</span></span></th>
<th><span data-ttu-id="2b2f5-160">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="2b2f5-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2b2f5-161">Description</span><span class="sxs-lookup"><span data-stu-id="2b2f5-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b2f5-162"><strong>Toutes les heures</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="2b2f5-163"><strong>Tous les jours</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="2b2f5-164"><strong>Toutes les semaines</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="2b2f5-165"><strong>Tous les mois</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-166">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-166">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p112">Indique l’intervalle de temps sélectionné. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, une répartition par jour de l’activité d’enregistrement utilisateur est affichée pour cette date.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2f5-170"><strong>Nombre total de conférences PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-171">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-171">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-172">Nombre total de conférences ayant autorisé l’accès de rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2f5-173"><strong>Nombre total de participants</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-174">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-174">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-175">Nombre total de personnes ayant participé à des conférences ayant autorisé l’accès de rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2f5-176"><strong>Nombre total de minutes par conférence A/V</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-177">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-177">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-178">Durée totale de conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2f5-179"><strong>Nombre total de minutes par participant à la conférence A/V</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-180">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-180">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p113">Durée totale de participants audio/vidéo. Par exemple, si un participant a passé cinq minutes dans une conférence A/V et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants de conférences A/V sera de huit minutes.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2f5-183"><strong>Nombre total de participants PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-184">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-184">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-185">Nombre total d’utilisateurs qui se sont connectés à des conférences ayant autorisé l’accès de rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b2f5-186"><strong>Nombre total de minutes par participant PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-187">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-187">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p114">Durée totale de conférence passée par les utilisateurs de rendez-vous. Par exemple, si un participant de rendez-vous a passé cinq minutes dans une conférence et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants PSTN sera de huit minutes.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b2f5-190"><strong>Organisateurs de conférence uniques</strong></span><span class="sxs-lookup"><span data-stu-id="2b2f5-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="2b2f5-191">Non</span><span class="sxs-lookup"><span data-stu-id="2b2f5-191">No</span></span></p></td>
<td><p><span data-ttu-id="2b2f5-p115">Nombre total d’utilisateurs qui ont organisé au moins une conférence ayant autorisé l’accès de rendez-vous. Les utilisateurs qui ont organisé plusieurs conférences sont comptabilisés comme un organisateur unique, tout comme les utilisateurs ayant organisé une seule conférence.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

