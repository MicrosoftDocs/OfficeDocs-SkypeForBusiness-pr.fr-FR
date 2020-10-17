---
title: 'Lync Server 2013 : rapport de synthèse de la qualité des médias'
description: 'Lync Server 2013 : rapport de synthèse de la qualité des médias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2616b7e3cdea9df7b004745a5c407188870903c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558070"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="4681c-103">Rapport de synthèse de la qualité des médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4681c-103">Media Quality Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4681c-104">_**Dernière modification de la rubrique :** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="4681c-104">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="4681c-105">Le rapport de synthèse de la qualité des médias permet d’analyser la qualité des appels au sein de votre organisation : ce rapport fournit des mesures d’appel de qualité de l’expérience (QoE) détaillées décomposées selon les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="4681c-105">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="4681c-106">Appels d’égal à égal UC (tels qu’un appel Microsoft Lync 2013 vers Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="4681c-106">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="4681c-107">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="4681c-107">UC Conference Sessions</span></span>

  - <span data-ttu-id="4681c-108">Sessions de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="4681c-108">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="4681c-109">Appels PSTN : contournement du média</span><span class="sxs-lookup"><span data-stu-id="4681c-109">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="4681c-110">Appels PSTN (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="4681c-110">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="4681c-111">Appels PSTN (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="4681c-111">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="4681c-112">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="4681c-112">Other Call Types</span></span>

<span data-ttu-id="4681c-113">Quand vous ouvrez le rapport pour la première fois, une synthèse des informations pour chaque catégorie s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4681c-113">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="4681c-114">Sans quitter le rapport, vous pouvez développer chaque catégorie pour consulter des sous-catégories telles que les appels passés d’Office Communicator 2007 R2 à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4681c-114">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="4681c-115">Vous pouvez développer également ces sous-catégories pour afficher des détails sur chaque appel passé dans cette sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="4681c-115">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="4681c-116">Dans Microsoft Lync Server 2013, le rapport de synthèse de la qualité des médias divise les données en trois types d’appels : les appels audio, les appels vidéo et les appels de partage d’applications.</span><span class="sxs-lookup"><span data-stu-id="4681c-116">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="4681c-117">Chaque type d’appel correspond à une section du rapport, et dispose d’un ensemble personnalisé de mesures des appels.</span><span class="sxs-lookup"><span data-stu-id="4681c-117">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="4681c-118">Le rapport de synthèse de la qualité des médias vous permet d’appliquer des filtres pour comparer la qualité des appels entre les appels câblés et les appels sans fil, les appels internes et externes, les appels VPN et non VPN.</span><span class="sxs-lookup"><span data-stu-id="4681c-118">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="4681c-119">Accès au rapport de synthèse de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="4681c-119">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="4681c-120">Le rapport de synthèse de la qualité des médias est accessible à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="4681c-120">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4681c-121">Vous pouvez accéder au [rapport des listes d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="4681c-121">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4681c-122">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="4681c-122">Call volume</span></span>

  - <span data-ttu-id="4681c-123">Pourcentage d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="4681c-123">Poor call percentage</span></span>

<span data-ttu-id="4681c-124">De plus, vous pouvez accéder au Rapport de distribution des mesures de qualité des médias en cliquant sur l’une des mesures d’appel audio suivantes :</span><span class="sxs-lookup"><span data-stu-id="4681c-124">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="4681c-125">Boucle (ms)</span><span class="sxs-lookup"><span data-stu-id="4681c-125">Round trip (ms)</span></span>

  - <span data-ttu-id="4681c-126">Dégradation (MOS)</span><span class="sxs-lookup"><span data-stu-id="4681c-126">Degradation (MOS)</span></span>

  - <span data-ttu-id="4681c-127">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="4681c-127">Packet loss</span></span>

  - <span data-ttu-id="4681c-128">Gigue (ms)</span><span class="sxs-lookup"><span data-stu-id="4681c-128">Jitter (ms)</span></span>

  - <span data-ttu-id="4681c-129">Taux de masquage de la réparation</span><span class="sxs-lookup"><span data-stu-id="4681c-129">Healer concealed ratio</span></span>

  - <span data-ttu-id="4681c-130">Taux d’étirement de la réparation</span><span class="sxs-lookup"><span data-stu-id="4681c-130">Healer stretched ratio</span></span>

  - <span data-ttu-id="4681c-131">Taux de compression de la réparation</span><span class="sxs-lookup"><span data-stu-id="4681c-131">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4681c-132">Filtres</span><span class="sxs-lookup"><span data-stu-id="4681c-132">Filters</span></span>

<span data-ttu-id="4681c-p104">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, grâce au rapport de synthèse de la qualité des médias, vous pouvez filtrer les données retournées selon des éléments précis, tels que le type d’accès (à savoir « accès interne » par comparaison à « accès externe ») ou la connexion réseau câblée/sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="4681c-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4681c-137">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="4681c-137">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="4681c-138">Filtres du rapport de synthèse de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="4681c-138">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4681c-139">Nom</span><span class="sxs-lookup"><span data-stu-id="4681c-139">Name</span></span></th>
<th><span data-ttu-id="4681c-140">Description</span><span class="sxs-lookup"><span data-stu-id="4681c-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4681c-141"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-141"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="4681c-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4681c-144">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4681c-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4681c-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="4681c-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4681c-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4681c-147">7/7/2012</span></span></p>
<p><span data-ttu-id="4681c-148">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="4681c-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4681c-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4681c-149">7/3/2012</span></span></p>
<p><span data-ttu-id="4681c-150">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="4681c-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-151"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-151"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4681c-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4681c-154">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4681c-154">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4681c-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="4681c-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4681c-157">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4681c-157">7/7/2012</span></span></p>
<p><span data-ttu-id="4681c-158">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="4681c-158">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4681c-159">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4681c-159">7/3/2012</span></span></p>
<p><span data-ttu-id="4681c-160">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="4681c-160">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-161"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-161"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-p109">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4681c-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4681c-164">Tous les</span><span class="sxs-lookup"><span data-stu-id="4681c-164">[All]</span></span></p></li>
<li><p><span data-ttu-id="4681c-165">Interne</span><span class="sxs-lookup"><span data-stu-id="4681c-165">Internal</span></span></p></li>
<li><p><span data-ttu-id="4681c-166">Externe</span><span class="sxs-lookup"><span data-stu-id="4681c-166">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-167"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-167"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-p110">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4681c-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4681c-170">Tous les</span><span class="sxs-lookup"><span data-stu-id="4681c-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="4681c-171">Circuit</span><span class="sxs-lookup"><span data-stu-id="4681c-171">Wired</span></span></p></li>
<li><p><span data-ttu-id="4681c-172">Fil</span><span class="sxs-lookup"><span data-stu-id="4681c-172">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-p111">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4681c-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4681c-176">Tous les</span><span class="sxs-lookup"><span data-stu-id="4681c-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="4681c-177">VPN</span><span class="sxs-lookup"><span data-stu-id="4681c-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="4681c-178">Non VPN</span><span class="sxs-lookup"><span data-stu-id="4681c-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4681c-179">Mesures</span><span class="sxs-lookup"><span data-stu-id="4681c-179">Metrics</span></span>

<span data-ttu-id="4681c-180">Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="4681c-180">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="4681c-181">Mesures du rapport de synthèse de la qualité des médias : synthèse des appels audio</span><span class="sxs-lookup"><span data-stu-id="4681c-181">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4681c-182">Nom</span><span class="sxs-lookup"><span data-stu-id="4681c-182">Name</span></span></th>
<th><span data-ttu-id="4681c-183">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4681c-183">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4681c-184">Description</span><span class="sxs-lookup"><span data-stu-id="4681c-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4681c-185"><strong>Type d’appel/type de système d’extrémité</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-185"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-186">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-186">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p112">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4681c-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4681c-189">Appels d’égal à égal UC</span><span class="sxs-lookup"><span data-stu-id="4681c-189">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4681c-190">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="4681c-190">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4681c-191">Sessions de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="4681c-191">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4681c-192">Appels PSTN : contournement du média</span><span class="sxs-lookup"><span data-stu-id="4681c-192">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4681c-193">Appels PSTN (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="4681c-193">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4681c-194">Appels PSTN (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="4681c-194">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4681c-195">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="4681c-195">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-196"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-196"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-197">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-197">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-198">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-198">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-199"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-200">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-200">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p113">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="4681c-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-203"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-203"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-204">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-204">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-205">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="4681c-205">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-206"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-206"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-207">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-207">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-208">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="4681c-208">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-209"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-209"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-210">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-210">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-211">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="4681c-211">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-212"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-212"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-213">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-213">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p114">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="4681c-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="4681c-p115">Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="4681c-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-218"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-218"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-219">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-219">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-220">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-220">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="4681c-221">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="4681c-221">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="4681c-222">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="4681c-222">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="4681c-223">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="4681c-223">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="4681c-224">Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-224">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="4681c-p117">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-227"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-227"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-228">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-228">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p118">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-232"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-232"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-233">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-233">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-234">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="4681c-234">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4681c-235">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-235">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-236"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-236"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-237">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-237">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p120">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-240"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-240"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-241">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-241">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p121">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-244"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-244"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-245">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-245">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p122">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="4681c-248">Mesures du rapport de synthèse de la qualité des médias : synthèse des appels vidéo</span><span class="sxs-lookup"><span data-stu-id="4681c-248">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4681c-249">Nom</span><span class="sxs-lookup"><span data-stu-id="4681c-249">Name</span></span></th>
<th><span data-ttu-id="4681c-250">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4681c-250">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4681c-251">Description</span><span class="sxs-lookup"><span data-stu-id="4681c-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4681c-252"><strong>Type d’appel/type de système d’extrémité</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-252"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-253">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-253">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p123">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4681c-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4681c-256">Appels d’égal à égal UC</span><span class="sxs-lookup"><span data-stu-id="4681c-256">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4681c-257">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="4681c-257">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4681c-258">Sessions de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="4681c-258">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4681c-259">Appels PSTN : contournement du média</span><span class="sxs-lookup"><span data-stu-id="4681c-259">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4681c-260">Appels PSTN (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="4681c-260">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4681c-261">Appels PSTN (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="4681c-261">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4681c-262">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="4681c-262">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-263"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-263"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-264">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-264">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-265">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-265">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-266"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-266"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-267">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-267">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p124">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="4681c-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-270"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-270"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-271">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-271">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-272">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="4681c-272">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-273"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-273"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-274">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-274">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-275">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="4681c-275">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-276"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-276"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-277">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-277">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-278">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="4681c-278">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-279"><strong>Vitesse de transmission moyenne (Kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-279"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-280">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-280">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-281">Vitesse de transmission vidéo moyenne (en kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="4681c-281">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-282"><strong>Vitesse de transmission faible (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-282"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-283">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-283">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-284">Pourcentage de l’appel où la vitesse de transmission était faible.</span><span class="sxs-lookup"><span data-stu-id="4681c-284">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-285"><strong>Perte de paquets sortante</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-285"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-286">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-286">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p125">Perte de paquets RTP (Real-Time Transport Protocol) pour les paquets sortants. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-290"><strong>Image figée (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-290"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-291">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-291">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p126">Pourcentage d’images « figées ». Dans une image figée, la vidéo cesse d’avancer tandis que la partie audio de l’appel continue.</span><span class="sxs-lookup"><span data-stu-id="4681c-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-294"><strong>Fréquence d’images moyenne sortante</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-294"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-295">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-295">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-296">Fréquence d’images moyenne pour les transmissions sortantes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-296">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-297"><strong>Fréquence d’images moyenne entrante</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-297"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-298">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-298">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-299">Fréquence d’images moyenne pour les transmissions entrantes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-299">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-300"><strong>Fréquence d’images basse entrante (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-300"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-301">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-301">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-302">Pourcentage de l’appel où la vitesse de transmission pour la vidéo entrante était faible.</span><span class="sxs-lookup"><span data-stu-id="4681c-302">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-303"><strong>Intégrité des clients (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-303"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4681c-304">Indique l’intégrité relative du périphérique client pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-304">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="4681c-305">Mesures du rapport de synthèse de la qualité des médias : synthèse des appels de partage d’application</span><span class="sxs-lookup"><span data-stu-id="4681c-305">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4681c-306">Nom</span><span class="sxs-lookup"><span data-stu-id="4681c-306">Name</span></span></th>
<th><span data-ttu-id="4681c-307">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4681c-307">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4681c-308">Description</span><span class="sxs-lookup"><span data-stu-id="4681c-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4681c-309"><strong>Type d’appel/type de système d’extrémité</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-309"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-310">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-310">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p127">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4681c-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4681c-313">Appels d’égal à égal UC</span><span class="sxs-lookup"><span data-stu-id="4681c-313">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4681c-314">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="4681c-314">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4681c-315">Sessions de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="4681c-315">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4681c-316">Appels PSTN : contournement du média</span><span class="sxs-lookup"><span data-stu-id="4681c-316">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4681c-317">Appels PSTN (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="4681c-317">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4681c-318">Appels PSTN (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="4681c-318">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4681c-319">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="4681c-319">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-320"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-320"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-321">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-321">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-322">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="4681c-322">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-323"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-323"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-324">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-324">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p128">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="4681c-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-327"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-327"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-328">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-328">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-329">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="4681c-329">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-330"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-330"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-331">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-331">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-332">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="4681c-332">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-333"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-333"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-334">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-334">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-335">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="4681c-335">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-336"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-336"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-337">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-337">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-338">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="4681c-338">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4681c-339">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="4681c-339">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-340"><strong>Unilatéral relatif moyen</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-340"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-341">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-341">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-p130">Retard unilatéral relatif moyen entre deux points de terminaison du média. Il s’agit d’une mesure de latence sur un seul tronçon.</span><span class="sxs-lookup"><span data-stu-id="4681c-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4681c-344"><strong>Latence moyenne de traitement des mosaïques RDP</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-344"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-345">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-345">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-346">Latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage.</span><span class="sxs-lookup"><span data-stu-id="4681c-346">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="4681c-347">Une moyenne élevée reflète un délai plus long dans l’expérience de visualisation et inclut la latence du réseau.</span><span class="sxs-lookup"><span data-stu-id="4681c-347">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="4681c-348">Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.</span><span class="sxs-lookup"><span data-stu-id="4681c-348">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4681c-349"><strong>Nombre total de mosaïques altérées (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4681c-349"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="4681c-350">Non</span><span class="sxs-lookup"><span data-stu-id="4681c-350">No</span></span></p></td>
<td><p><span data-ttu-id="4681c-351">Pourcentage total de mosaïques RDP altérées.</span><span class="sxs-lookup"><span data-stu-id="4681c-351">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

