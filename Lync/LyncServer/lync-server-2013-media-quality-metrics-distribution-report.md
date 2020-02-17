---
title: 'Lync Server 2013 : rapport de distribution des mesures de qualité des médias'
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
ms.openlocfilehash: 38adc41aaffcccbb27d4c9105f0fecabcae3c21c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="8847e-102">Le rapport de distribution des mesures de qualité des médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8847e-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8847e-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="8847e-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="8847e-104">Le rapport de distribution des mesures de qualité des médias vous permet d’afficher un graphique qui indique les valeurs de distribution pour une mesure de qualité de l’expérience, comme la gigue ou la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="8847e-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="8847e-105">Par exemple, supposons que vos utilisateurs effectuent un total de 10 appels téléphoniques ; ces 10 appels indiquent les temps d’aller-retour suivants :</span><span class="sxs-lookup"><span data-stu-id="8847e-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8847e-106">Numéro d’appel</span><span class="sxs-lookup"><span data-stu-id="8847e-106">Call Number</span></span></th>
<th><span data-ttu-id="8847e-107">Temps aller-retour (millisecondes)</span><span class="sxs-lookup"><span data-stu-id="8847e-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8847e-108">0,1</span><span class="sxs-lookup"><span data-stu-id="8847e-108">1</span></span></p></td>
<td><p><span data-ttu-id="8847e-109">50</span><span class="sxs-lookup"><span data-stu-id="8847e-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-110">n°2</span><span class="sxs-lookup"><span data-stu-id="8847e-110">2</span></span></p></td>
<td><p><span data-ttu-id="8847e-111">50</span><span class="sxs-lookup"><span data-stu-id="8847e-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-112">3</span><span class="sxs-lookup"><span data-stu-id="8847e-112">3</span></span></p></td>
<td><p><span data-ttu-id="8847e-113">50</span><span class="sxs-lookup"><span data-stu-id="8847e-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-114">4 </span><span class="sxs-lookup"><span data-stu-id="8847e-114">4</span></span></p></td>
<td><p><span data-ttu-id="8847e-115">50</span><span class="sxs-lookup"><span data-stu-id="8847e-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-116">5 </span><span class="sxs-lookup"><span data-stu-id="8847e-116">5</span></span></p></td>
<td><p><span data-ttu-id="8847e-117">50</span><span class="sxs-lookup"><span data-stu-id="8847e-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-118">6 </span><span class="sxs-lookup"><span data-stu-id="8847e-118">6</span></span></p></td>
<td><p><span data-ttu-id="8847e-119">50</span><span class="sxs-lookup"><span data-stu-id="8847e-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-120">7 </span><span class="sxs-lookup"><span data-stu-id="8847e-120">7</span></span></p></td>
<td><p><span data-ttu-id="8847e-121">50</span><span class="sxs-lookup"><span data-stu-id="8847e-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-122">8 </span><span class="sxs-lookup"><span data-stu-id="8847e-122">8</span></span></p></td>
<td><p><span data-ttu-id="8847e-123">4550</span><span class="sxs-lookup"><span data-stu-id="8847e-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-124">9 </span><span class="sxs-lookup"><span data-stu-id="8847e-124">9</span></span></p></td>
<td><p><span data-ttu-id="8847e-125">50</span><span class="sxs-lookup"><span data-stu-id="8847e-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-126">10 </span><span class="sxs-lookup"><span data-stu-id="8847e-126">10</span></span></p></td>
<td><p><span data-ttu-id="8847e-127">50</span><span class="sxs-lookup"><span data-stu-id="8847e-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8847e-128">La moyenne de ces temps d’aller-retour est de 500 millisecondes (5000 divisée par 10).</span><span class="sxs-lookup"><span data-stu-id="8847e-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="8847e-129">500 millisecondes est un temps d’aller-retour extrêmement important ; par conséquent, vous pourriez penser que vous rencontrez un problème sérieux en matière de congestion du réseau.</span><span class="sxs-lookup"><span data-stu-id="8847e-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="8847e-130">(Les temps d’aller-retour longs sont généralement le résultat des réseaux surchargés.)</span><span class="sxs-lookup"><span data-stu-id="8847e-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="8847e-131">En réalité, bien évidemment, 90% de vos appels ont des temps d’aller-retour excellents ; Il y avait simplement un appel incorrect qui a faussé les résultats globaux.</span><span class="sxs-lookup"><span data-stu-id="8847e-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="8847e-132">Si vous examinez uniquement le temps d’aller-retour moyen, vous pouvez passer à une mauvaise conclusion.</span><span class="sxs-lookup"><span data-stu-id="8847e-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="8847e-133">Le rapport de distribution des mesures de qualité des médias vous permet d’éviter de sauter des conclusions erronées en affichant une distribution graphique d’une mesure spécifiée (par exemple, la durée des boucles).</span><span class="sxs-lookup"><span data-stu-id="8847e-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="8847e-134">Ces graphiques permettent de clarifier le fait que vous avez neuf appels très bons et un très mauvais appel.</span><span class="sxs-lookup"><span data-stu-id="8847e-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="8847e-135">De la même façon, vous souhaiterez peut-être continuer à étudier cet appel ; Toutefois, le fait que 9 des 10 appels ont été très intéressants indique qu’il n’y a aucune raison de modifier radicalement votre réseau, au moins dans le temps.</span><span class="sxs-lookup"><span data-stu-id="8847e-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="8847e-136">Filtres</span><span class="sxs-lookup"><span data-stu-id="8847e-136">Filters</span></span>

