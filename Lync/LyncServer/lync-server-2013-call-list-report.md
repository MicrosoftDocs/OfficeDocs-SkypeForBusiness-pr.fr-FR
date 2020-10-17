---
title: 'Lync Server 2013 : rapport de liste d’appels'
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
ms.openlocfilehash: 7d9d437b32907108d5666ef9e1b175c170030585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526291"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="b89b3-102">Rapport de liste d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89b3-102">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b89b3-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b89b3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b89b3-104">Le rapport des listes d’appels fournit des mesures de qualité de l’expérience pour les appels individuels émis et reçus dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b89b3-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="b89b3-105">Notez que les mesures réelles indiquées dépendent de la façon dont vous accédez au rapport de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="b89b3-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="b89b3-106">Par exemple, si vous ouvrez le rapport à partir du [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md), vous verrez des métriques telles que les mesures suivantes, qui sont également signalées dans le rapport de périphérique :</span><span class="sxs-lookup"><span data-stu-id="b89b3-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="b89b3-107">Microphone de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b89b3-107">Caller's microphone</span></span>

  - <span data-ttu-id="b89b3-108">Haut-parleur de l’appelant</span><span class="sxs-lookup"><span data-stu-id="b89b3-108">Caller's speaker</span></span>

  - <span data-ttu-id="b89b3-109">Microphone de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b89b3-109">Callee's microphone</span></span>

  - <span data-ttu-id="b89b3-110">Haut-parleur de l’appelé</span><span class="sxs-lookup"><span data-stu-id="b89b3-110">Callee's speaker</span></span>

  - <span data-ttu-id="b89b3-111">Ratio de la durée du basculement vocal</span><span class="sxs-lookup"><span data-stu-id="b89b3-111">Ratio of voice switch time</span></span>

<span data-ttu-id="b89b3-112">Toutefois, si vous ouvrez le rapport liste des appels à partir du [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md), vous ne verrez aucune de ces mesures ; au lieu de cela, vous verrez des mesures comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="b89b3-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="b89b3-113">Boucle (ms)</span><span class="sxs-lookup"><span data-stu-id="b89b3-113">Round trip (ms)</span></span>

  - <span data-ttu-id="b89b3-114">Dégradation (MOS)</span><span class="sxs-lookup"><span data-stu-id="b89b3-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="b89b3-115">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="b89b3-115">Packet loss</span></span>

  - <span data-ttu-id="b89b3-116">Gigue (ms)</span><span class="sxs-lookup"><span data-stu-id="b89b3-116">Jitter (ms)</span></span>

<span data-ttu-id="b89b3-117">Il s’agit des mesures indiquées dans le rapport d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="b89b3-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="b89b3-118">Toutefois, à partir du rapport liste des appels, vous pouvez toujours cliquer sur la mesure détail pour fournir des informations QoE complètes pour tous les appels.</span><span class="sxs-lookup"><span data-stu-id="b89b3-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="b89b3-119">Accès au rapport de liste d’appels</span><span class="sxs-lookup"><span data-stu-id="b89b3-119">Accessing the Call List Report</span></span>

<span data-ttu-id="b89b3-120">Le rapport des listes d’appels est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="b89b3-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="b89b3-121">Le [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b89b3-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b89b3-122">Le [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b89b3-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b89b3-123">Le [rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b89b3-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b89b3-124">Le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)</span><span class="sxs-lookup"><span data-stu-id="b89b3-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="b89b3-125">À partir du rapport liste des appels, vous pouvez accéder au [rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) en cliquant sur la mesure détail.</span><span class="sxs-lookup"><span data-stu-id="b89b3-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="b89b3-126">Utilisation optimale du rapport liste des appels</span><span class="sxs-lookup"><span data-stu-id="b89b3-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="b89b3-127">Si vous ne vous souvenez pas de la mesure des mesures du rapport de liste d’appels (par exemple, temps de commutation de voix), placez votre souris sur l’étiquette de mesure ; une info-bulle s’affiche et vous donne une brève description de la mesure.</span><span class="sxs-lookup"><span data-stu-id="b89b3-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b89b3-128">Filtres</span><span class="sxs-lookup"><span data-stu-id="b89b3-128">Filters</span></span>

<span data-ttu-id="b89b3-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="b89b3-129">None.</span></span> <span data-ttu-id="b89b3-130">Vous ne pouvez pas filtrer le rapport de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="b89b3-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b89b3-131">Mesures</span><span class="sxs-lookup"><span data-stu-id="b89b3-131">Metrics</span></span>

<span data-ttu-id="b89b3-132">Le tableau suivant répertorie les informations fournies dans le rapport de liste d’appels pour chaque appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="b89b3-133">Mesures du rapport de liste d’appels</span><span class="sxs-lookup"><span data-stu-id="b89b3-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b89b3-134">Nom</span><span class="sxs-lookup"><span data-stu-id="b89b3-134">Name</span></span></th>
<th><span data-ttu-id="b89b3-135">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="b89b3-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b89b3-136">Description</span><span class="sxs-lookup"><span data-stu-id="b89b3-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-137"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-138">Non</span><span class="sxs-lookup"><span data-stu-id="b89b3-138">No</span></span></p></td>
<td><p><span data-ttu-id="b89b3-139">Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-141">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-142">Adresse SIP de la personne qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-143"><strong>Appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-144">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-145">Adresse SIP de la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b89b3-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-146"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-147">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-148">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-149"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-150">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-151">Date et heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-152"><strong>Agent utilisateur de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-153">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-154">Logiciel utilisé par le point de terminaison de la personne qui a initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-155"><strong>Agent utilisateur de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-156">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-157">Logiciel utilisé par le point de terminaison de la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="b89b3-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-158"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-159">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-p104">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b89b3-p105">Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-164"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-165">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-166">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="b89b3-167">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="b89b3-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="b89b3-168">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="b89b3-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="b89b3-169">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="b89b3-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="b89b3-170">Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</span><span class="sxs-lookup"><span data-stu-id="b89b3-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="b89b3-p107">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-173"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-174">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-p108">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-178"><strong>Scintill</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-179">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-180">Gigue moyenne du délai d’arrivée entre les paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="b89b3-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b89b3-181">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b89b3-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-182"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-183">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-p110">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-186"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-187">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-p111">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b89b3-190"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-191">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-p112">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b89b3-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b89b3-194"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="b89b3-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="b89b3-195">Oui</span><span class="sxs-lookup"><span data-stu-id="b89b3-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="b89b3-196">Type de liaison de communication sans fil.</span><span class="sxs-lookup"><span data-stu-id="b89b3-196">Type of wireless communication link.</span></span> <span data-ttu-id="b89b3-197">En règle générale, il s’agit de l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b89b3-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b89b3-198">Transmettre</span><span class="sxs-lookup"><span data-stu-id="b89b3-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="b89b3-199">Directes</span><span class="sxs-lookup"><span data-stu-id="b89b3-199">Direct</span></span></p></li>
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

