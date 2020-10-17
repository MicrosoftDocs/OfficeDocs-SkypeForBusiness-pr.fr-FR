---
title: 'Lync Server 2013 : rapport de tendance de la qualité des médias serveur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b40f2c316216b01415b3e58d5d59c97421439d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510301"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="717c5-102">Rapport de tendance de la qualité des médias serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="717c5-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="717c5-103">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="717c5-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="717c5-p101">Le rapport de tendance générale de la qualité des médias serveur vous permet de comparer de façon graphique la qualité de l’expérience sur 5 serveurs maximum, par exemple le volume d’appel, le pourcentage d’appels médiocres, la perte de paquet et la gigue. Cela permet d’identifier plus facilement les serveurs dont les performances sont médiocres, les serveurs qui sont sous-utilisés ou sur-utilisés.</span><span class="sxs-lookup"><span data-stu-id="717c5-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="717c5-106">Accès au rapport de tendance générale de la qualité des médias serveur</span><span class="sxs-lookup"><span data-stu-id="717c5-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="717c5-107">Le rapport de tendance générale de la qualité des médias serveur est accessible à partir de l’un des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="717c5-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="717c5-108">[Rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure tendance)</span><span class="sxs-lookup"><span data-stu-id="717c5-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="717c5-109">[Rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) (en cliquant sur la mesure serveur Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="717c5-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="717c5-110">Si l’appelant ou l’appelé est un serveur, vous pouvez également accéder au rapport de tendance des médias de qualité serveur en cliquant sur le nom du point de terminaison.)</span><span class="sxs-lookup"><span data-stu-id="717c5-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="717c5-111">Utilisation efficace du rapport de tendance de la qualité des médias serveur</span><span class="sxs-lookup"><span data-stu-id="717c5-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="717c5-112">Lorsque vous cliquez sur la mesure tendance dans le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) pour un serveur spécifique, le rapport de tendance de la qualité des médias serveur s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="717c5-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="717c5-113">Cependant, vous obtenez une instance vide de ce rapport ; le serveur que vous sélectionnez ne sera pas affiché à l’écran.</span><span class="sxs-lookup"><span data-stu-id="717c5-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="717c5-114">Vous devez sélectionner ce serveur dans la liste déroulante Serveurs.</span><span class="sxs-lookup"><span data-stu-id="717c5-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="717c5-115">Notez que la liste déroulante Serveurs propose une option Tout sélectionner.</span><span class="sxs-lookup"><span data-stu-id="717c5-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="717c5-116">Cette option ne sera pas disponible si vous avez plus de 5 serveurs, en effet le rapport de tendance de la qualité des médias serveur ne peut afficher que 5 serveurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="717c5-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="717c5-117">Sur les graphiques affichés par le rapport de tendance de la qualité des médias serveur, les points étiquetés volume d’appels et pourcentage d’appels médiocres sont des lien hypertexte ; un clic sur un point de la courbe ouvre une instance du [rapport de liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) affichant le nombre total d’appels (ou d’appels médiocres) pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="717c5-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="717c5-118">Filtres</span><span class="sxs-lookup"><span data-stu-id="717c5-118">Filters</span></span>

