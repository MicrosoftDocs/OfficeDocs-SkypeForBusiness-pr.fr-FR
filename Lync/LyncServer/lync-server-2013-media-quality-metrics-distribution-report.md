---
title: 'Lync Server 2013 : rapport de distribution des mesures de qualité des médias'
description: 'Lync Server 2013 : rapport de distribution des mesures de qualité des médias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548150"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="1cf14-103">Le rapport de distribution des mesures de qualité des médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cf14-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cf14-104">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="1cf14-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="1cf14-105">Le rapport de distribution des mesures de qualité des médias vous permet d’afficher un graphique qui indique les valeurs de distribution pour une mesure de qualité de l’expérience, comme la gigue ou la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="1cf14-105">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="1cf14-106">Par exemple, supposons que vos utilisateurs effectuent un total de 10 appels téléphoniques ; ces 10 appels indiquent les temps d’aller-retour suivants :</span><span class="sxs-lookup"><span data-stu-id="1cf14-106">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1cf14-107">Numéro d’appel</span><span class="sxs-lookup"><span data-stu-id="1cf14-107">Call Number</span></span></th>
<th><span data-ttu-id="1cf14-108">Temps aller-retour (millisecondes)</span><span class="sxs-lookup"><span data-stu-id="1cf14-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-109">0,1</span><span class="sxs-lookup"><span data-stu-id="1cf14-109">1</span></span></p></td>
<td><p><span data-ttu-id="1cf14-110">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-111">n°2</span><span class="sxs-lookup"><span data-stu-id="1cf14-111">2</span></span></p></td>
<td><p><span data-ttu-id="1cf14-112">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-113">3</span><span class="sxs-lookup"><span data-stu-id="1cf14-113">3</span></span></p></td>
<td><p><span data-ttu-id="1cf14-114">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-115">4 </span><span class="sxs-lookup"><span data-stu-id="1cf14-115">4</span></span></p></td>
<td><p><span data-ttu-id="1cf14-116">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-117">5 </span><span class="sxs-lookup"><span data-stu-id="1cf14-117">5</span></span></p></td>
<td><p><span data-ttu-id="1cf14-118">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-119">6 </span><span class="sxs-lookup"><span data-stu-id="1cf14-119">6</span></span></p></td>
<td><p><span data-ttu-id="1cf14-120">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-121">7 </span><span class="sxs-lookup"><span data-stu-id="1cf14-121">7</span></span></p></td>
<td><p><span data-ttu-id="1cf14-122">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-123">8 </span><span class="sxs-lookup"><span data-stu-id="1cf14-123">8</span></span></p></td>
<td><p><span data-ttu-id="1cf14-124">4550</span><span class="sxs-lookup"><span data-stu-id="1cf14-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-125">9 </span><span class="sxs-lookup"><span data-stu-id="1cf14-125">9</span></span></p></td>
<td><p><span data-ttu-id="1cf14-126">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-127">10 </span><span class="sxs-lookup"><span data-stu-id="1cf14-127">10</span></span></p></td>
<td><p><span data-ttu-id="1cf14-128">50</span><span class="sxs-lookup"><span data-stu-id="1cf14-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1cf14-129">La moyenne de ces temps d’aller-retour est de 500 millisecondes (5000 divisée par 10).</span><span class="sxs-lookup"><span data-stu-id="1cf14-129">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="1cf14-130">500 millisecondes est un temps d’aller-retour extrêmement important ; par conséquent, vous pourriez penser que vous rencontrez un problème sérieux en matière de congestion du réseau.</span><span class="sxs-lookup"><span data-stu-id="1cf14-130">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="1cf14-131">(Les temps d’aller-retour longs sont généralement le résultat des réseaux surchargés.)</span><span class="sxs-lookup"><span data-stu-id="1cf14-131">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="1cf14-132">En réalité, bien évidemment, 90% de vos appels ont des temps d’aller-retour excellents ; Il y avait simplement un appel incorrect qui a faussé les résultats globaux.</span><span class="sxs-lookup"><span data-stu-id="1cf14-132">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="1cf14-133">Si vous examinez uniquement le temps d’aller-retour moyen, vous pouvez passer à une mauvaise conclusion.</span><span class="sxs-lookup"><span data-stu-id="1cf14-133">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="1cf14-134">Le rapport de distribution des mesures de qualité des médias vous permet d’éviter de sauter des conclusions erronées en affichant une distribution graphique d’une mesure spécifiée (par exemple, la durée des boucles).</span><span class="sxs-lookup"><span data-stu-id="1cf14-134">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="1cf14-135">Ces graphiques permettent de clarifier le fait que vous avez neuf appels très bons et un très mauvais appel.</span><span class="sxs-lookup"><span data-stu-id="1cf14-135">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="1cf14-136">De la même façon, vous souhaiterez peut-être continuer à étudier cet appel ; Toutefois, le fait que 9 des 10 appels ont été très intéressants indique qu’il n’y a aucune raison de modifier radicalement votre réseau, au moins dans le temps.</span><span class="sxs-lookup"><span data-stu-id="1cf14-136">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="1cf14-137">Filtres</span><span class="sxs-lookup"><span data-stu-id="1cf14-137">Filters</span></span>

