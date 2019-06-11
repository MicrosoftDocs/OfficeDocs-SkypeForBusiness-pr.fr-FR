---
title: 'Lync Server 2013: rapport de comparaison de la qualité multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="f8e04-102">Rapport de comparaison de qualité multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8e04-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e04-103">_**Dernière modification de la rubrique:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="f8e04-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="f8e04-104">Le rapport comparatif de la qualité des médias vous permet de comparer les valeurs de qualité des appels pour différents types d’appels audio (par exemple, des appels passés sur un réseau sans fil par rapport à ceux effectués via une connexion câblée).</span><span class="sxs-lookup"><span data-stu-id="f8e04-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="f8e04-105">Accès au rapport comparatif de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="f8e04-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="f8e04-106">Le rapport comparatif de la qualité des médias est accessible à partir de la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="f8e04-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f8e04-107">Filtres</span><span class="sxs-lookup"><span data-stu-id="f8e04-107">Filters</span></span>

<span data-ttu-id="f8e04-p101">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport comparatif de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="f8e04-110">Filtres du rapport comparatif de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="f8e04-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8e04-111">Nom</span><span class="sxs-lookup"><span data-stu-id="f8e04-111">Name</span></span></th>
<th><span data-ttu-id="f8e04-112">Description</span><span class="sxs-lookup"><span data-stu-id="f8e04-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-113"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-p102">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f8e04-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f8e04-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f8e04-p103">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f8e04-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f8e04-119">7/7/2012</span></span></p>
<p><span data-ttu-id="f8e04-120">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="f8e04-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f8e04-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f8e04-121">7/3/2012</span></span></p>
<p><span data-ttu-id="f8e04-122">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="f8e04-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e04-123"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-p104">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f8e04-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f8e04-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f8e04-p105">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f8e04-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f8e04-129">7/7/2012</span></span></p>
<p><span data-ttu-id="f8e04-130">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="f8e04-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f8e04-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f8e04-131">7/3/2012</span></span></p>
<p><span data-ttu-id="f8e04-132">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="f8e04-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-133"><strong>Appels</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-p106">Type d’appel à utiliser en tant que principal élément de comparaison. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8e04-136">[Tous]</span><span class="sxs-lookup"><span data-stu-id="f8e04-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="f8e04-137">Externe</span><span class="sxs-lookup"><span data-stu-id="f8e04-137">External</span></span></p></li>
<li><p><span data-ttu-id="f8e04-138">Interne</span><span class="sxs-lookup"><span data-stu-id="f8e04-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="f8e04-139">VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-140">Non-VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-141">Câblé</span><span class="sxs-lookup"><span data-stu-id="f8e04-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="f8e04-142">Sans fil</span><span class="sxs-lookup"><span data-stu-id="f8e04-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="f8e04-143">Externe et câblé</span><span class="sxs-lookup"><span data-stu-id="f8e04-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="f8e04-144">Externe et sans fil</span><span class="sxs-lookup"><span data-stu-id="f8e04-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="f8e04-145">Externe et VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-146">Externe et non VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-147">Interne et câblé</span><span class="sxs-lookup"><span data-stu-id="f8e04-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="f8e04-148">Interne et sans fil</span><span class="sxs-lookup"><span data-stu-id="f8e04-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e04-149"><strong>Comparer avec les appels</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-p107">Type d’appel à utiliser en tant qu’élément de comparaison secondaire. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8e04-152">[Tous]</span><span class="sxs-lookup"><span data-stu-id="f8e04-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="f8e04-153">Externe</span><span class="sxs-lookup"><span data-stu-id="f8e04-153">External</span></span></p></li>
<li><p><span data-ttu-id="f8e04-154">Interne</span><span class="sxs-lookup"><span data-stu-id="f8e04-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="f8e04-155">VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-156">Non-VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-157">Câblé</span><span class="sxs-lookup"><span data-stu-id="f8e04-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="f8e04-158">Sans fil</span><span class="sxs-lookup"><span data-stu-id="f8e04-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="f8e04-159">Externe et câblé</span><span class="sxs-lookup"><span data-stu-id="f8e04-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="f8e04-160">Externe et sans fil</span><span class="sxs-lookup"><span data-stu-id="f8e04-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="f8e04-161">Externe et VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-162">Externe et non VPN</span><span class="sxs-lookup"><span data-stu-id="f8e04-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="f8e04-163">Interne et câblé</span><span class="sxs-lookup"><span data-stu-id="f8e04-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="f8e04-164">Interne et sans fil</span><span class="sxs-lookup"><span data-stu-id="f8e04-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-165"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-p108">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8e04-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8e04-168">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="f8e04-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f8e04-169">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="f8e04-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f8e04-170">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="f8e04-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f8e04-171">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f8e04-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="f8e04-172">Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="f8e04-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f8e04-173">Mesures</span><span class="sxs-lookup"><span data-stu-id="f8e04-173">Metrics</span></span>

<span data-ttu-id="f8e04-174">Le tableau qui suit répertorie les informations fournies dans le rapport comparatif de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="f8e04-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="f8e04-175">Mesures du rapport comparatif de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="f8e04-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8e04-176">Nom</span><span class="sxs-lookup"><span data-stu-id="f8e04-176">Name</span></span></th>
<th><span data-ttu-id="f8e04-177">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="f8e04-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f8e04-178">Description</span><span class="sxs-lookup"><span data-stu-id="f8e04-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-179"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-180">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-180">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-181">Nombre total d’appels.</span><span class="sxs-lookup"><span data-stu-id="f8e04-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e04-182"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-183">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-183">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-184">Taux moyen de dégradation de la note MOS (note moyenne d’opinion) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="f8e04-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="f8e04-185">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée) ; une valeur inférieure ou égale à 0,5 indique une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="f8e04-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="f8e04-186">Traditionnellement, les notes moyennes d’opinion étaient calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="f8e04-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="f8e04-187">Lync Server utilise un ensemble d’algorithmes pour prévoir la façon dont les utilisateurs auraient noté un appel.</span><span class="sxs-lookup"><span data-stu-id="f8e04-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="f8e04-p111">Les valeurs de dégradation élevées peuvent avoir plusieurs causes : une congestion, un dépassement de la bande passante disponible, une congestion/interférence dans la liaison sans fil ou bien la surcharge d’un serveur multimédia ou d’un système d’extrémité. Ces valeurs se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-190"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-191">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-191">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-p112">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="f8e04-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e04-194"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-195">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-195">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-p113">Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f8e04-p114">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-200"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-201">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-201">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-p115">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e04-205"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-206">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-206">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-207">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="f8e04-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f8e04-208">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="f8e04-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-209"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-210">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-210">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-p117">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e04-213"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-214">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-214">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-p118">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e04-217"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="f8e04-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8e04-218">Non</span><span class="sxs-lookup"><span data-stu-id="f8e04-218">No</span></span></p></td>
<td><p><span data-ttu-id="f8e04-p119">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="f8e04-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

