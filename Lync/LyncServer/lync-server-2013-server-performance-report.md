---
title: 'Rapport de performances du serveur Lync Server 2013 :'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb7e01086ac423380a913b75391ec3086ee3736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="e5292-102">Rapport sur les performances du serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5292-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5292-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e5292-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e5292-104">Le rapport sur les performances du serveur fournit une liste de serveurs Microsoft Lync Server 2013 ayant constaté le plus grand pourcentage d’appels médiocres.</span><span class="sxs-lookup"><span data-stu-id="e5292-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="e5292-105">Ce rapport est décomposé en fonction des types de serveur, et propose des statistiques distinctes pour les types suivants :</span><span class="sxs-lookup"><span data-stu-id="e5292-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="e5292-106">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="e5292-106">Mediation Server</span></span>

  - <span data-ttu-id="e5292-107">Serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="e5292-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="e5292-108">Serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="e5292-108">A/V Edge Server</span></span>

  - <span data-ttu-id="e5292-109">Passerelle (serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="e5292-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="e5292-110">Passerelle (contournement du serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="e5292-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="e5292-111">Vidéo (y compris les mesures vidéo pour les serveurs de conférence A/V et les serveurs Edge A/V)</span><span class="sxs-lookup"><span data-stu-id="e5292-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="e5292-112">Partage d’application (y compris les mesures de partage d’application pour les serveurs de conférence A/V et les serveurs Edge A/V)</span><span class="sxs-lookup"><span data-stu-id="e5292-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="e5292-p102">Il est important de noter que le classement indiqué dans le rapport est relatif. Par exemple, supposons que le serveur ayant les pires performances a reçu un appel médiocre sur les 1 000 passés. Ce pourcentage de 0,1 est plus qu’acceptable. Cependant, s’il s’agit du serveur ayant les pires performances (c’est-à-dire que les autres serveurs ont un pourcentage d’appels médiocres inférieur à 0,1 %), ce serveur s’affichera dans le rapport de performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="e5292-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="e5292-117">Accès au rapport de performances du serveur</span><span class="sxs-lookup"><span data-stu-id="e5292-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="e5292-118">Le rapport de performances du serveur est accessible à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="e5292-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e5292-119">Vous pouvez explorer le rapport de la [liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5292-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e5292-120">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="e5292-120">Call volume</span></span>

  - <span data-ttu-id="e5292-121">Pourcentage d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="e5292-121">Poor call percentage</span></span>

<span data-ttu-id="e5292-122">De plus, vous pouvez accéder au rapport de tendance de la qualité des médias serveur en cliquant sur la mesure suivante :</span><span class="sxs-lookup"><span data-stu-id="e5292-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="e5292-123">Tendance</span><span class="sxs-lookup"><span data-stu-id="e5292-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="e5292-124">Optimiser l’utilisation du rapport sur les performances du serveur</span><span class="sxs-lookup"><span data-stu-id="e5292-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="e5292-p104">Le rapport de performances du serveur fournit plusieurs moyens pour filtrer les données ; par exemple, vous pouvez filtrer sur un type de réseau (appels passés via une connexion câblée ou sans fil) et un type d’accès (appels passés à l’intérieur du pare-feu ou à l’extérieur). Il est conseillé d’utiliser ces filtres quand vous affichez le rapport de performances du serveur. Par exemple, vous avez un serveur de médiation avec un pourcentage d’appels médiocre de 3,24 %. Si vous considérez uniquement les appels sans fil, ce même serveur peut avoir un pourcentage d’appels médiocres de 20 %. Cela signifie que ce serveur ne gère pas bien les appels sans fil, mais ce problème peut être partiellement masqué par les appels câblés qui ne posent pas de problème.</span><span class="sxs-lookup"><span data-stu-id="e5292-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e5292-130">Filtres</span><span class="sxs-lookup"><span data-stu-id="e5292-130">Filters</span></span>

<span data-ttu-id="e5292-p105">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le rapport de performances du serveur vous permet par exemple, de filtrer les données renvoyées par type de serveur ou type de réseau (câblé ou sans fil). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les données sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="e5292-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e5292-135">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="e5292-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="e5292-136">Filtres de rapport de performances du serveur</span><span class="sxs-lookup"><span data-stu-id="e5292-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5292-137">Nom</span><span class="sxs-lookup"><span data-stu-id="e5292-137">Name</span></span></th>
<th><span data-ttu-id="e5292-138">Description</span><span class="sxs-lookup"><span data-stu-id="e5292-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5292-139"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="e5292-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e5292-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e5292-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5292-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="e5292-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5292-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5292-145">7/7/2012</span></span></p>
<p><span data-ttu-id="e5292-146">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="e5292-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5292-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5292-147">7/3/2012</span></span></p>
<p><span data-ttu-id="e5292-148">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="e5292-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-149"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="e5292-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e5292-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e5292-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5292-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="e5292-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5292-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5292-155">7/7/2012</span></span></p>
<p><span data-ttu-id="e5292-156">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="e5292-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5292-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5292-157">7/3/2012</span></span></p>
<p><span data-ttu-id="e5292-158">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="e5292-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-159"><strong>Type de serveur</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p110">Indique le type de serveur dont les performances doivent être rapportées. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5292-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e5292-162">[Tous]</span><span class="sxs-lookup"><span data-stu-id="e5292-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5292-163">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="e5292-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="e5292-164">Serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="e5292-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="e5292-165">Serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="e5292-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-166"><strong>N premiers</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p111">Indique le nombre de serveurs (sur la base du pourcentage d’appels médiocres) à afficher dans chaque catégorie. Par exemple, si vous sélectionnez <strong>5</strong>, les cinq serveurs ayant les performances les plus médiocres sont affichés. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5292-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e5292-170">[Tous]</span><span class="sxs-lookup"><span data-stu-id="e5292-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5292-171">5</span><span class="sxs-lookup"><span data-stu-id="e5292-171">5</span></span></p></li>
<li><p><span data-ttu-id="e5292-172">0,10</span><span class="sxs-lookup"><span data-stu-id="e5292-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-173"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p112">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5292-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e5292-176">[Tous]</span><span class="sxs-lookup"><span data-stu-id="e5292-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5292-177">Interne</span><span class="sxs-lookup"><span data-stu-id="e5292-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="e5292-178">Externe</span><span class="sxs-lookup"><span data-stu-id="e5292-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-179"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p113">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5292-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e5292-182">[Tous]</span><span class="sxs-lookup"><span data-stu-id="e5292-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5292-183">Câblé</span><span class="sxs-lookup"><span data-stu-id="e5292-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="e5292-184">Sans fil</span><span class="sxs-lookup"><span data-stu-id="e5292-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-p114">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5292-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e5292-188">[Tous]</span><span class="sxs-lookup"><span data-stu-id="e5292-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5292-189">VPN</span><span class="sxs-lookup"><span data-stu-id="e5292-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="e5292-190">Non-VPN</span><span class="sxs-lookup"><span data-stu-id="e5292-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e5292-191">Mesures</span><span class="sxs-lookup"><span data-stu-id="e5292-191">Metrics</span></span>

<span data-ttu-id="e5292-192">Le tableau qui suit répertorie les informations fournies dans le rapport de performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="e5292-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="e5292-193">Mesures du rapport de performances du serveur : synthèse des appels audio</span><span class="sxs-lookup"><span data-stu-id="e5292-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5292-194">Nom</span><span class="sxs-lookup"><span data-stu-id="e5292-194">Name</span></span></th>
<th><span data-ttu-id="e5292-195">Tri possible</span><span class="sxs-lookup"><span data-stu-id="e5292-195">Can Sort On</span></span></th>
<th><span data-ttu-id="e5292-196">Description</span><span class="sxs-lookup"><span data-stu-id="e5292-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5292-197"><strong>Serveur</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-198">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-198">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-199">Nom/adresse IP du serveur</span><span class="sxs-lookup"><span data-stu-id="e5292-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-200"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-201">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-201">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-202">Nombre total d’appels effectués.</span><span class="sxs-lookup"><span data-stu-id="e5292-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-203"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-204">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-204">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p115">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="e5292-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-207"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-208">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-p116">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="e5292-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e5292-p117">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="e5292-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-213"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-214">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-215">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="e5292-216">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="e5292-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="e5292-217">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="e5292-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="e5292-218">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="e5292-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="e5292-219">Dans Lync Server, le serveur de surveillance utilise un ensemble d’algorithmes pour prévoir la façon dont les utilisateurs auraient noté un appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="e5292-p119">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="e5292-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-222"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-223">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-p120">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="e5292-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-227"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-228">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-229">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="e5292-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e5292-230">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="e5292-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-231"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-232">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-p122">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="e5292-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-235"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-236">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-p123">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="e5292-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-239"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-240">Oui</span><span class="sxs-lookup"><span data-stu-id="e5292-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="e5292-p124">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="e5292-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="e5292-243">Mesures du rapport de performances du serveur : synthèse des appels vidéo</span><span class="sxs-lookup"><span data-stu-id="e5292-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5292-244">Nom</span><span class="sxs-lookup"><span data-stu-id="e5292-244">Name</span></span></th>
<th><span data-ttu-id="e5292-245">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="e5292-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5292-246">Description</span><span class="sxs-lookup"><span data-stu-id="e5292-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5292-247"><strong>Type d’appel/type de point de terminaison</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-248">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-248">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p125">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="e5292-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5292-251">Appels P2P UC</span><span class="sxs-lookup"><span data-stu-id="e5292-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="e5292-252">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="e5292-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="e5292-253">Sessions de conférence RTC</span><span class="sxs-lookup"><span data-stu-id="e5292-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="e5292-254">Appels RTC : contournement du média</span><span class="sxs-lookup"><span data-stu-id="e5292-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="e5292-255">Appels RTC (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="e5292-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="e5292-256">Appels RTC (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="e5292-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="e5292-257">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="e5292-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-258"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-259">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-259">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-260">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-261"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-262">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-262">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p126">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="e5292-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-265"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-266">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-266">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-267">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="e5292-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-268"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-269">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-269">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-270">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="e5292-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-271"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-272">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-272">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-273">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="e5292-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-274"><strong>Vitesse de transmission moyenne (Kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-275">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-275">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-276">Vitesse de transmission vidéo moyenne (en kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="e5292-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-277"><strong>Vitesse de transmission faible (%)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-278">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-278">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-279">Pourcentage de l’appel où la vitesse de transmission était faible.</span><span class="sxs-lookup"><span data-stu-id="e5292-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-280"><strong>Perte de paquets sortante</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-281">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-281">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p127">Perte de paquets RTP (Real-Time Transport Protocol) pour les paquets sortants. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="e5292-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-285"><strong>Image figée (%)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-286">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-286">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p128">Pourcentage d’images « figées ». Dans une image figée, la vidéo cesse d’avancer tandis que la partie audio de l’appel continue.</span><span class="sxs-lookup"><span data-stu-id="e5292-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-289"><strong>Fréquence d’images moyenne sortante</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-290">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-290">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-291">Fréquence d’images moyenne pour les transmissions sortantes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-292"><strong>Fréquence d’images moyenne entrante</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-293">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-293">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-294">Fréquence d’images moyenne pour les transmissions entrantes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-295"><strong>Fréquence d’images basse entrante (%)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-296">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-296">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-297">Pourcentage de l’appel où la vitesse de transmission pour la vidéo entrante était faible.</span><span class="sxs-lookup"><span data-stu-id="e5292-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-298"><strong>Intégrité des clients (%)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5292-299">Indique l’intégrité relative du périphérique client pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="e5292-300">Mesures du rapport de performances du serveur : synthèse des appels de partage d’application</span><span class="sxs-lookup"><span data-stu-id="e5292-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5292-301">Nom</span><span class="sxs-lookup"><span data-stu-id="e5292-301">Name</span></span></th>
<th><span data-ttu-id="e5292-302">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="e5292-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5292-303">Description</span><span class="sxs-lookup"><span data-stu-id="e5292-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5292-304"><strong>Type d’appel/type de point de terminaison</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-305">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-305">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p129">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="e5292-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5292-308">Appels P2P UC</span><span class="sxs-lookup"><span data-stu-id="e5292-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="e5292-309">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="e5292-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="e5292-310">Sessions de conférence RTC</span><span class="sxs-lookup"><span data-stu-id="e5292-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="e5292-311">Appels RTC : contournement du média</span><span class="sxs-lookup"><span data-stu-id="e5292-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="e5292-312">Appels RTC (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="e5292-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="e5292-313">Appels RTC (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="e5292-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="e5292-314">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="e5292-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-315"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-316">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-316">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-317">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="e5292-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-318"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-319">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-319">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p130">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="e5292-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-322"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-323">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-323">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-324">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="e5292-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-325"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-326">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-326">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-327">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="e5292-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-328"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-329">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-329">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-330">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="e5292-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-331"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-332">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-332">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-333">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="e5292-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e5292-334">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="e5292-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-335"><strong>Unilatéral relatif moyen</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-336">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-336">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p132">Retard unilatéral relatif moyen entre deux points de terminaison du média. Il s’agit d’une mesure de latence sur un seul tronçon.</span><span class="sxs-lookup"><span data-stu-id="e5292-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5292-339"><strong>Latence moyenne de traitement des mosaïques RDP</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-340">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-340">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-p133">Latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. Cette mesure ne couvre pas la latence du réseau. Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.</span><span class="sxs-lookup"><span data-stu-id="e5292-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5292-345"><strong>Nombre total de mosaïques altérées (%)</strong></span><span class="sxs-lookup"><span data-stu-id="e5292-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="e5292-346">Non</span><span class="sxs-lookup"><span data-stu-id="e5292-346">No</span></span></p></td>
<td><p><span data-ttu-id="e5292-347">Pourcentage total de mosaïques RDP altérées.</span><span class="sxs-lookup"><span data-stu-id="e5292-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

