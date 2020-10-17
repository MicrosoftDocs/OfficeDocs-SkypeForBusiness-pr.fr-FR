---
title: 'Lync Server 2013 : rapport de liste d’appels'
description: 'Lync Server 2013 : rapport de liste d’appels.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561690"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="b5ac2-103">Rapport de liste d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5ac2-103">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5ac2-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b5ac2-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b5ac2-105">Le rapport des listes d’appels fournit des mesures de qualité de l’expérience pour les appels individuels émis et reçus dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="b5ac2-106">Notez que les mesures réelles indiquées dépendent de la façon dont vous accédez au rapport de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="b5ac2-107">Par exemple, si vous ouvrez le rapport à partir du [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md), vous verrez des métriques telles que les mesures suivantes, qui sont également signalées dans le rapport de périphérique :</span><span class="sxs-lookup"><span data-stu-id="b5ac2-107">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="b5ac2-108">Microphone de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b5ac2-108">Caller's microphone</span></span>

  - <span data-ttu-id="b5ac2-109">Haut-parleur de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b5ac2-109">Caller's speaker</span></span>

  - <span data-ttu-id="b5ac2-110">Microphone de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b5ac2-110">Callee's microphone</span></span>

  - <span data-ttu-id="b5ac2-111">Haut-parleur de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b5ac2-111">Callee's speaker</span></span>

  - <span data-ttu-id="b5ac2-112">Ratio de la durée du basculement vocal</span><span class="sxs-lookup"><span data-stu-id="b5ac2-112">Ratio of voice switch time</span></span>

<span data-ttu-id="b5ac2-113">Toutefois, si vous ouvrez le rapport liste des appels à partir du [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md), vous ne verrez aucune de ces mesures ; au lieu de cela, vous verrez des mesures comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="b5ac2-113">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="b5ac2-114">Boucle (ms)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-114">Round trip (ms)</span></span>

  - <span data-ttu-id="b5ac2-115">Dégradation (MOS)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-115">Degradation (MOS)</span></span>

  - <span data-ttu-id="b5ac2-116">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="b5ac2-116">Packet loss</span></span>

  - <span data-ttu-id="b5ac2-117">Gigue (ms)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-117">Jitter (ms)</span></span>

<span data-ttu-id="b5ac2-118">Il s’agit des mesures indiquées dans le rapport d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-118">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="b5ac2-119">Toutefois, à partir du rapport liste des appels, vous pouvez toujours cliquer sur la mesure détail pour fournir des informations QoE complètes pour tous les appels.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-119">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="b5ac2-120">Accès au rapport de liste d’appels</span><span class="sxs-lookup"><span data-stu-id="b5ac2-120">Accessing the Call List Report</span></span>

<span data-ttu-id="b5ac2-121">Le rapport des listes d’appels est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="b5ac2-121">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="b5ac2-122">Le [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-122">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b5ac2-123">Le [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-123">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b5ac2-124">Le [rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b5ac2-125">Le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b5ac2-125">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="b5ac2-126">À partir du rapport liste des appels, vous pouvez accéder au [rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) en cliquant sur la mesure détail.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-126">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="b5ac2-127">Utilisation optimale du rapport liste des appels</span><span class="sxs-lookup"><span data-stu-id="b5ac2-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="b5ac2-128">Si vous ne vous souvenez pas de la mesure des mesures du rapport de liste d’appels (par exemple, temps de commutation de voix), placez votre souris sur l’étiquette de mesure ; une info-bulle s’affiche et vous donne une brève description de la mesure.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b5ac2-129">Filtres</span><span class="sxs-lookup"><span data-stu-id="b5ac2-129">Filters</span></span>

<span data-ttu-id="b5ac2-130">Aucun.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-130">None.</span></span> <span data-ttu-id="b5ac2-131">Vous ne pouvez pas filtrer le rapport de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-131">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b5ac2-132">Mesures</span><span class="sxs-lookup"><span data-stu-id="b5ac2-132">Metrics</span></span>

<span data-ttu-id="b5ac2-133">Le tableau suivant répertorie les informations fournies dans le rapport de liste d’appels pour chaque appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-133">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="b5ac2-134">Mesures du rapport de liste d’appels</span><span class="sxs-lookup"><span data-stu-id="b5ac2-134">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5ac2-135">Nom</span><span class="sxs-lookup"><span data-stu-id="b5ac2-135">Name</span></span></th>
<th><span data-ttu-id="b5ac2-136">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="b5ac2-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b5ac2-137">Description</span><span class="sxs-lookup"><span data-stu-id="b5ac2-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-138"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-138"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-139">Non</span><span class="sxs-lookup"><span data-stu-id="b5ac2-139">No</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-140">Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-140">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-141"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-141"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-142">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-143">Adresse SIP de la personne qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-143">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-144"><strong>Appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-144"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-145">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-146">Adresse SIP de la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-146">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-147"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-147"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-148">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-148">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-149">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-149">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-150"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-150"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-151">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-152">Date et heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-152">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-153"><strong>Agent utilisateur de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-153"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-154">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-154">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-155">Logiciel utilisé par le point de terminaison de la personne qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-155">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-156"><strong>Agent utilisateur de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-156"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-157">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-157">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-158">Logiciel utilisé par le point de terminaison de la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-158">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-159"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-159"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-160">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-160">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-p104">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b5ac2-p105">Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-165"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-165"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-166">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-166">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-167">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="b5ac2-168">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="b5ac2-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="b5ac2-169">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="b5ac2-170">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="b5ac2-171">Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-171">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="b5ac2-p107">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-174"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-174"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-175">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-p108">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-179"><strong>Scintill</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-179"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-180">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-181">Gigue moyenne du délai d’arrivée entre les paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-181">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b5ac2-182">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-182">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-183"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-183"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-184">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-p110">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-187"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-187"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-188">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-188">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-p111">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ac2-191"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-191"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-192">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-p112">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ac2-195"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="b5ac2-195"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ac2-196">Oui</span><span class="sxs-lookup"><span data-stu-id="b5ac2-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="b5ac2-197">Type de liaison de communication sans fil.</span><span class="sxs-lookup"><span data-stu-id="b5ac2-197">Type of wireless communication link.</span></span> <span data-ttu-id="b5ac2-198">En règle générale, il s’agit de l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b5ac2-198">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b5ac2-199">Transmettre</span><span class="sxs-lookup"><span data-stu-id="b5ac2-199">Relay</span></span></p></li>
<li><p><span data-ttu-id="b5ac2-200">Directes</span><span class="sxs-lookup"><span data-stu-id="b5ac2-200">Direct</span></span></p></li>
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