<span data-ttu-id="1cf14-138">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="1cf14-138">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1cf14-139">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="1cf14-139">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="1cf14-140">Filtres du rapport de distribution des mesures de qualité des médias</span><span class="sxs-lookup"><span data-stu-id="1cf14-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1cf14-141">Nom</span><span class="sxs-lookup"><span data-stu-id="1cf14-141">Name</span></span></th>
<th><span data-ttu-id="1cf14-142">Description</span><span class="sxs-lookup"><span data-stu-id="1cf14-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1cf14-146">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1cf14-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1cf14-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1cf14-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1cf14-149">7/7/2012</span></span></p>
<p><span data-ttu-id="1cf14-150">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1cf14-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1cf14-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1cf14-151">7/3/2012</span></span></p>
<p><span data-ttu-id="1cf14-152">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1cf14-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1cf14-156">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1cf14-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1cf14-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1cf14-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1cf14-159">7/7/2012</span></span></p>
<p><span data-ttu-id="1cf14-160">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1cf14-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1cf14-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1cf14-161">7/3/2012</span></span></p>
<p><span data-ttu-id="1cf14-162">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1cf14-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-163"><strong>Minimum sur l’axe x</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-164">Plus petite valeur à afficher sur l’axe X du graphique.</span><span class="sxs-lookup"><span data-stu-id="1cf14-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-165"><strong>Maximum sur l’axe x</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-166">Valeur la plus élevée à afficher sur l’axe X du graphique.</span><span class="sxs-lookup"><span data-stu-id="1cf14-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-167"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-p110">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1cf14-170">Tous les</span><span class="sxs-lookup"><span data-stu-id="1cf14-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="1cf14-171">Interne</span><span class="sxs-lookup"><span data-stu-id="1cf14-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="1cf14-172">Externe</span><span class="sxs-lookup"><span data-stu-id="1cf14-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cf14-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-p111">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1cf14-176">Tous les</span><span class="sxs-lookup"><span data-stu-id="1cf14-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="1cf14-177">VPN</span><span class="sxs-lookup"><span data-stu-id="1cf14-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="1cf14-178">Non VPN</span><span class="sxs-lookup"><span data-stu-id="1cf14-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cf14-179"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="1cf14-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="1cf14-p112">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1cf14-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1cf14-182">Tous les</span><span class="sxs-lookup"><span data-stu-id="1cf14-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="1cf14-183">Circuit</span><span class="sxs-lookup"><span data-stu-id="1cf14-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="1cf14-184">Fil</span><span class="sxs-lookup"><span data-stu-id="1cf14-184">Wireless</span></span></p></li>
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

