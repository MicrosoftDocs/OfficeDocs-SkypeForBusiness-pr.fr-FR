---
title: 'Lync Server 2013 : table AppSharingStream'
description: 'Lync Server 2013 : table AppSharingStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574720"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="8335a-103">Table AppSharingStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8335a-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8335a-104">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="8335a-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="8335a-105">La table AppSharingStream contient la mesure Qualité de l’expérience (QoE) pour les flux de données réseau utilisés pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="8335a-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="8335a-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8335a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8335a-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8335a-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8335a-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8335a-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8335a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="8335a-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="8335a-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8335a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8335a-114">Date et heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="8335a-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-116">int</span><span class="sxs-lookup"><span data-stu-id="8335a-116">int</span></span></p></td>
<td><p><span data-ttu-id="8335a-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8335a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8335a-118">Identificateur séquentiel utilisé pour distinguer les sessions qui ont débuté à la même date et à la même heure.</span><span class="sxs-lookup"><span data-stu-id="8335a-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="8335a-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8335a-121">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="8335a-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8335a-p102">Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8335a-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8335a-124">0 – audio</span><span class="sxs-lookup"><span data-stu-id="8335a-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="8335a-125">1 – vidéo</span><span class="sxs-lookup"><span data-stu-id="8335a-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="8335a-126">2 – Vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="8335a-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="8335a-127">3 – partage d’application/Bureau</span><span class="sxs-lookup"><span data-stu-id="8335a-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-129">int</span><span class="sxs-lookup"><span data-stu-id="8335a-129">int</span></span></p></td>
<td><p><span data-ttu-id="8335a-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="8335a-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="8335a-131">Identificateur unique du flux de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="8335a-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-133">int</span><span class="sxs-lookup"><span data-stu-id="8335a-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-134">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="8335a-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8335a-135">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="8335a-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-137">int</span><span class="sxs-lookup"><span data-stu-id="8335a-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-138">Gigue maximale du délai d’arrivée entre les paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="8335a-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8335a-139">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="8335a-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-140"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-141">int</span><span class="sxs-lookup"><span data-stu-id="8335a-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p105">Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="8335a-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8335a-p106">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="8335a-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-147">int</span><span class="sxs-lookup"><span data-stu-id="8335a-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p107">Temps maximal (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="8335a-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8335a-p108">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="8335a-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-153">float</span><span class="sxs-lookup"><span data-stu-id="8335a-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p109">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="8335a-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-158">float</span><span class="sxs-lookup"><span data-stu-id="8335a-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p110">Taux maximal de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="8335a-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-163">int</span><span class="sxs-lookup"><span data-stu-id="8335a-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-164">Nombre de paquets envoyés.</span><span class="sxs-lookup"><span data-stu-id="8335a-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-165"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-166">int</span><span class="sxs-lookup"><span data-stu-id="8335a-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p111">Estimation de la quantité de bande passante unidirectionnelle disponible à la fin de la session. Indiquée en bits par seconde.</span><span class="sxs-lookup"><span data-stu-id="8335a-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-170">int</span><span class="sxs-lookup"><span data-stu-id="8335a-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-171">Description de la charge utile du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="8335a-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-173">float</span><span class="sxs-lookup"><span data-stu-id="8335a-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p112">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-177">float</span><span class="sxs-lookup"><span data-stu-id="8335a-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p113">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-181">float</span><span class="sxs-lookup"><span data-stu-id="8335a-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p114">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-185">int</span><span class="sxs-lookup"><span data-stu-id="8335a-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p115">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-190">float</span><span class="sxs-lookup"><span data-stu-id="8335a-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p116">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-195">float</span><span class="sxs-lookup"><span data-stu-id="8335a-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p117">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-200">int</span><span class="sxs-lookup"><span data-stu-id="8335a-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p118">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-205">float</span><span class="sxs-lookup"><span data-stu-id="8335a-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p119">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-210">float</span><span class="sxs-lookup"><span data-stu-id="8335a-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p120">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="8335a-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="8335a-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-216">Rôle d’application (personne effectuant le partage ou spectateur) et type de contenu.</span><span class="sxs-lookup"><span data-stu-id="8335a-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-218">float</span><span class="sxs-lookup"><span data-stu-id="8335a-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p121">Temps total de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="8335a-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-222">float</span><span class="sxs-lookup"><span data-stu-id="8335a-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p122">Temps moyen de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="8335a-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-226">float</span><span class="sxs-lookup"><span data-stu-id="8335a-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p123">Temps maximal de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="8335a-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-230">int</span><span class="sxs-lookup"><span data-stu-id="8335a-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p124">Occurrences de rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="8335a-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-234">float</span><span class="sxs-lookup"><span data-stu-id="8335a-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p125">Densité des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="8335a-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-238">float</span><span class="sxs-lookup"><span data-stu-id="8335a-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p126">Durée des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="8335a-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-242">int</span><span class="sxs-lookup"><span data-stu-id="8335a-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-243">Occurrences d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="8335a-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-245">float</span><span class="sxs-lookup"><span data-stu-id="8335a-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p127">Densité d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une faible densité d’intervalles équivaut à une meilleure expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="8335a-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-249">float</span><span class="sxs-lookup"><span data-stu-id="8335a-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-p128">Durée des intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). De brèves durées d’intervalle équivalent à une meilleure expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="8335a-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-253">float</span><span class="sxs-lookup"><span data-stu-id="8335a-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-254">Taux total de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-256">float</span><span class="sxs-lookup"><span data-stu-id="8335a-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-257">Taux moyen de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-259">float</span><span class="sxs-lookup"><span data-stu-id="8335a-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-260">Taux maximal de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-262">int</span><span class="sxs-lookup"><span data-stu-id="8335a-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-263">Occurrences de rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-265">float</span><span class="sxs-lookup"><span data-stu-id="8335a-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-266">Densité des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-268">float</span><span class="sxs-lookup"><span data-stu-id="8335a-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-269">Durée des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-271">int</span><span class="sxs-lookup"><span data-stu-id="8335a-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-272">Occurrences d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-274">float</span><span class="sxs-lookup"><span data-stu-id="8335a-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-275">Densité d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-277">float</span><span class="sxs-lookup"><span data-stu-id="8335a-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-278">Durée des intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="8335a-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-280">float</span><span class="sxs-lookup"><span data-stu-id="8335a-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-281">Pourcentage total du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-283">float</span><span class="sxs-lookup"><span data-stu-id="8335a-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-284">Pourcentage moyen du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-286">float</span><span class="sxs-lookup"><span data-stu-id="8335a-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-287">Pourcentage maximal du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-289">int</span><span class="sxs-lookup"><span data-stu-id="8335a-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-290">Occurrences de rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-292">float</span><span class="sxs-lookup"><span data-stu-id="8335a-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-293">Densité des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-295">float</span><span class="sxs-lookup"><span data-stu-id="8335a-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-296">Durée des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-298">int</span><span class="sxs-lookup"><span data-stu-id="8335a-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-299">Occurrences d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-301">float</span><span class="sxs-lookup"><span data-stu-id="8335a-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-302">Densité d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-304">float</span><span class="sxs-lookup"><span data-stu-id="8335a-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-305">Durée des intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="8335a-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-307">float</span><span class="sxs-lookup"><span data-stu-id="8335a-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-308">Nombre total d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-310">float</span><span class="sxs-lookup"><span data-stu-id="8335a-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-311">Nombre moyen d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-313">float</span><span class="sxs-lookup"><span data-stu-id="8335a-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-314">Nombre maximal d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-316">int</span><span class="sxs-lookup"><span data-stu-id="8335a-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-317">Occurrences de rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-319">float</span><span class="sxs-lookup"><span data-stu-id="8335a-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-320">Densité de rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-322">float</span><span class="sxs-lookup"><span data-stu-id="8335a-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-323">Durée des rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-325">int</span><span class="sxs-lookup"><span data-stu-id="8335a-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-326">Occurrences d’intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-328">float</span><span class="sxs-lookup"><span data-stu-id="8335a-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-329">Densité d’intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-331">float</span><span class="sxs-lookup"><span data-stu-id="8335a-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-332">Durée des intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="8335a-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-334">float</span><span class="sxs-lookup"><span data-stu-id="8335a-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-335">Fréquence totale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-337">float</span><span class="sxs-lookup"><span data-stu-id="8335a-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-338">Fréquence moyenne des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-340">float</span><span class="sxs-lookup"><span data-stu-id="8335a-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-341">Fréquence maximale des mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-343">int</span><span class="sxs-lookup"><span data-stu-id="8335a-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-344">Occurrences de rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-346">float</span><span class="sxs-lookup"><span data-stu-id="8335a-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-347">Densité des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-349">float</span><span class="sxs-lookup"><span data-stu-id="8335a-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-350">Durée des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-352">int</span><span class="sxs-lookup"><span data-stu-id="8335a-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-353">Occurrences d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-355">float</span><span class="sxs-lookup"><span data-stu-id="8335a-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-356">Densité d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-358">float</span><span class="sxs-lookup"><span data-stu-id="8335a-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-359">Durée des intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-361">float</span><span class="sxs-lookup"><span data-stu-id="8335a-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-362">Fréquence totale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-364">float</span><span class="sxs-lookup"><span data-stu-id="8335a-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-365">Fréquence moyenne des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-367">float</span><span class="sxs-lookup"><span data-stu-id="8335a-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-368">Fréquence maximale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-370">int</span><span class="sxs-lookup"><span data-stu-id="8335a-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-371">Occurrences de rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-373">float</span><span class="sxs-lookup"><span data-stu-id="8335a-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-374">Densité des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-376">float</span><span class="sxs-lookup"><span data-stu-id="8335a-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-377">Durée des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-379">int</span><span class="sxs-lookup"><span data-stu-id="8335a-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-380">Occurrences d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-382">float</span><span class="sxs-lookup"><span data-stu-id="8335a-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-383">Densité d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-385">float</span><span class="sxs-lookup"><span data-stu-id="8335a-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-386">Durée des intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8335a-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-388">float</span><span class="sxs-lookup"><span data-stu-id="8335a-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-389">Fréquence totale de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-391">float</span><span class="sxs-lookup"><span data-stu-id="8335a-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-392">Fréquence moyenne de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-394">float</span><span class="sxs-lookup"><span data-stu-id="8335a-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-395">Fréquence maximale de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-397">int</span><span class="sxs-lookup"><span data-stu-id="8335a-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-398">Occurrences de rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-400">float</span><span class="sxs-lookup"><span data-stu-id="8335a-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-401">Densité des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-403">float</span><span class="sxs-lookup"><span data-stu-id="8335a-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-404">Durée des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-406">int</span><span class="sxs-lookup"><span data-stu-id="8335a-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-407">Occurrences d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-409">float</span><span class="sxs-lookup"><span data-stu-id="8335a-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-410">Densité d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-412">float</span><span class="sxs-lookup"><span data-stu-id="8335a-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-413">Durée des intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-415">float</span><span class="sxs-lookup"><span data-stu-id="8335a-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-416">Fréquence totale d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-418">float</span><span class="sxs-lookup"><span data-stu-id="8335a-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-419">Fréquence moyenne d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-421">float</span><span class="sxs-lookup"><span data-stu-id="8335a-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-422">Fréquence maximale d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-424">int</span><span class="sxs-lookup"><span data-stu-id="8335a-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-425">Occurrences de rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-427">float</span><span class="sxs-lookup"><span data-stu-id="8335a-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-428">Densité des rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-430">float</span><span class="sxs-lookup"><span data-stu-id="8335a-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-431">Durée des rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-433">int</span><span class="sxs-lookup"><span data-stu-id="8335a-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-434">Occurrences d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-436">float</span><span class="sxs-lookup"><span data-stu-id="8335a-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-437">Densité d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-439">float</span><span class="sxs-lookup"><span data-stu-id="8335a-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-440">Durée des intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="8335a-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-442">int</span><span class="sxs-lookup"><span data-stu-id="8335a-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-443">Hauteur moyenne de résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="8335a-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-445">int</span><span class="sxs-lookup"><span data-stu-id="8335a-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-446">Largeur moyenne de résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="8335a-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-447"><strong>Entrants</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-448">légèrement</span><span class="sxs-lookup"><span data-stu-id="8335a-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-449">Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.</span><span class="sxs-lookup"><span data-stu-id="8335a-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8335a-450"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-451">légèrement</span><span class="sxs-lookup"><span data-stu-id="8335a-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-452">Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.</span><span class="sxs-lookup"><span data-stu-id="8335a-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8335a-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="8335a-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="8335a-454">légèrement</span><span class="sxs-lookup"><span data-stu-id="8335a-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8335a-455">1 signifie que la direction du flux va de l’appelant à l’appelé.</span><span class="sxs-lookup"><span data-stu-id="8335a-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="8335a-456">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="8335a-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

