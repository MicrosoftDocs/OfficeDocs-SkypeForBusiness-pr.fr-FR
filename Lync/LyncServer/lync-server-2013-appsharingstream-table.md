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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499501"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="983c8-102">Table AppSharingStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="983c8-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="983c8-103">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="983c8-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="983c8-104">La table AppSharingStream contient la mesure Qualité de l’expérience (QoE) pour les flux de données réseau utilisés pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="983c8-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="983c8-105">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="983c8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="983c8-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="983c8-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="983c8-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="983c8-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="983c8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="983c8-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="983c8-112">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="983c8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="983c8-113">Date et heure de début de la session.</span><span class="sxs-lookup"><span data-stu-id="983c8-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-115">int</span><span class="sxs-lookup"><span data-stu-id="983c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="983c8-116">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="983c8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="983c8-117">Identificateur séquentiel utilisé pour distinguer les sessions qui ont débuté à la même date et à la même heure.</span><span class="sxs-lookup"><span data-stu-id="983c8-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="983c8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="983c8-120">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="983c8-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="983c8-p102">Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="983c8-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="983c8-123">0 – audio</span><span class="sxs-lookup"><span data-stu-id="983c8-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="983c8-124">1 – vidéo</span><span class="sxs-lookup"><span data-stu-id="983c8-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="983c8-125">2 – Vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="983c8-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="983c8-126">3 – partage d’application/Bureau</span><span class="sxs-lookup"><span data-stu-id="983c8-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-128">int</span><span class="sxs-lookup"><span data-stu-id="983c8-128">int</span></span></p></td>
<td><p><span data-ttu-id="983c8-129">Primaire</span><span class="sxs-lookup"><span data-stu-id="983c8-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="983c8-130">Identificateur unique du flux de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="983c8-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-132">int</span><span class="sxs-lookup"><span data-stu-id="983c8-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-133">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="983c8-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="983c8-134">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="983c8-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-136">int</span><span class="sxs-lookup"><span data-stu-id="983c8-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-137">Gigue maximale du délai d’arrivée entre les paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="983c8-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="983c8-138">(L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="983c8-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-139"><strong>Retour</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-140">int</span><span class="sxs-lookup"><span data-stu-id="983c8-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p105">Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="983c8-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="983c8-p106">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="983c8-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-146">int</span><span class="sxs-lookup"><span data-stu-id="983c8-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p107">Temps maximal (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="983c8-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="983c8-p108">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="983c8-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-152">float</span><span class="sxs-lookup"><span data-stu-id="983c8-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p109">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="983c8-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-157">float</span><span class="sxs-lookup"><span data-stu-id="983c8-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p110">Taux maximal de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="983c8-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-162">int</span><span class="sxs-lookup"><span data-stu-id="983c8-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-163">Nombre de paquets envoyés.</span><span class="sxs-lookup"><span data-stu-id="983c8-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-164"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-165">int</span><span class="sxs-lookup"><span data-stu-id="983c8-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p111">Estimation de la quantité de bande passante unidirectionnelle disponible à la fin de la session. Indiquée en bits par seconde.</span><span class="sxs-lookup"><span data-stu-id="983c8-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-169">int</span><span class="sxs-lookup"><span data-stu-id="983c8-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-170">Description de la charge utile du partage d’application.</span><span class="sxs-lookup"><span data-stu-id="983c8-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-172">float</span><span class="sxs-lookup"><span data-stu-id="983c8-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p112">Quantité totale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-176">float</span><span class="sxs-lookup"><span data-stu-id="983c8-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p113">Quantité moyenne de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-180">float</span><span class="sxs-lookup"><span data-stu-id="983c8-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p114">Quantité maximale de latence unidirectionnelle. La latence unidirectionnelle relative mesure le retard entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-184">int</span><span class="sxs-lookup"><span data-stu-id="983c8-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p115">Nombre total d’occurrences de rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-189">float</span><span class="sxs-lookup"><span data-stu-id="983c8-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p116">Densité totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-194">float</span><span class="sxs-lookup"><span data-stu-id="983c8-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p117">Durée totale des rafales unidirectionnelles. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-199">int</span><span class="sxs-lookup"><span data-stu-id="983c8-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p118">Nombre total d’occurrences d’intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-204">float</span><span class="sxs-lookup"><span data-stu-id="983c8-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p119">Densité totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-209">float</span><span class="sxs-lookup"><span data-stu-id="983c8-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p120">Durée totale des intervalles unidirectionnels. Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier ; les intervalles indiquent les retards entre les rafales. Cette valeur mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="983c8-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="983c8-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-215">Rôle d’application (personne effectuant le partage ou spectateur) et type de contenu.</span><span class="sxs-lookup"><span data-stu-id="983c8-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-217">float</span><span class="sxs-lookup"><span data-stu-id="983c8-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p121">Temps total de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="983c8-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-221">float</span><span class="sxs-lookup"><span data-stu-id="983c8-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p122">Temps moyen de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="983c8-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-225">float</span><span class="sxs-lookup"><span data-stu-id="983c8-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p123">Temps maximal de traitement des mosaïques RDP (Remote Desktop Protocol). Un total plus élevé équivaut à une expérience de visionnage plus longue.</span><span class="sxs-lookup"><span data-stu-id="983c8-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-229">int</span><span class="sxs-lookup"><span data-stu-id="983c8-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p124">Occurrences de rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="983c8-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-233">float</span><span class="sxs-lookup"><span data-stu-id="983c8-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p125">Densité des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="983c8-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-237">float</span><span class="sxs-lookup"><span data-stu-id="983c8-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p126">Durée des rafales dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Dans une transmission « par rafales », les données sont transmises de façon sporadique contrairement à un flux de données régulier.</span><span class="sxs-lookup"><span data-stu-id="983c8-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-241">int</span><span class="sxs-lookup"><span data-stu-id="983c8-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-242">Occurrences d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="983c8-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-244">float</span><span class="sxs-lookup"><span data-stu-id="983c8-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p127">Densité d’intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). Une faible densité d’intervalles équivaut à une meilleure expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="983c8-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-248">float</span><span class="sxs-lookup"><span data-stu-id="983c8-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-p128">Durée des intervalles dans le temps de traitement des mosaïques RDP (Remote Desktop Protocol). De brèves durées d’intervalle équivalent à une meilleure expérience de visionnage.</span><span class="sxs-lookup"><span data-stu-id="983c8-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-252">float</span><span class="sxs-lookup"><span data-stu-id="983c8-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-253">Taux total de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-255">float</span><span class="sxs-lookup"><span data-stu-id="983c8-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-256">Taux moyen de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-258">float</span><span class="sxs-lookup"><span data-stu-id="983c8-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-259">Taux maximal de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-261">int</span><span class="sxs-lookup"><span data-stu-id="983c8-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-262">Occurrences de rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-264">float</span><span class="sxs-lookup"><span data-stu-id="983c8-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-265">Densité des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-267">float</span><span class="sxs-lookup"><span data-stu-id="983c8-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-268">Durée des rafales dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-270">int</span><span class="sxs-lookup"><span data-stu-id="983c8-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-271">Occurrences d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-273">float</span><span class="sxs-lookup"><span data-stu-id="983c8-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-274">Densité d’intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-276">float</span><span class="sxs-lookup"><span data-stu-id="983c8-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-277">Durée des intervalles dans le taux de mosaïques capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="983c8-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-279">float</span><span class="sxs-lookup"><span data-stu-id="983c8-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-280">Pourcentage total du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-282">float</span><span class="sxs-lookup"><span data-stu-id="983c8-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-283">Pourcentage moyen du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-285">float</span><span class="sxs-lookup"><span data-stu-id="983c8-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-286">Pourcentage maximal du contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-288">int</span><span class="sxs-lookup"><span data-stu-id="983c8-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-289">Occurrences de rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-291">float</span><span class="sxs-lookup"><span data-stu-id="983c8-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-292">Densité des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-294">float</span><span class="sxs-lookup"><span data-stu-id="983c8-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-295">Durée des rafales pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-297">int</span><span class="sxs-lookup"><span data-stu-id="983c8-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-298">Occurrences d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-300">float</span><span class="sxs-lookup"><span data-stu-id="983c8-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-301">Densité d’intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-303">float</span><span class="sxs-lookup"><span data-stu-id="983c8-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-304">Durée des intervalles pour le contenu qui n’a pas atteint le spectateur mais qui a été ignoré et remplacé par du contenu récent.</span><span class="sxs-lookup"><span data-stu-id="983c8-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-306">float</span><span class="sxs-lookup"><span data-stu-id="983c8-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-307">Nombre total d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-309">float</span><span class="sxs-lookup"><span data-stu-id="983c8-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-310">Nombre moyen d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-312">float</span><span class="sxs-lookup"><span data-stu-id="983c8-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-313">Nombre maximal d’images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-315">int</span><span class="sxs-lookup"><span data-stu-id="983c8-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-316">Occurrences de rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-318">float</span><span class="sxs-lookup"><span data-stu-id="983c8-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-319">Densité de rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-321">float</span><span class="sxs-lookup"><span data-stu-id="983c8-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-322">Durée des rafales dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-324">int</span><span class="sxs-lookup"><span data-stu-id="983c8-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-325">Occurrences d’intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-327">float</span><span class="sxs-lookup"><span data-stu-id="983c8-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-328">Densité d’intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-330">float</span><span class="sxs-lookup"><span data-stu-id="983c8-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-331">Durée des intervalles dans les images récupérées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="983c8-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-333">float</span><span class="sxs-lookup"><span data-stu-id="983c8-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-334">Fréquence totale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-336">float</span><span class="sxs-lookup"><span data-stu-id="983c8-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-337">Fréquence moyenne des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-339">float</span><span class="sxs-lookup"><span data-stu-id="983c8-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-340">Fréquence maximale des mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-342">int</span><span class="sxs-lookup"><span data-stu-id="983c8-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-343">Occurrences de rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-345">float</span><span class="sxs-lookup"><span data-stu-id="983c8-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-346">Densité des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-348">float</span><span class="sxs-lookup"><span data-stu-id="983c8-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-349">Durée des rafales dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-351">int</span><span class="sxs-lookup"><span data-stu-id="983c8-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-352">Occurrences d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-354">float</span><span class="sxs-lookup"><span data-stu-id="983c8-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-355">Densité d’intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-357">float</span><span class="sxs-lookup"><span data-stu-id="983c8-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-358">Durée des intervalles dans la fréquence de mosaïques entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-360">float</span><span class="sxs-lookup"><span data-stu-id="983c8-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-361">Fréquence totale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-363">float</span><span class="sxs-lookup"><span data-stu-id="983c8-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-364">Fréquence moyenne des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-366">float</span><span class="sxs-lookup"><span data-stu-id="983c8-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-367">Fréquence maximale des images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-369">int</span><span class="sxs-lookup"><span data-stu-id="983c8-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-370">Occurrences de rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-372">float</span><span class="sxs-lookup"><span data-stu-id="983c8-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-373">Densité des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-375">float</span><span class="sxs-lookup"><span data-stu-id="983c8-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-376">Durée des rafales dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-378">int</span><span class="sxs-lookup"><span data-stu-id="983c8-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-379">Occurrences d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-381">float</span><span class="sxs-lookup"><span data-stu-id="983c8-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-382">Densité d’intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-384">float</span><span class="sxs-lookup"><span data-stu-id="983c8-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-385">Durée des intervalles dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="983c8-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-387">float</span><span class="sxs-lookup"><span data-stu-id="983c8-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-388">Fréquence totale de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-390">float</span><span class="sxs-lookup"><span data-stu-id="983c8-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-391">Fréquence moyenne de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-393">float</span><span class="sxs-lookup"><span data-stu-id="983c8-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-394">Fréquence maximale de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-396">int</span><span class="sxs-lookup"><span data-stu-id="983c8-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-397">Occurrences de rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-399">float</span><span class="sxs-lookup"><span data-stu-id="983c8-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-400">Densité des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-402">float</span><span class="sxs-lookup"><span data-stu-id="983c8-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-403">Durée des rafales dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-405">int</span><span class="sxs-lookup"><span data-stu-id="983c8-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-406">Occurrences d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-408">float</span><span class="sxs-lookup"><span data-stu-id="983c8-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-409">Densité d’intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-411">float</span><span class="sxs-lookup"><span data-stu-id="983c8-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-412">Durée des intervalles dans la fréquence de mosaïques sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-414">float</span><span class="sxs-lookup"><span data-stu-id="983c8-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-415">Fréquence totale d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-417">float</span><span class="sxs-lookup"><span data-stu-id="983c8-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-418">Fréquence moyenne d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-420">float</span><span class="sxs-lookup"><span data-stu-id="983c8-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-421">Fréquence maximale d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-423">int</span><span class="sxs-lookup"><span data-stu-id="983c8-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-424">Occurrences de rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-426">float</span><span class="sxs-lookup"><span data-stu-id="983c8-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-427">Densité des rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-429">float</span><span class="sxs-lookup"><span data-stu-id="983c8-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-430">Durée des rafales dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-432">int</span><span class="sxs-lookup"><span data-stu-id="983c8-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-433">Occurrences d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-435">float</span><span class="sxs-lookup"><span data-stu-id="983c8-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-436">Densité d’intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-438">float</span><span class="sxs-lookup"><span data-stu-id="983c8-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-439">Durée des intervalles dans la fréquence d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="983c8-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-441">int</span><span class="sxs-lookup"><span data-stu-id="983c8-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-442">Hauteur moyenne de résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="983c8-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-444">int</span><span class="sxs-lookup"><span data-stu-id="983c8-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-445">Largeur moyenne de résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="983c8-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-446"><strong>Entrants</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-447">légèrement</span><span class="sxs-lookup"><span data-stu-id="983c8-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-448">Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.</span><span class="sxs-lookup"><span data-stu-id="983c8-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="983c8-449"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-450">légèrement</span><span class="sxs-lookup"><span data-stu-id="983c8-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-451">Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.</span><span class="sxs-lookup"><span data-stu-id="983c8-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="983c8-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="983c8-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="983c8-453">légèrement</span><span class="sxs-lookup"><span data-stu-id="983c8-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="983c8-454">1 signifie que la direction du flux va de l’appelant à l’appelé.</span><span class="sxs-lookup"><span data-stu-id="983c8-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="983c8-455">0 signifie que la direction du flux va de l’appelé à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="983c8-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