<span data-ttu-id="8847e-137">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="8847e-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8847e-138">Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="8847e-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="8847e-139">Filtres du rapport de distribution des mesures de qualité des médias</span><span class="sxs-lookup"><span data-stu-id="8847e-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8847e-140">Nom</span><span class="sxs-lookup"><span data-stu-id="8847e-140">Name</span></span></th>
<th><span data-ttu-id="8847e-141">Description</span><span class="sxs-lookup"><span data-stu-id="8847e-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8847e-142"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="8847e-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8847e-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8847e-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8847e-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="8847e-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8847e-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8847e-148">7/7/2012</span></span></p>
<p><span data-ttu-id="8847e-149">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="8847e-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8847e-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8847e-150">7/3/2012</span></span></p>
<p><span data-ttu-id="8847e-151">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="8847e-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-152"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="8847e-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8847e-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8847e-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8847e-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="8847e-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8847e-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8847e-158">7/7/2012</span></span></p>
<p><span data-ttu-id="8847e-159">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="8847e-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8847e-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8847e-160">7/3/2012</span></span></p>
<p><span data-ttu-id="8847e-161">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="8847e-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-162"><strong>Minimum sur l’axe x</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-163">Plus petite valeur à afficher sur l’axe X du graphique.</span><span class="sxs-lookup"><span data-stu-id="8847e-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-164"><strong>Maximum sur l’axe x</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-165">Valeur la plus élevée à afficher sur l’axe X du graphique.</span><span class="sxs-lookup"><span data-stu-id="8847e-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-166"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-p110">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8847e-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8847e-169">Tous les</span><span class="sxs-lookup"><span data-stu-id="8847e-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="8847e-170">Interne</span><span class="sxs-lookup"><span data-stu-id="8847e-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="8847e-171">Externe</span><span class="sxs-lookup"><span data-stu-id="8847e-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8847e-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-p111">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8847e-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8847e-175">Tous les</span><span class="sxs-lookup"><span data-stu-id="8847e-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="8847e-176">VPN</span><span class="sxs-lookup"><span data-stu-id="8847e-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="8847e-177">Non VPN</span><span class="sxs-lookup"><span data-stu-id="8847e-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8847e-178"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="8847e-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="8847e-p112">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8847e-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8847e-181">Tous les</span><span class="sxs-lookup"><span data-stu-id="8847e-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="8847e-182">Circuit</span><span class="sxs-lookup"><span data-stu-id="8847e-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="8847e-183">Fil</span><span class="sxs-lookup"><span data-stu-id="8847e-183">Wireless</span></span></p></li>
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

