---
title: 'Lync Server 2013 : rapport d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f7db796a4edab00918b0353e9b635f4615ba9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="86135-102">Rapport d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86135-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86135-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="86135-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="86135-p101">Le rapport d’emplacement fournit des informations sur les mesures de la qualité des appels regroupées par emplacement réseau (c’est-à-dire, par sous-réseau). Si vos utilisateurs rencontrent des problèmes avec leurs appels, ce rapport peut vous aider à déterminer si ces problèmes sont étendus ou s’ils sont largement réduits à un segment de réseau donné.</span><span class="sxs-lookup"><span data-stu-id="86135-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="86135-106">Accès au rapport d’emplacement</span><span class="sxs-lookup"><span data-stu-id="86135-106">Accessing the Location Report</span></span>

<span data-ttu-id="86135-p102">Le rapport d’emplacement est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au rapport des listes d’appels en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="86135-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="86135-109">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="86135-109">Call volume</span></span>

  - <span data-ttu-id="86135-110">Pourcentage d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="86135-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="86135-111">Filtres</span><span class="sxs-lookup"><span data-stu-id="86135-111">Filters</span></span>

<span data-ttu-id="86135-p103">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’emplacement vous permet de filtrer des éléments comme l’emplacement duquel un appel provient ou s’il s’est produit sur une connexion  réseau câblée ou sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="86135-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="86135-116">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="86135-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="86135-117">Filtres du rapport d’emplacement</span><span class="sxs-lookup"><span data-stu-id="86135-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86135-118">Nom</span><span class="sxs-lookup"><span data-stu-id="86135-118">Name</span></span></th>
<th><span data-ttu-id="86135-119">Description</span><span class="sxs-lookup"><span data-stu-id="86135-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86135-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="86135-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-p104">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="86135-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="86135-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86135-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86135-p105">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="86135-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86135-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86135-126">7/7/2012</span></span></p>
<p><span data-ttu-id="86135-127">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="86135-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86135-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86135-128">7/3/2012</span></span></p>
<p><span data-ttu-id="86135-129">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="86135-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="86135-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-p106">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="86135-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="86135-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86135-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86135-p107">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="86135-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86135-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86135-136">7/7/2012</span></span></p>
<p><span data-ttu-id="86135-137">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="86135-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86135-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86135-138">7/3/2012</span></span></p>
<p><span data-ttu-id="86135-139">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="86135-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-140"><strong>Emplacement de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="86135-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-p108">Sous-réseau IP de l’utilisateur qui a émis l’appel. Vous pouvez uniquement sélectionner <strong>[Tous]</strong> pour indiquer tous les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="86135-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-143"><strong>Emplacement de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="86135-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-p109">Sous-réseau IP de l’utilisateur qui a reçu l’appel. Vous pouvez uniquement sélectionner <strong>[Tous]</strong> pour indiquer tous les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="86135-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-146"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="86135-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-p110">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="86135-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="86135-149">Tous les</span><span class="sxs-lookup"><span data-stu-id="86135-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="86135-150">Circuit</span><span class="sxs-lookup"><span data-stu-id="86135-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="86135-151">Fil</span><span class="sxs-lookup"><span data-stu-id="86135-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="86135-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-p111">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="86135-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="86135-155">Tous les</span><span class="sxs-lookup"><span data-stu-id="86135-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="86135-156">VPN</span><span class="sxs-lookup"><span data-stu-id="86135-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="86135-157">Non VPN</span><span class="sxs-lookup"><span data-stu-id="86135-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="86135-158">Mesures</span><span class="sxs-lookup"><span data-stu-id="86135-158">Metrics</span></span>

<span data-ttu-id="86135-159">Le tableau qui suit répertorie les informations fournies dans le rapport d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="86135-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="86135-160">Mesures du rapport d’emplacement</span><span class="sxs-lookup"><span data-stu-id="86135-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86135-161">Nom</span><span class="sxs-lookup"><span data-stu-id="86135-161">Name</span></span></th>
<th><span data-ttu-id="86135-162">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="86135-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="86135-163">Description</span><span class="sxs-lookup"><span data-stu-id="86135-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86135-164"><strong>Sous-réseau de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="86135-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-165">Non</span><span class="sxs-lookup"><span data-stu-id="86135-165">No</span></span></p></td>
<td><p><span data-ttu-id="86135-166">Sous-réseau IP de l’utilisateur qui a émis l’appel.</span><span class="sxs-lookup"><span data-stu-id="86135-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-167"><strong>Sous-réseau de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="86135-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-168">Non</span><span class="sxs-lookup"><span data-stu-id="86135-168">No</span></span></p></td>
<td><p><span data-ttu-id="86135-169">Sous-réseau IP de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="86135-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-170"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="86135-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-171">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-172">Nombre total d’appels émis.</span><span class="sxs-lookup"><span data-stu-id="86135-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-173"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="86135-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-174">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-p112">Pourcentage d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="86135-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-177"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="86135-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-178">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-p113">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="86135-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="86135-p114">Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="86135-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-183"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="86135-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-184">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-185">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="86135-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="86135-186">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="86135-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="86135-187">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="86135-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="86135-188">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="86135-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="86135-189">Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</span><span class="sxs-lookup"><span data-stu-id="86135-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="86135-p116">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="86135-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-192"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="86135-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-193">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-p117">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="86135-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-197"><strong>Scintill</strong></span><span class="sxs-lookup"><span data-stu-id="86135-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-198">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-199">Gigue moyenne du délai d’arrivée entre les paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="86135-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="86135-200">(L’instabilité est une mesure &quot;de&quot; la fluctuations d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="86135-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-201"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="86135-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-202">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-p119">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="86135-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86135-205"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="86135-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-206">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-p120">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="86135-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86135-209"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="86135-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="86135-210">Oui</span><span class="sxs-lookup"><span data-stu-id="86135-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="86135-p121">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="86135-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

