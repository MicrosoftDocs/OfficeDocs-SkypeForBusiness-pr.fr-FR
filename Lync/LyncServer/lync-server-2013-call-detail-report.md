---
title: 'Lync Server 2013 : rapport détaillé des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb57cde990e4c4218297c69aeb3c8933f9a3fd92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="b7fb5-102">Rapport détaillé des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7fb5-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7fb5-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b7fb5-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b7fb5-104">Le rapport sur le détail de l’appel fournit un aperçu détaillé d’un appel individuel ; le rapport inclut presque toutes les mesures de qualité de l’expérience et les statistiques collectées par Lync Server, divisée en sections de rapport, telles que :</span><span class="sxs-lookup"><span data-stu-id="b7fb5-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="b7fb5-105">Informations d’appel</span><span class="sxs-lookup"><span data-stu-id="b7fb5-105">Call Information</span></span>

  - <span data-ttu-id="b7fb5-106">Mesures du signal et du périphérique de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b7fb5-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="b7fb5-107">Mesures du signal et du périphérique de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b7fb5-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="b7fb5-108">Événement client de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b7fb5-108">Caller Client Event</span></span>

  - <span data-ttu-id="b7fb5-109">Événement client de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b7fb5-109">Callee Client Event</span></span>

  - <span data-ttu-id="b7fb5-110">Flux de données audio (de l’appelant vers l’appelé)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="b7fb5-111">Flux de données vidéo (de l’appelant vers l’appelé)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="b7fb5-112">Flux de données audio (de l’appelé vers l’appelant)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="b7fb5-113">Flux de données vidéo (de l’appelé vers l’appelant)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="b7fb5-p101">Gardez à l’esprit que les catégories et les mesures qui figurent dans un rapport donné dépendent de deux facteurs : du type de session et du type des systèmes d’extrémité utilisés dans la session. Par exemple, un appel audio ne fait l’objet d’aucune mesure de flux de données vidéo, car il n’en comporte pas. De même, il peut arriver qu’un rapport répertorie des statistiques sur l’appelant mais pas sur l’appelé. En règle générale, cela est dû au fait que l’appelé utilise un appareil non compatible SIP. La génération de statistiques à la fin d’un appel est une tâche qui incombe aux systèmes d’extrémité. Or, un téléphone cellulaire (qui n’a pas connaissance de SIP ni des statistiques SIP) n’est pas capable de fournir ce type d’information. Si vous appelez une personne et qu’elle vous répond sur son téléphone cellulaire, vous n’obtiendrez pas de rapport de ce téléphone à la fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="b7fb5-120">Le rapport sur le détail de l’appel s’avère particulièrement utile pour identifier les causes exactes des problèmes de qualité des médias rencontrés lors d’un appel donné.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="b7fb5-121">Accès au rapport sur le détail de l’appel</span><span class="sxs-lookup"><span data-stu-id="b7fb5-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="b7fb5-122">Le rapport sur le détail de l’appel est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="b7fb5-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="b7fb5-123">Le [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="b7fb5-124">Le [rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b7fb5-125">Le [rapport de comparaison de la qualité des médias dans Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (en cliquant sur le [rapport liste des appels dans Lync Server 2013](lync-server-2013-call-list-report.md) , puis en cliquant sur la mesure détail).</span><span class="sxs-lookup"><span data-stu-id="b7fb5-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="b7fb5-126">Le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b7fb5-127">Le [rapport liste des appels dans Lync Server 2013](lync-server-2013-call-list-report.md) (en cliquant sur la mesure détail)</span><span class="sxs-lookup"><span data-stu-id="b7fb5-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="b7fb5-128">À partir du rapport sur le détail de l’appel, vous pouvez accéder au [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7fb5-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b7fb5-129">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="b7fb5-129">Capture device</span></span>

  - <span data-ttu-id="b7fb5-130">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="b7fb5-130">Render device</span></span>

<span data-ttu-id="b7fb5-131">Vous pouvez aussi accéder au Rapport de tendance générale de la qualité des médias serveur en cliquant sur la mesure Serveur Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="b7fb5-132">Utilisation optimale du rapport sur le détail de l’appel</span><span class="sxs-lookup"><span data-stu-id="b7fb5-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="b7fb5-p102">En règle générale, le rapport sur le détail de l’appel comprend plus de 250 mesures différentes, avec notamment les éléments Dérive d’horodatage du microphone, Durée du SNR faible et Durée de l’écho au point de terminaison. Si vous ne vous rappelez pas de la fonction de l’une de ces nombreuses mesures, placez le curseur de la souris sur l’étiquette de la mesure ; vous devriez obtenir une info-bulle décrivant cette mesure.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="b7fb5-p103">Si vous avez des difficultés à retrouver une mesure, tapez une partie de son nom dans la zone de recherche et cliquez sur Rechercher. Par exemple, si vous ne trouvez pas la mesure Durée du SNR faible, tapez SNR dans la zone de recherche, puis cliquez sur Rechercher.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="b7fb5-137">Notez que le rapport effectue uniquement le suivi des informations relatives à un appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="b7fb5-138">L’appel lui-même n’est pas enregistré.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b7fb5-139">Filtres</span><span class="sxs-lookup"><span data-stu-id="b7fb5-139">Filters</span></span>

<span data-ttu-id="b7fb5-p105">Aucun. Vous ne pouvez pas filtrer le rapport sur le détail de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b7fb5-142">Mesures</span><span class="sxs-lookup"><span data-stu-id="b7fb5-142">Metrics</span></span>

<span data-ttu-id="b7fb5-143">Le tableau suivant liste les informations fournies dans le rapport sur le détail de l’appel pour chaque appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="b7fb5-144">Mesures du rapport sur le détail de l’appel</span><span class="sxs-lookup"><span data-stu-id="b7fb5-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7fb5-145">Nom</span><span class="sxs-lookup"><span data-stu-id="b7fb5-145">Name</span></span></th>
<th><span data-ttu-id="b7fb5-146">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="b7fb5-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b7fb5-147">Description</span><span class="sxs-lookup"><span data-stu-id="b7fb5-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-148"><strong>PAI de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-149">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-149">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-p106">PAI (P-Asserted-Identity) de l’utilisateur qui a initié l’appel. La PAI sert à transmettre l’identité prouvée d’un utilisateur au sein d’un réseau approuvé.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-152"><strong>URI de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-153">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-153">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-154">Adresse SIP de l’utilisateur qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-155"><strong>Système d’extrémité de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-156">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-156">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-157">Appareil utilisé pour passer l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-158"><strong>Agent utilisateur de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-159">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-159">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-160">Logiciel utilisé sur l’appareil utilisé pour passer l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-161"><strong>Début de l’appel</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-162">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-162">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-163">Date et heure où l’appel a été passé.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-164"><strong>Appel de contournement du serveur de médiation</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-165">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-165">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-166">Indique si l’appel connecté à une passerelle vocale PSTN ou IP-PBX qualifié sans passer par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-167"><strong>SE de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-168">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-168">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-169">Système d’exploitation de l’ordinateur de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-170"><strong>UC de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-171">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-171">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-172">UC installée dans l’ordinateur de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-173"><strong>Numéro principal de l’UC de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-174">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-174">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-175">Numéro de processeur dans l’ordinateur utilisé par la personne qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-176"><strong>Vitesse de l’UC de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-177">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-177">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-178">Vitesse d’horloge de l’UC de l’ordinateur utilisé par la personne qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-179"><strong>Virtualisation de l’UC de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-180">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-180">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-181">Virtualisation (le cas échéant) utilisée sur l’ordinateur utilisé par la personne qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-182"><strong>PAI de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-183">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-183">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-p107">PAI (P-Asserted-Identity) de l’utilisateur qui a été invité à participer à l’appel. La PAI sert à transmettre l’identité prouvée d’un utilisateur au sein d’un réseau approuvé.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-186"><strong>URI de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-187">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-187">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-188">Adresse SIP de l’utilisateur appelé.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-189"><strong>Système d’extrémité de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-190">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-190">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-191">Appareil utilisé pour recevoir l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-192"><strong>Agent utilisateur de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-193">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-193">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-194">Logiciel utilisé sur l’appareil qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-195"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-196">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-196">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-197">Durée de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-198"><strong>Indicateur d’avertissement de contournement de média</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-199">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-199">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-200">Avertissement paru quand le serveur de médiation a été contourné.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-201"><strong>SE de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-202">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-202">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-203">Système d’exploitation de l’ordinateur de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-204"><strong>UC de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-205">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-205">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-206">UC installée dans l’ordinateur de l’utilisateur qui a été appelé.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-207"><strong>Numéro principal de l’UC de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-208">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-208">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-209">Numéro de processeur dans l’ordinateur utilisé par la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fb5-210"><strong>Vitesse de l’UC de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-211">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-211">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-212">Vitesse d’horloge de l’UC de l’ordinateur utilisé par la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fb5-213"><strong>Virtualisation de l’UC de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b7fb5-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="b7fb5-214">Non</span><span class="sxs-lookup"><span data-stu-id="b7fb5-214">No</span></span></p></td>
<td><p><span data-ttu-id="b7fb5-215">Virtualisation (le cas échéant) utilisée sur l’ordinateur utilisé par la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b7fb5-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

