---
title: 'Lync Server 2013 : rapport de synthèse sur la qualité multimédia'
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
ms.openlocfilehash: 6980168a2d509bc32b9aa48f30167bca8721fef2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="1f3fc-102">Rapport synthèse qualité multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f3fc-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f3fc-103">_**Dernière modification de la rubrique :** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="1f3fc-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="1f3fc-104">Le rapport de synthèse de la qualité des médias permet d’analyser la qualité des appels au sein de votre organisation : ce rapport fournit des mesures d’appel de qualité de l’expérience (QoE) détaillées décomposées selon les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="1f3fc-105">Appels d’égal à égal (par exemple, Microsoft Lync 2013 vers Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="1f3fc-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="1f3fc-106">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="1f3fc-107">Sessions de conférence RTC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="1f3fc-108">Appels RTC : contournement du média</span><span class="sxs-lookup"><span data-stu-id="1f3fc-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="1f3fc-109">Appels RTC (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="1f3fc-110">Appels RTC (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="1f3fc-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="1f3fc-111">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="1f3fc-111">Other Call Types</span></span>

<span data-ttu-id="1f3fc-112">Quand vous ouvrez le rapport pour la première fois, une synthèse des informations pour chaque catégorie s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="1f3fc-113">Sans quitter le rapport, vous pouvez développer chaque catégorie pour afficher des sous-catégories, comme les appels passés à partir d’Office Communicator 2007 R2 vers Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="1f3fc-114">Vous pouvez développer également ces sous-catégories pour afficher des détails sur chaque appel passé dans cette sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="1f3fc-115">Dans Microsoft Lync Server 2013, le rapport synthèse qualité multimédia répartit les données en trois types d’appels : les appels audio, les appels vidéo et les appels de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="1f3fc-116">Chaque type d’appel correspond à une section du rapport, et dispose d’un ensemble personnalisé de mesures des appels.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="1f3fc-117">Le rapport de synthèse de la qualité des médias vous permet d’appliquer des filtres pour comparer la qualité des appels entre les appels câblés et les appels sans fil, les appels internes et externes, les appels VPN et non VPN.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="1f3fc-118">Accès au rapport de synthèse de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="1f3fc-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="1f3fc-119">Le rapport de synthèse de la qualité des médias est accessible à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="1f3fc-120">Vous pouvez explorer le rapport de la [liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="1f3fc-121">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="1f3fc-121">Call volume</span></span>

  - <span data-ttu-id="1f3fc-122">Pourcentage d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="1f3fc-122">Poor call percentage</span></span>

<span data-ttu-id="1f3fc-123">De plus, vous pouvez accéder au Rapport de distribution des mesures de qualité des médias en cliquant sur l’une des mesures d’appel audio suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="1f3fc-124">Boucle (ms)</span><span class="sxs-lookup"><span data-stu-id="1f3fc-124">Round trip (ms)</span></span>

  - <span data-ttu-id="1f3fc-125">Dégradation (MOS)</span><span class="sxs-lookup"><span data-stu-id="1f3fc-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="1f3fc-126">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="1f3fc-126">Packet loss</span></span>

  - <span data-ttu-id="1f3fc-127">Gigue (ms)</span><span class="sxs-lookup"><span data-stu-id="1f3fc-127">Jitter (ms)</span></span>

  - <span data-ttu-id="1f3fc-128">Taux de masquage de la réparation</span><span class="sxs-lookup"><span data-stu-id="1f3fc-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="1f3fc-129">Taux d’étirement de la réparation</span><span class="sxs-lookup"><span data-stu-id="1f3fc-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="1f3fc-130">Taux de compression de la réparation</span><span class="sxs-lookup"><span data-stu-id="1f3fc-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1f3fc-131">Filtres</span><span class="sxs-lookup"><span data-stu-id="1f3fc-131">Filters</span></span>

<span data-ttu-id="1f3fc-p104">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, grâce au rapport de synthèse de la qualité des médias, vous pouvez filtrer les données renvoyées selon des éléments précis, tels que le type d’accès (à savoir « accès interne » par comparaison à « accès externe ») ou la connexion réseau câblée/sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="1f3fc-136">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="1f3fc-137">Filtres du rapport de synthèse de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="1f3fc-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f3fc-138">Nom</span><span class="sxs-lookup"><span data-stu-id="1f3fc-138">Name</span></span></th>
<th><span data-ttu-id="1f3fc-139">Description</span><span class="sxs-lookup"><span data-stu-id="1f3fc-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-140"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p105">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1f3fc-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f3fc-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f3fc-p106">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f3fc-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1f3fc-146">7/7/2012</span></span></p>
<p><span data-ttu-id="1f3fc-147">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f3fc-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1f3fc-148">7/3/2012</span></span></p>
<p><span data-ttu-id="1f3fc-149">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-150"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p107">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1f3fc-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f3fc-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f3fc-p108">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f3fc-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1f3fc-156">7/7/2012</span></span></p>
<p><span data-ttu-id="1f3fc-157">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f3fc-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1f3fc-158">7/3/2012</span></span></p>
<p><span data-ttu-id="1f3fc-159">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-160"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p109">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f3fc-163">[Tous]</span><span class="sxs-lookup"><span data-stu-id="1f3fc-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-164">Interne</span><span class="sxs-lookup"><span data-stu-id="1f3fc-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-165">Externe</span><span class="sxs-lookup"><span data-stu-id="1f3fc-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-166"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p110">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f3fc-169">[Tous]</span><span class="sxs-lookup"><span data-stu-id="1f3fc-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-170">Câblé</span><span class="sxs-lookup"><span data-stu-id="1f3fc-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-171">Sans fil</span><span class="sxs-lookup"><span data-stu-id="1f3fc-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p111">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f3fc-175">[Tous]</span><span class="sxs-lookup"><span data-stu-id="1f3fc-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-176">VPN</span><span class="sxs-lookup"><span data-stu-id="1f3fc-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-177">Non-VPN</span><span class="sxs-lookup"><span data-stu-id="1f3fc-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1f3fc-178">Mesures</span><span class="sxs-lookup"><span data-stu-id="1f3fc-178">Metrics</span></span>

<span data-ttu-id="1f3fc-179">Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="1f3fc-180">Mesures du rapport de synthèse de la qualité des médias : synthèse des appels audio</span><span class="sxs-lookup"><span data-stu-id="1f3fc-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f3fc-181">Nom</span><span class="sxs-lookup"><span data-stu-id="1f3fc-181">Name</span></span></th>
<th><span data-ttu-id="1f3fc-182">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f3fc-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f3fc-183">Description</span><span class="sxs-lookup"><span data-stu-id="1f3fc-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-184"><strong>Type d’appel/type de point de terminaison</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-185">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-185">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p112">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f3fc-188">Appels P2P UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-189">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-190">Sessions de conférence RTC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-191">Appels RTC : contournement du média</span><span class="sxs-lookup"><span data-stu-id="1f3fc-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-192">Appels RTC (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-193">Appels RTC (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="1f3fc-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-194">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="1f3fc-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-195"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-196">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-196">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-197">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-198"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-199">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-199">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p113">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-202"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-203">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-203">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-204">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-205"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-206">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-206">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-207">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-208"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-209">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-209">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-210">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-211"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-212">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-212">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p114">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1f3fc-p115">Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-217"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-218">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-218">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-219">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="1f3fc-220">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="1f3fc-221">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="1f3fc-222">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="1f3fc-223">Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prévoir la façon dont les utilisateurs auraient noté un appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="1f3fc-p117">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-226"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-227">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-227">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p118">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-231"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-232">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-232">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-233">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1f3fc-234">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-235"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-236">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-236">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p120">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-239"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-240">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-240">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p121">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-243"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-244">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-244">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p122">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="1f3fc-247">Mesures du rapport de synthèse de la qualité des médias : synthèse des appels vidéo</span><span class="sxs-lookup"><span data-stu-id="1f3fc-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f3fc-248">Nom</span><span class="sxs-lookup"><span data-stu-id="1f3fc-248">Name</span></span></th>
<th><span data-ttu-id="1f3fc-249">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f3fc-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f3fc-250">Description</span><span class="sxs-lookup"><span data-stu-id="1f3fc-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-251"><strong>Type d’appel/type de point de terminaison</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-252">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-252">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p123">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f3fc-255">Appels P2P UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-256">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-257">Sessions de conférence RTC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-258">Appels RTC : contournement du média</span><span class="sxs-lookup"><span data-stu-id="1f3fc-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-259">Appels RTC (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-260">Appels RTC (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="1f3fc-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-261">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="1f3fc-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-262"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-263">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-263">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-264">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-265"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-266">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-266">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p124">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-269"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-270">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-270">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-271">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-272"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-273">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-273">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-274">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-275"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-276">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-276">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-277">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-278"><strong>Vitesse de transmission moyenne (Kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-279">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-279">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-280">Vitesse de transmission vidéo moyenne (en kilobits par seconde).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-281"><strong>Vitesse de transmission faible (%)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-282">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-282">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-283">Pourcentage de l’appel où la vitesse de transmission était faible.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-284"><strong>Perte de paquets sortante</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-285">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-285">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p125">Perte de paquets RTP (Real-Time Transport Protocol) pour les paquets sortants. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-289"><strong>Image figée (%)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-290">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-290">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p126">Pourcentage d’images « figées ». Dans une image figée, la vidéo cesse d’avancer tandis que la partie audio de l’appel continue.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-293"><strong>Fréquence d’images moyenne sortante</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-294">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-294">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-295">Fréquence d’images moyenne pour les transmissions sortantes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-296"><strong>Fréquence d’images moyenne entrante</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-297">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-297">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-298">Fréquence d’images moyenne pour les transmissions entrantes pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-299"><strong>Fréquence d’images basse entrante (%)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-300">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-300">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-301">Pourcentage de l’appel où la vitesse de transmission pour la vidéo entrante était faible.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-302"><strong>Intégrité des clients (%)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f3fc-303">Indique l’intégrité relative du périphérique client pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="1f3fc-304">Mesures du rapport de synthèse de la qualité des médias : synthèse des appels de partage d’application</span><span class="sxs-lookup"><span data-stu-id="1f3fc-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f3fc-305">Nom</span><span class="sxs-lookup"><span data-stu-id="1f3fc-305">Name</span></span></th>
<th><span data-ttu-id="1f3fc-306">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1f3fc-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f3fc-307">Description</span><span class="sxs-lookup"><span data-stu-id="1f3fc-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-308"><strong>Type d’appel/type de point de terminaison</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-309">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-309">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p127">Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f3fc-312">Appels P2P UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-313">Sessions de conférence UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-314">Sessions de conférence RTC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-315">Appels RTC : contournement du média</span><span class="sxs-lookup"><span data-stu-id="1f3fc-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-316">Appels RTC (sans contournement) : partie UC</span><span class="sxs-lookup"><span data-stu-id="1f3fc-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-317">Appels RTC (sans contournement) : partie passerelle</span><span class="sxs-lookup"><span data-stu-id="1f3fc-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="1f3fc-318">Autres types d’appels</span><span class="sxs-lookup"><span data-stu-id="1f3fc-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-319"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-320">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-320">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-321">Nombre total d’appels par type d’appel.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-322"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-323">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-323">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p128">Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-326"><strong>Volume d’appels (appels sans fil)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-327">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-327">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-328">Nombre total d’appels qui utilisaient une connexion sans fil.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-329"><strong>Volume d’appels (appels VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-330">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-330">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-331">Nombre total d’appels qui utilisaient une connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-332"><strong>Volume d’appels (appels externes)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-333">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-333">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-334">Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).</span><span class="sxs-lookup"><span data-stu-id="1f3fc-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-335"><strong>Gigue (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-336">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-336">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-337">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1f3fc-338">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-339"><strong>Unilatéral relatif moyen</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-340">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-340">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p130">Retard unilatéral relatif moyen entre deux points de terminaison du média. Il s’agit d’une mesure de latence sur un seul tronçon.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f3fc-343"><strong>Latence moyenne de traitement des mosaïques RDP</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-344">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-344">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-p131">Latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. Une moyenne élevée équivaut à une expérience de visionnage plus longue et inclut une latence du réseau. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-p131">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. A high average reflects a longer delay in the viewing experience, and includes network latency. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f3fc-348"><strong>Nombre total de mosaïques altérées (%)</strong></span><span class="sxs-lookup"><span data-stu-id="1f3fc-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="1f3fc-349">Non</span><span class="sxs-lookup"><span data-stu-id="1f3fc-349">No</span></span></p></td>
<td><p><span data-ttu-id="1f3fc-350">Pourcentage total de mosaïques RDP altérées.</span><span class="sxs-lookup"><span data-stu-id="1f3fc-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

