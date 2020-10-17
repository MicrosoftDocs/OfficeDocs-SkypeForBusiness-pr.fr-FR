---
title: 'Lync Server 2013 : rapport de tendance des emplacements'
description: 'Lync Server 2013 : rapport de tendance des emplacements.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83035bf81e793416035e1bd90906b3c27e51f7f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572120"
---
# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="f7bf9-103">Rapport de tendance des emplacements dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7bf9-103">Location Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7bf9-104">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f7bf9-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f7bf9-105">Le rapport de tendance générale des emplacements fournit des informations de tendance sur la qualité des appels pour les emplacements réseau.</span><span class="sxs-lookup"><span data-stu-id="f7bf9-105">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="f7bf9-106">Filtres</span><span class="sxs-lookup"><span data-stu-id="f7bf9-106">Filters</span></span>

<span data-ttu-id="f7bf9-p101">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, grâce au rapport de tendance générale des emplacements, vous pouvez filtrer les données retournées selon des éléments précis, tels que le type d’accès (à savoir « accès interne » par comparaison à « accès externe ») ou la connexion réseau câblée/sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour ou semaine.</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="f7bf9-111">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de tendance générale des emplacements.</span><span class="sxs-lookup"><span data-stu-id="f7bf9-111">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="f7bf9-112">Filtres du rapport de tendance générale des emplacements</span><span class="sxs-lookup"><span data-stu-id="f7bf9-112">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7bf9-113">Nom</span><span class="sxs-lookup"><span data-stu-id="f7bf9-113">Name</span></span></th>
<th><span data-ttu-id="f7bf9-114">Description</span><span class="sxs-lookup"><span data-stu-id="f7bf9-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7bf9-115"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f7bf9-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f7bf9-p102">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f7bf9-118">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f7bf9-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f7bf9-p103">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f7bf9-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f7bf9-121">7/7/2012</span></span></p>
<p><span data-ttu-id="f7bf9-122">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f7bf9-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f7bf9-123">7/3/2012</span></span></p>
<p><span data-ttu-id="f7bf9-124">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="f7bf9-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7bf9-125"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f7bf9-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f7bf9-p104">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f7bf9-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f7bf9-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f7bf9-p105">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f7bf9-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f7bf9-131">7/7/2012</span></span></p>
<p><span data-ttu-id="f7bf9-132">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f7bf9-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f7bf9-133">7/3/2012</span></span></p>
<p><span data-ttu-id="f7bf9-134">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="f7bf9-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7bf9-135"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="f7bf9-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f7bf9-p106">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7bf9-138">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="f7bf9-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-139">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="f7bf9-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-140">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="f7bf9-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f7bf9-p107">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 1/1/2011 et une date de fin le 28/2/2011, les données s’affichent pour les jours compris entre le 1/8/2011 à minuit et le 1/9/2011 à minuit (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7bf9-143"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="f7bf9-143"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="f7bf9-p108">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7bf9-146">Tous les</span><span class="sxs-lookup"><span data-stu-id="f7bf9-146">[All]</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-147">Interne</span><span class="sxs-lookup"><span data-stu-id="f7bf9-147">Internal</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-148">Externe</span><span class="sxs-lookup"><span data-stu-id="f7bf9-148">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7bf9-149"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="f7bf9-149"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="f7bf9-p109">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7bf9-152">Tous les</span><span class="sxs-lookup"><span data-stu-id="f7bf9-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-153">Circuit</span><span class="sxs-lookup"><span data-stu-id="f7bf9-153">Wired</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-154">Fil</span><span class="sxs-lookup"><span data-stu-id="f7bf9-154">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7bf9-155"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="f7bf9-155"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f7bf9-p110">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7bf9-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7bf9-158">Tous les</span><span class="sxs-lookup"><span data-stu-id="f7bf9-158">[All]</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-159">VPN</span><span class="sxs-lookup"><span data-stu-id="f7bf9-159">VPN</span></span></p></li>
<li><p><span data-ttu-id="f7bf9-160">Non VPN</span><span class="sxs-lookup"><span data-stu-id="f7bf9-160">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