<span data-ttu-id="717c5-p104">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de tendance de la qualité des médias serveur.</span><span class="sxs-lookup"><span data-stu-id="717c5-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="717c5-121">Filtres du rapport de tendance de la qualité des médias serveur</span><span class="sxs-lookup"><span data-stu-id="717c5-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="717c5-122">Nom</span><span class="sxs-lookup"><span data-stu-id="717c5-122">Name</span></span></th>
<th><span data-ttu-id="717c5-123">Description</span><span class="sxs-lookup"><span data-stu-id="717c5-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="717c5-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="717c5-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="717c5-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="717c5-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="717c5-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="717c5-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="717c5-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="717c5-130">7/7/2012</span></span></p>
<p><span data-ttu-id="717c5-131">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="717c5-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="717c5-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="717c5-132">7/3/2012</span></span></p>
<p><span data-ttu-id="717c5-133">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="717c5-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="717c5-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="717c5-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="717c5-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="717c5-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="717c5-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="717c5-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="717c5-140">7/7/2012</span></span></p>
<p><span data-ttu-id="717c5-141">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="717c5-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="717c5-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="717c5-142">7/3/2012</span></span></p>
<p><span data-ttu-id="717c5-143">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="717c5-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-144"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p109">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="717c5-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="717c5-147">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="717c5-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="717c5-148">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="717c5-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="717c5-149">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="717c5-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="717c5-p110">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec le 7/8/2012 comme date de début et le 28/9/2012 comme date de fin, les données s’affichent pour les jours compris entre le 7/8/2012 12:00 AM et le 7/9/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="717c5-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-152"><strong>Type de serveur</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p111">Type de serveur de l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="717c5-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="717c5-155">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="717c5-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="717c5-156">Serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="717c5-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="717c5-157">Serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="717c5-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="717c5-158">Passerelle (serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="717c5-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="717c5-159">Passerelle (contournement du serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="717c5-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="717c5-160">Serveur de conférence AS</span><span class="sxs-lookup"><span data-stu-id="717c5-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-161"><strong>Servers</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p112">Nom du serveur de la session ; cette liste déroulante est automatiquement remplie en fonction de la valeur du filtre Type de serveur. Vous pouvez sélectionner jusqu’à 5 serveurs différents lors de la création d’un rapport.</span><span class="sxs-lookup"><span data-stu-id="717c5-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-164"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p113">Indique si le participant était connecté au réseau interne ou à partir d’un réseau externe. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="717c5-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="717c5-167">Tous les</span><span class="sxs-lookup"><span data-stu-id="717c5-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="717c5-168">Interne</span><span class="sxs-lookup"><span data-stu-id="717c5-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="717c5-169">Externe</span><span class="sxs-lookup"><span data-stu-id="717c5-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-170"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p114">Indique le type de réseau auquel le participant était connecté. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="717c5-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="717c5-173">Tous les</span><span class="sxs-lookup"><span data-stu-id="717c5-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="717c5-174">Circuit</span><span class="sxs-lookup"><span data-stu-id="717c5-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="717c5-175">Fil</span><span class="sxs-lookup"><span data-stu-id="717c5-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-p115">Indique si un participant externe utilisait une connexion VPN lors de la session. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="717c5-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="717c5-179">Tous les</span><span class="sxs-lookup"><span data-stu-id="717c5-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="717c5-180">VPN</span><span class="sxs-lookup"><span data-stu-id="717c5-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="717c5-181">Non VPN</span><span class="sxs-lookup"><span data-stu-id="717c5-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="717c5-182">Mesures</span><span class="sxs-lookup"><span data-stu-id="717c5-182">Metrics</span></span>

<span data-ttu-id="717c5-183">Le tableau qui suit répertorie les informations fournies dans le rapport de tendance de la qualité des médias serveur.</span><span class="sxs-lookup"><span data-stu-id="717c5-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="717c5-184">Mesures du rapport de tendance de la qualité des médias serveur</span><span class="sxs-lookup"><span data-stu-id="717c5-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="717c5-185">Nom</span><span class="sxs-lookup"><span data-stu-id="717c5-185">Name</span></span></th>
<th><span data-ttu-id="717c5-186">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="717c5-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="717c5-187">Description</span><span class="sxs-lookup"><span data-stu-id="717c5-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="717c5-188"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-189">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-189">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-190">Nombre total d’appels.</span><span class="sxs-lookup"><span data-stu-id="717c5-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-191"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-192">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-192">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-193">Taux moyen de dégradation de la note MOS (note moyenne d’opinion) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="717c5-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="717c5-194">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée) ; une valeur inférieure ou égale à 0,5 indique une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="717c5-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="717c5-195">Traditionnellement, les notes moyennes d’opinion étaient calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="717c5-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="717c5-196">Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</span><span class="sxs-lookup"><span data-stu-id="717c5-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="717c5-p117">Les valeurs de dégradation élevées peuvent avoir plusieurs causes : une congestion, un dépassement de la bande passante disponible, une congestion/interférence dans la liaison sans fil ou bien la surcharge d’un serveur multimédia ou d’un système d’extrémité. Ces valeurs se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="717c5-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-199"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-200">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-200">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-p118">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="717c5-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-203"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-204">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-204">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-p119">Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un point de terminaison. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="717c5-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="717c5-p120">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="717c5-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-209"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-210">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-210">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-p121">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="717c5-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-214"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-215">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-215">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-216">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="717c5-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="717c5-217">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="717c5-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-218"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-219">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-219">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-p123">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="717c5-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717c5-222"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-223">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-223">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-p124">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="717c5-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717c5-226"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="717c5-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="717c5-227">Non</span><span class="sxs-lookup"><span data-stu-id="717c5-227">No</span></span></p></td>
<td><p><span data-ttu-id="717c5-p125">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="717c5-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

