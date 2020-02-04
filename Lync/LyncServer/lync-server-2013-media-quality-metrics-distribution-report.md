---
title: 'Rapport de distribution de métriques de qualité multimédia Lync Server 2013 :'
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
ms.openlocfilehash: 085525063d13c60dc1702ebf169fed92707675e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="2ae2b-102">Rapport de distribution des métriques de qualité multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae2b-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae2b-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2ae2b-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2ae2b-p101">Le rapport de distribution des mesures de qualité des médias vous permet de consulter un graphique qui affiche les valeurs de distribution pour une mesure de la qualité de l’expérience, comme la gigue ou la perte de paquets. Par exemple, supposons que vos utilisateurs passent un total de 10 appels téléphoniques. Ces 10 appels présentent les délais d’aller-retour suivants :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ae2b-106">Numéro de l’appel</span><span class="sxs-lookup"><span data-stu-id="2ae2b-106">Call Number</span></span></th>
<th><span data-ttu-id="2ae2b-107">Durée d’aller-retour (millisecondes)</span><span class="sxs-lookup"><span data-stu-id="2ae2b-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-108">1</span><span class="sxs-lookup"><span data-stu-id="2ae2b-108">1</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-109">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-110">deuxième</span><span class="sxs-lookup"><span data-stu-id="2ae2b-110">2</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-111">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-112">3</span><span class="sxs-lookup"><span data-stu-id="2ae2b-112">3</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-113">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-114">4</span><span class="sxs-lookup"><span data-stu-id="2ae2b-114">4</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-115">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-116">5</span><span class="sxs-lookup"><span data-stu-id="2ae2b-116">5</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-117">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-118">6</span><span class="sxs-lookup"><span data-stu-id="2ae2b-118">6</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-119">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-120">7</span><span class="sxs-lookup"><span data-stu-id="2ae2b-120">7</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-121">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-122">version8</span><span class="sxs-lookup"><span data-stu-id="2ae2b-122">8</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-123">4550</span><span class="sxs-lookup"><span data-stu-id="2ae2b-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-124">09</span><span class="sxs-lookup"><span data-stu-id="2ae2b-124">9</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-125">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-126">0,10</span><span class="sxs-lookup"><span data-stu-id="2ae2b-126">10</span></span></p></td>
<td><p><span data-ttu-id="2ae2b-127">50</span><span class="sxs-lookup"><span data-stu-id="2ae2b-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ae2b-128">La moyenne de ces temps d’aller-retour est de 500 millisecondes (5000 divisée par 10).</span><span class="sxs-lookup"><span data-stu-id="2ae2b-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="2ae2b-129">500 millisecondes est une durée de roundtrip très importante ; par conséquent, il est possible que vous rencontriez un problème sérieux avec la congestion du réseau.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="2ae2b-130">(Les temps de roundtrip longs sont généralement le résultat de réseaux surchargés.)</span><span class="sxs-lookup"><span data-stu-id="2ae2b-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="2ae2b-131">Pour le moment, le nombre de fois que 90% de vos appels avait des temps d’aller-retour exceptionnels. il vous suffit d’un appel incorrect qui a faussé les résultats globaux.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="2ae2b-132">Si vous observez uniquement la durée de l’aller-retour moyenne, vous risquez de sauter une erreur de conclusion.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="2ae2b-p104">Le rapport de distribution des mesures de qualité des médias vous permet de ne pas tirer de conclusions hâtives et erronées : il vous présente une répartition graphique d’une mesure précise (comme le délai d’aller-retour). Ces graphiques permettent de clarifier la situation, à savoir que vous avez passé neuf appels de très bonne qualité et un de mauvaise qualité. Vous souhaitez peut-être examiner plus en détail cet appel-ci. Cependant, le fait que 9 appels sur 10 étaient de bonne qualité semble indiquer qu’il n’existe aucune raison d’apporter des modifications radicales à votre réseau, au moins pas pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="2ae2b-136">Filtres</span><span class="sxs-lookup"><span data-stu-id="2ae2b-136">Filters</span></span>

<span data-ttu-id="2ae2b-p105">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="2ae2b-139">Filtres du rapport de distribution des mesures de qualité des médias</span><span class="sxs-lookup"><span data-stu-id="2ae2b-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ae2b-140">Nom</span><span class="sxs-lookup"><span data-stu-id="2ae2b-140">Name</span></span></th>
<th><span data-ttu-id="2ae2b-141">Description</span><span class="sxs-lookup"><span data-stu-id="2ae2b-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-142"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-p106">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2ae2b-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2ae2b-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ae2b-p107">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ae2b-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ae2b-148">7/7/2012</span></span></p>
<p><span data-ttu-id="2ae2b-149">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ae2b-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ae2b-150">7/3/2012</span></span></p>
<p><span data-ttu-id="2ae2b-151">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-152"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-p108">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2ae2b-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2ae2b-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ae2b-p109">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ae2b-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ae2b-158">7/7/2012</span></span></p>
<p><span data-ttu-id="2ae2b-159">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ae2b-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ae2b-160">7/3/2012</span></span></p>
<p><span data-ttu-id="2ae2b-161">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-162"><strong>Minimum sur l’axe x</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-163">Plus petite valeur à afficher sur l’axe X du graphique.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-164"><strong>Maximum sur l’axe x</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-165">Plus grande valeur à afficher sur l’axe X du graphique.</span><span class="sxs-lookup"><span data-stu-id="2ae2b-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-166"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-p110">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ae2b-169">[Tous]</span><span class="sxs-lookup"><span data-stu-id="2ae2b-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="2ae2b-170">Interne</span><span class="sxs-lookup"><span data-stu-id="2ae2b-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="2ae2b-171">Externe</span><span class="sxs-lookup"><span data-stu-id="2ae2b-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae2b-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-p111">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ae2b-175">[Tous]</span><span class="sxs-lookup"><span data-stu-id="2ae2b-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="2ae2b-176">VPN</span><span class="sxs-lookup"><span data-stu-id="2ae2b-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="2ae2b-177">Non-VPN</span><span class="sxs-lookup"><span data-stu-id="2ae2b-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae2b-178"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="2ae2b-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ae2b-p112">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ae2b-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ae2b-181">[Tous]</span><span class="sxs-lookup"><span data-stu-id="2ae2b-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="2ae2b-182">Câblé</span><span class="sxs-lookup"><span data-stu-id="2ae2b-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="2ae2b-183">Sans fil</span><span class="sxs-lookup"><span data-stu-id="2ae2b-183">Wireless</span></span></p></li>
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

