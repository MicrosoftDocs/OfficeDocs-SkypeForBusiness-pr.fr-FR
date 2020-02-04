---
title: 'Lync Server 2013 : rapport sur la liste d’appels'
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
ms.openlocfilehash: ce2954f848d448676aea2931cda4dffa8ddc0c5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="85523-102">Rapport de liste d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85523-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85523-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="85523-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="85523-104">Le rapport Liste des appels fournit des métriques de Qualité de l’expérience pour chaque appel émis et reçu dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="85523-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="85523-105">Notez que les mesures réelles indiquées dépendent de la façon dont vous accédez au rapport Liste des appels.</span><span class="sxs-lookup"><span data-stu-id="85523-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="85523-106">Par exemple, si vous ouvrez le rapport à partir du [rapport sur les appareils dans Lync Server 2013](lync-server-2013-device-report.md), vous verrez des indicateurs tels que les métriques suivantes qui sont également signalées sur le rapport sur les appareils :</span><span class="sxs-lookup"><span data-stu-id="85523-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="85523-107">Microphone de l’appelant</span><span class="sxs-lookup"><span data-stu-id="85523-107">Caller's microphone</span></span>

  - <span data-ttu-id="85523-108">Haut-parleur de l’appelant</span><span class="sxs-lookup"><span data-stu-id="85523-108">Caller's speaker</span></span>

  - <span data-ttu-id="85523-109">Microphone de l’appelé</span><span class="sxs-lookup"><span data-stu-id="85523-109">Callee's microphone</span></span>

  - <span data-ttu-id="85523-110">Haut-parleur de l’appelé</span><span class="sxs-lookup"><span data-stu-id="85523-110">Callee's speaker</span></span>

  - <span data-ttu-id="85523-111">Ratio de la durée du basculement vocal</span><span class="sxs-lookup"><span data-stu-id="85523-111">Ratio of voice switch time</span></span>

<span data-ttu-id="85523-112">Toutefois, si vous ouvrez le rapport liste d’appels [dans le rapport d’emplacements dans Lync Server 2013](lync-server-2013-location-report.md), vous ne verrez pas l’un de ces indicateurs. à la place, vous verrez des métriques comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="85523-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="85523-113">Boucle (ms)</span><span class="sxs-lookup"><span data-stu-id="85523-113">Round trip (ms)</span></span>

  - <span data-ttu-id="85523-114">Dégradation (MOS)</span><span class="sxs-lookup"><span data-stu-id="85523-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="85523-115">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="85523-115">Packet loss</span></span>

  - <span data-ttu-id="85523-116">Gigue (ms)</span><span class="sxs-lookup"><span data-stu-id="85523-116">Jitter (ms)</span></span>

<span data-ttu-id="85523-p102">Il s’agit des mesures signalées dans le Rapport d’emplacement. Cependant, dans le rapport Liste des appels, vous pouvez toujours cliquer sur la mesure Détail pour fournir des informations de qualité de l’expérience complète pour n’importe quel appel.</span><span class="sxs-lookup"><span data-stu-id="85523-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="85523-119">Accès au rapport Liste des appels</span><span class="sxs-lookup"><span data-stu-id="85523-119">Accessing the Call List Report</span></span>

<span data-ttu-id="85523-120">Le rapport Liste des appels est accessible à partir des rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="85523-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="85523-121">Le [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur le volume des appels ou en utilisant une métrique de pourcentage médiocre)</span><span class="sxs-lookup"><span data-stu-id="85523-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="85523-122">[Rapport sur les appareils dans Lync Server 2013](lync-server-2013-device-report.md) (en cliquant sur le volume des appels ou en utilisant une métrique de pourcentage médiocre)</span><span class="sxs-lookup"><span data-stu-id="85523-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="85523-123">[Rapport synthèse sur la qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur le volume des appels ou sur le pourcentage d’appels médiocre)</span><span class="sxs-lookup"><span data-stu-id="85523-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="85523-124">Rapport sur les [performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur le volume des appels ou en utilisant une métrique de pourcentage médiocre)</span><span class="sxs-lookup"><span data-stu-id="85523-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="85523-125">Dans le rapport de la liste d’appels, vous pouvez accéder au [rapport Détails des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) en cliquant sur la métrique de détail.</span><span class="sxs-lookup"><span data-stu-id="85523-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="85523-126">Utilisation optimale du rapport Liste des appels</span><span class="sxs-lookup"><span data-stu-id="85523-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="85523-127">Si vous ne vous souvenez pas de la signification de certaines des mesures du rapport Liste des appels (par exemple, Ratio de la durée du basculement vocal), maintenez le pointeur de la souris sur l’étiquette de la mesure ; une info-bulle s’affiche et fournit une brève description de la mesure.</span><span class="sxs-lookup"><span data-stu-id="85523-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="85523-128">Filtres</span><span class="sxs-lookup"><span data-stu-id="85523-128">Filters</span></span>

