---
title: 'Lync Server 2013 : table AppSharingStream'
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
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="88603-102">Table AppSharingStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88603-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88603-103">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="88603-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="88603-104">La table AppSharingStream contient la mesure Qualité de l’expérience (QoE) pour les flux de données réseau utilisés pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="88603-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="88603-105">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88603-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88603-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="88603-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="88603-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="88603-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="88603-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="88603-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="88603-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="88603-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88603-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="88603-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="88603-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="88603-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="88603-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88603-113">Date et heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="88603-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88603-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-115">int</span><span class="sxs-lookup"><span data-stu-id="88603-115">int</span></span></p></td>
<td><p><span data-ttu-id="88603-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="88603-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88603-117">Identificateur séquentiel utilisé pour distinguer les sessions qui ont débuté à la même date et à la même heure.</span><span class="sxs-lookup"><span data-stu-id="88603-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="88603-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="88603-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="88603-120">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="88603-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88603-p102">Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="88603-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="88603-123">0 – audio</span><span class="sxs-lookup"><span data-stu-id="88603-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="88603-124">1 – vidéo</span><span class="sxs-lookup"><span data-stu-id="88603-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="88603-125">2 – Vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="88603-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="88603-126">3 – partage d’application/Bureau</span><span class="sxs-lookup"><span data-stu-id="88603-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="88603-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-128">int</span><span class="sxs-lookup"><span data-stu-id="88603-128">int</span></span></p></td>
<td><p><span data-ttu-id="88603-129">Primaire</span><span class="sxs-lookup"><span data-stu-id="88603-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="88603-130">Identificateur unique du flux de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="88603-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="88603-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-132">int</span><span class="sxs-lookup"><span data-stu-id="88603-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-133">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="88603-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="88603-134">(L’instabilité est une mesure &quot;de&quot; la fluctuations d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="88603-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-136">int</span><span class="sxs-lookup"><span data-stu-id="88603-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-137">Gigue maximale du délai d’arrivée entre les paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="88603-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="88603-138">(L’instabilité est une mesure &quot;de&quot; la fluctuations d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="88603-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-139"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="88603-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-140">int</span><span class="sxs-lookup"><span data-stu-id="88603-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p105">Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="88603-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="88603-p106">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou une surcharge d’un serveur multimédia. Les durées d’aller-retour élevées ont un impact sur la qualité des conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="88603-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-146">int</span><span class="sxs-lookup"><span data-stu-id="88603-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p107">Temps maximal (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="88603-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="88603-p108">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="88603-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="88603-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-152">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p109">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="88603-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-157">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p110">Taux maximal de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="88603-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="88603-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-162">int</span><span class="sxs-lookup"><span data-stu-id="88603-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-163">Nombre de paquets envoyés.</span><span class="sxs-lookup"><span data-stu-id="88603-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-164"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="88603-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-165">int</span><span class="sxs-lookup"><span data-stu-id="88603-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p111">Estimation de la quantité de bande passante unidirectionnelle disponible à la fin de la session. Indiquée en bits par seconde.</span><span class="sxs-lookup"><span data-stu-id="88603-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="88603-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-169">int</span><span class="sxs-lookup"><span data-stu-id="88603-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-170">Description de la charge utile du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="88603-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-172">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p112">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-176">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p113">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-180">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p114">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-184">int</span><span class="sxs-lookup"><span data-stu-id="88603-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p115">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-189">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p116">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-194">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p117">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-199">int</span><span class="sxs-lookup"><span data-stu-id="88603-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p118">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-204">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p119">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-209">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p120">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="88603-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="88603-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="88603-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-215">Rôle d’application (personne effectuant le partage ou spectateur) et type de contenu.</span><span class="sxs-lookup"><span data-stu-id="88603-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-217">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p121">Temps total de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="88603-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-221">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p122">Temps moyen de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="88603-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-225">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p123">Temps maximal de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="88603-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-229">int</span><span class="sxs-lookup"><span data-stu-id="88603-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p124">Occurrences de rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="88603-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-233">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p125">Densité des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="88603-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-237">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p126">Durée des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="88603-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-241">int</span><span class="sxs-lookup"><span data-stu-id="88603-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-242">Occurrences d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="88603-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-244">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p127">Densité d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une faible densité d’intervalles équivaut à une meilleure expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="88603-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-248">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-p128">Durée des intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). De brèves durées d’intervalle équivalent à une meilleure expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="88603-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-252">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-253">Taux total de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-255">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-256">Taux moyen de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-258">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-259">Taux maximal de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-261">int</span><span class="sxs-lookup"><span data-stu-id="88603-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-262">Occurrences de rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-264">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-265">Densité des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-267">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-268">Durée des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-270">int</span><span class="sxs-lookup"><span data-stu-id="88603-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-271">Occurrences d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-273">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-274">Densité d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-276">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-277">Durée des intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="88603-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-279">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-280">Pourcentage total du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-282">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-283">Pourcentage moyen du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-285">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-286">Pourcentage maximal du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-288">int</span><span class="sxs-lookup"><span data-stu-id="88603-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-289">Occurrences de rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-291">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-292">Densité des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-294">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-295">Durée des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-297">int</span><span class="sxs-lookup"><span data-stu-id="88603-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-298">Occurrences d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-300">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-301">Densité d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-303">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-304">Durée des intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="88603-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-306">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-307">Nombre total d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-309">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-310">Nombre moyen d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-312">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-313">Nombre maximal d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-315">int</span><span class="sxs-lookup"><span data-stu-id="88603-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-316">Occurrences de rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-318">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-319">Densité de rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-321">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-322">Durée des rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-324">int</span><span class="sxs-lookup"><span data-stu-id="88603-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-325">Occurrences d’intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-327">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-328">Densité d’intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-330">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-331">Durée des intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="88603-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-333">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-334">Fréquence totale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-336">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-337">Fréquence moyenne des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-339">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-340">Fréquence maximale des mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-342">int</span><span class="sxs-lookup"><span data-stu-id="88603-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-343">Occurrences de rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-345">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-346">Densité des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-348">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-349">Durée des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-351">int</span><span class="sxs-lookup"><span data-stu-id="88603-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-352">Occurrences d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-354">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-355">Densité d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-357">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-358">Durée des intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-360">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-361">Fréquence totale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-363">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-364">Fréquence moyenne des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-366">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-367">Fréquence maximale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-369">int</span><span class="sxs-lookup"><span data-stu-id="88603-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-370">Occurrences de rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-372">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-373">Densité des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-375">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-376">Durée des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-378">int</span><span class="sxs-lookup"><span data-stu-id="88603-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-379">Occurrences d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-381">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-382">Densité d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-384">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-385">Durée des intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="88603-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-387">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-388">Fréquence totale de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-390">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-391">Fréquence moyenne de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-393">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-394">Fréquence maximale de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-396">int</span><span class="sxs-lookup"><span data-stu-id="88603-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-397">Occurrences de rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-399">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-400">Densité des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-402">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-403">Durée des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-405">int</span><span class="sxs-lookup"><span data-stu-id="88603-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-406">Occurrences d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-408">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-409">Densité d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-411">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-412">Durée des intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="88603-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-414">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-415">Fréquence totale d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="88603-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-417">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-418">Fréquence moyenne d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="88603-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-420">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-421">Fréquence maximale d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-423">int</span><span class="sxs-lookup"><span data-stu-id="88603-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-424">Occurrences de rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-426">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-427">Densité des rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-429">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-430">Durée des rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="88603-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-432">int</span><span class="sxs-lookup"><span data-stu-id="88603-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-433">Occurrences d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="88603-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-435">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-436">Densité d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="88603-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-438">flottant</span><span class="sxs-lookup"><span data-stu-id="88603-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-439">Durée des intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="88603-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="88603-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-441">int</span><span class="sxs-lookup"><span data-stu-id="88603-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-442">Hauteur moyenne de résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="88603-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="88603-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-444">int</span><span class="sxs-lookup"><span data-stu-id="88603-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-445">Largeur moyenne de résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="88603-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-446"><strong>Entrant</strong></span><span class="sxs-lookup"><span data-stu-id="88603-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-447">légèrement</span><span class="sxs-lookup"><span data-stu-id="88603-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-448">Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.</span><span class="sxs-lookup"><span data-stu-id="88603-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88603-449"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="88603-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-450">légèrement</span><span class="sxs-lookup"><span data-stu-id="88603-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-451">Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.</span><span class="sxs-lookup"><span data-stu-id="88603-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88603-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="88603-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="88603-453">légèrement</span><span class="sxs-lookup"><span data-stu-id="88603-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88603-454">1 signifie que la direction du flux va de l’appelant à l’appelé.</span><span class="sxs-lookup"><span data-stu-id="88603-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="88603-455">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="88603-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