<span data-ttu-id="85523-p103">Aucun. Il est impossible de filtrer le rapport de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="85523-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="85523-131">Mesures</span><span class="sxs-lookup"><span data-stu-id="85523-131">Metrics</span></span>

<span data-ttu-id="85523-132">Le tableau qui suit répertorie les informations fournies dans le rapport de liste d’appels pour chaque appel.</span><span class="sxs-lookup"><span data-stu-id="85523-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="85523-133">Mesures du rapport de liste d’appels</span><span class="sxs-lookup"><span data-stu-id="85523-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85523-134">Nom</span><span class="sxs-lookup"><span data-stu-id="85523-134">Name</span></span></th>
<th><span data-ttu-id="85523-135">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="85523-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="85523-136">Description</span><span class="sxs-lookup"><span data-stu-id="85523-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85523-137"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="85523-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-138">Non</span><span class="sxs-lookup"><span data-stu-id="85523-138">No</span></span></p></td>
<td><p><span data-ttu-id="85523-139">Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.</span><span class="sxs-lookup"><span data-stu-id="85523-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-140"><strong>Appelant</strong></span><span class="sxs-lookup"><span data-stu-id="85523-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-141">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-142">Adresse IP de la personne ayant initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="85523-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-143"><strong>Appelé</strong></span><span class="sxs-lookup"><span data-stu-id="85523-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-144">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-145">Adresse IP de la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="85523-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-146"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="85523-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-147">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-148">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="85523-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-149"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="85523-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-150">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-151">Date et heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="85523-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-152"><strong>Agent utilisateur de l’appelant</strong></span><span class="sxs-lookup"><span data-stu-id="85523-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-153">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-154">Logiciel utilisé par le point de terminaison de la personne ayant initié l’appel.</span><span class="sxs-lookup"><span data-stu-id="85523-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-155"><strong>Agent utilisateur de l’appelé</strong></span><span class="sxs-lookup"><span data-stu-id="85523-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-156">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-157">Logiciel utilisé par le point de terminaison de la personne qui a été appelée.</span><span class="sxs-lookup"><span data-stu-id="85523-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-158"><strong>Boucle (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="85523-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-159">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-p104">Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="85523-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="85523-p105">Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="85523-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-164"><strong>Dégradation (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="85523-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-165">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-166">Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel.</span><span class="sxs-lookup"><span data-stu-id="85523-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="85523-167">Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée).</span><span class="sxs-lookup"><span data-stu-id="85523-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="85523-168">Une valeur de 0,5 ou moins signifie une dégradation acceptable.</span><span class="sxs-lookup"><span data-stu-id="85523-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="85523-169">Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5.</span><span class="sxs-lookup"><span data-stu-id="85523-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="85523-170">Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prévoir la façon dont les utilisateurs auraient noté un appel.</span><span class="sxs-lookup"><span data-stu-id="85523-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="85523-p107">Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="85523-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-173"><strong>Perte de paquets</strong></span><span class="sxs-lookup"><span data-stu-id="85523-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-174">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-p108">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="85523-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-178"><strong>Gigue</strong></span><span class="sxs-lookup"><span data-stu-id="85523-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-179">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-180">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="85523-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="85523-181">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="85523-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-182"><strong>Taux de masquage de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="85523-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-183">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-p110">Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="85523-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-186"><strong>Taux d’étirement de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="85523-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-187">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-p111">Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="85523-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85523-190"><strong>Taux de compression de la réparation</strong></span><span class="sxs-lookup"><span data-stu-id="85523-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-191">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-p112">Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</span><span class="sxs-lookup"><span data-stu-id="85523-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85523-194"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="85523-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="85523-195">Oui</span><span class="sxs-lookup"><span data-stu-id="85523-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="85523-p113">Type de liaison de communication sans fil. Il s’agit en général de l’un des types suivants :</span><span class="sxs-lookup"><span data-stu-id="85523-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="85523-198">Relais</span><span class="sxs-lookup"><span data-stu-id="85523-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="85523-199">Direct</span><span class="sxs-lookup"><span data-stu-id="85523-199">Direct</span></span></p></li>
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

