---
title: 'Tableau Lync Server 2013: AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="74fc2-102">Table AppSharingStream dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74fc2-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74fc2-103">_**Dernière modification de la rubrique:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="74fc2-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="74fc2-104">La table AppSharingStream contient des métriques de qualité d’utilisation pour les flux réseau utilisés pour le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="74fc2-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="74fc2-105">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74fc2-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74fc2-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="74fc2-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="74fc2-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="74fc2-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="74fc2-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="74fc2-112">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="74fc2-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74fc2-113">Date et heure de démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="74fc2-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-115">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-115">int</span></span></p></td>
<td><p><span data-ttu-id="74fc2-116">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="74fc2-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74fc2-117">Identificateur séquentiel permettant de faire la distinction entre les sessions qui ont commencé à la même date et en même temps.</span><span class="sxs-lookup"><span data-stu-id="74fc2-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="74fc2-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="74fc2-120">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="74fc2-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74fc2-121">Représente le type de ligne vidéo utilisée lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="74fc2-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="74fc2-122">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="74fc2-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="74fc2-123">0-audio</span><span class="sxs-lookup"><span data-stu-id="74fc2-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="74fc2-124">1-vidéo</span><span class="sxs-lookup"><span data-stu-id="74fc2-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="74fc2-125">2-vidéo panoramique</span><span class="sxs-lookup"><span data-stu-id="74fc2-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="74fc2-126">3 – partage de bureau et d’application</span><span class="sxs-lookup"><span data-stu-id="74fc2-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-128">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-128">int</span></span></p></td>
<td><p><span data-ttu-id="74fc2-129">Principal</span><span class="sxs-lookup"><span data-stu-id="74fc2-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="74fc2-130">Identificateur unique du flux de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="74fc2-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-132">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-133">Gigue moyenne détectée entre les arrivées de paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="74fc2-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="74fc2-134">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="74fc2-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-136">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-137">Scintillement maximal détecté entre les arrivées de Paquets RTP.</span><span class="sxs-lookup"><span data-stu-id="74fc2-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="74fc2-138">(Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</span><span class="sxs-lookup"><span data-stu-id="74fc2-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-140">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-p105">Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="74fc2-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="74fc2-p106">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="74fc2-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-146">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-147">Quantité maximale de (en millisecondes) requise pour le paquet du protocole de transport en temps réel pour voyager vers un autre point de terminaison, puis retour.</span><span class="sxs-lookup"><span data-stu-id="74fc2-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="74fc2-148">Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</span><span class="sxs-lookup"><span data-stu-id="74fc2-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="74fc2-p108">Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</span><span class="sxs-lookup"><span data-stu-id="74fc2-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-152">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-p109">Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</span><span class="sxs-lookup"><span data-stu-id="74fc2-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-157">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-158">Taux maximal de perte de Paquets RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="74fc2-159">(La perte de paquets se produit lorsque les paquets RTP, un protocole utilisé pour transmettre des contenus audio et vidéo sur Internet, n’a pas pu atteindre leur destination.) Les taux de perte élevés sont généralement causés par une congestion; absence de bande passante; encombrement ou interférence sans fil; ou un serveur multimédia surchargé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="74fc2-160">La perte de paquets génère généralement une distorsion ou une perte de son.</span><span class="sxs-lookup"><span data-stu-id="74fc2-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-162">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-163">Nombre de paquets envoyés.</span><span class="sxs-lookup"><span data-stu-id="74fc2-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-164"><strong>Bande passante</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-165">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-166">Durée de bande passante estimée disponible à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="74fc2-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="74fc2-167">État en bits par seconde.</span><span class="sxs-lookup"><span data-stu-id="74fc2-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-169">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-170">Description de la charge utile de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="74fc2-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-172">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-173">Quantité totale de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-173">Total amount of one-way latency.</span></span> <span data-ttu-id="74fc2-174">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-175"><strong>Moyenne unidirectionnelle relative</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-176">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-177">Quantité moyenne de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-177">Average amount of one-way latency.</span></span> <span data-ttu-id="74fc2-178">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-180">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-181">Quantité maximale de latence à sens unique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="74fc2-182">Latence relative à sens unique, mesure du délai entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-184">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-185">Nombre total d’occurrences de rafales à sens unique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="74fc2-186">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="74fc2-187">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-189">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-190">Densité du Burst total unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="74fc2-190">Total one-way burst density.</span></span> <span data-ttu-id="74fc2-191">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="74fc2-192">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-194">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-195">Durée totale du Burst.</span><span class="sxs-lookup"><span data-stu-id="74fc2-195">Total one-way burst duration.</span></span> <span data-ttu-id="74fc2-196">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="74fc2-197">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-199">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-200">Nombre total d’occurrences de l’espacement unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="74fc2-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="74fc2-201">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="74fc2-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="74fc2-202">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-204">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-205">Densité de l’intervalle total à sens unique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-205">Total one-way gap density.</span></span> <span data-ttu-id="74fc2-206">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="74fc2-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="74fc2-207">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-209">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-210">Durée totale de l’intervalle.</span><span class="sxs-lookup"><span data-stu-id="74fc2-210">Total one-way gap duration.</span></span> <span data-ttu-id="74fc2-211">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendues au lieu d’un flux continu; les intervalles indiquent les retards entre ces rafales.</span><span class="sxs-lookup"><span data-stu-id="74fc2-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="74fc2-212">Cette métrique mesure le flux de données entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="74fc2-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-215">Rôle d’application (partage ou visionneuse) et type de contenu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-217">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-218">Durée totale du traitement des vignettes du protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-219">Un total supérieur équivaut à un délai plus long dans l’interface d’affichage.</span><span class="sxs-lookup"><span data-stu-id="74fc2-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-220"><strong>Vignettes RDP</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-221">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-222">Durée de traitement moyenne des vignettes du protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-223">Un total supérieur équivaut à un délai plus long dans l’interface d’affichage.</span><span class="sxs-lookup"><span data-stu-id="74fc2-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-225">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-226">Temps de traitement maximal pour les vignettes de protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-227">Un total supérieur équivaut à un délai plus long dans l’interface d’affichage.</span><span class="sxs-lookup"><span data-stu-id="74fc2-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-229">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-230">Des occurrences de Burst dans le temps de traitement des vignettes de protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-231">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-233">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-234">Densité Burst du temps de traitement des vignettes du protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-235">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-237">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-238">Durée Burst du temps de traitement des vignettes de protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-239">Une transmission «Burst» est une transmission dans laquelle les données sont transmises en rafales inattendus plutôt qu’à un flux continu.</span><span class="sxs-lookup"><span data-stu-id="74fc2-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-241">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-242">Occurrences de l’espace dans le temps de traitement des vignettes de protocole RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-244">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-245">La densité de l’intervalle du temps de traitement des vignettes RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-246">La densité de faible interépaisseur correspond à une meilleure expérience d’affichage.</span><span class="sxs-lookup"><span data-stu-id="74fc2-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-248">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-249">Durée de l’intervalle du temps de traitement des vignettes RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="74fc2-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="74fc2-250">Les durées de faible intervalle sont assimilées à une meilleure expérience d’affichage.</span><span class="sxs-lookup"><span data-stu-id="74fc2-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-252">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-253">Taux total de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-255">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-256">Taux moyen des vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-258">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-259">Taux maximal de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-261">dans t</span><span class="sxs-lookup"><span data-stu-id="74fc2-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-262">Occurrences de Burst dans le taux de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-264">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-265">Densité Burst dans le taux de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-267">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-268">Durée Burst dans le taux de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-270">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-271">Occurrences de l’espace dans le taux de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-273">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-274">Densité de l’intervalle dans le taux de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-276">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-277">Durée de l’intervalle en fonction du taux de vignettes capturées (en mosaïques par seconde).</span><span class="sxs-lookup"><span data-stu-id="74fc2-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-278"><strong>Vignettes altérées</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-279">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-280">Pourcentage total du contenu n’ayant pas atteint la visionneuse, mais qui a été ignoré et écrasé par le contenu actualisé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-282">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-283">Pourcentage moyen du contenu n’ayant pas atteint la visionneuse, mais qui a été ignoré et écrasé par le contenu actualisé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-285">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-286">Pourcentage maximal du contenu n’ayant pas atteint la visionneuse, mais a été ignoré et écrasé par le contenu actualisé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-288">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-289">Des occurrences de Burst pour le contenu n’ayant pas atteint la visionneuse, mais qui ont été ignorées et écrasées par le contenu fraîche.</span><span class="sxs-lookup"><span data-stu-id="74fc2-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-291">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-292">Densité Burst pour le contenu n’ayant pas atteint la visionneuse, mais qui a été ignoré et écrasé par le contenu actualisé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-294">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-295">Durée Burst pour le contenu n’ayant pas atteint la visionneuse, mais qui a été supprimée et écrasé par le contenu fraîche.</span><span class="sxs-lookup"><span data-stu-id="74fc2-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-297">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-298">Occurrences d’espace pour le contenu n’ayant pas atteint la visionneuse, mais qui ont été ignorées et écrasées par le contenu fraîche.</span><span class="sxs-lookup"><span data-stu-id="74fc2-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-300">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-301">Densité de l’intervalle pour le contenu n’ayant pas atteint la visionneuse, mais qui a été supprimée et écrasé par le contenu actualisé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-303">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-304">Durée de l’intervalle pour le contenu n’ayant pas atteint la visionneuse, mais qui a été annulée et écrasée par le contenu actualisé.</span><span class="sxs-lookup"><span data-stu-id="74fc2-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-306">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-307">Nombre total d’images abîmées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-309">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-310">Nombre moyen de trames abîmées dans la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-312">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-313">Nombre maximal d’images abîmées dans la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-315">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-316">Des occurrences de Burst dans les trames abîmées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-318">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-319">Densité Burst dans les trames abîmées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-321">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-322">Durée Burst dans les trames rachetées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-324">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-325">Occurrences de l’espace dans les trames abîmées dans la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-327">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-328">Densité de l’intervalle dans les trames rachetées à partir de la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-330">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-331">Durée de l’intervalle dans les trames abîmées par la source graphique.</span><span class="sxs-lookup"><span data-stu-id="74fc2-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-333">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-334">Taux total d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-336">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-337">Taux moyen d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-339">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-340">Taux maximal de vignettes entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-342">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-343">Des occurrences de Burst dans le taux de vignettes entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-345">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-346">Densité Burst dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-348">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-349">Durée Burst dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-351">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-352">Occurrences de l’espace dans le taux de vignette entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-354">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-355">Densité de l’intervalle dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-357">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-358">Durée de l’intervalle dans le taux de vignette entrante tel qu’il est reçu par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-360">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-361">Taux total d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-363">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-364">Taux moyen d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-366">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-367">Taux maximal d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-369">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-370">Des occurrences de Burst dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-372">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-373">Densité Burst dans la fréquence d’images entrantes reçue par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-375">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-376">Durée Burst dans la fréquence d’images entrantes reçue par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-378">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-379">Occurrences de l’espace dans la fréquence d’images entrantes reçues par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-381">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-382">Densité de l’intervalle dans la fréquence d’images entrantes reçue par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-384">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-385">Durée de l’intervalle dans la fréquence d’images entrantes reçue par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="74fc2-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-387">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-388">Taux total de vignettes sortantes de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-390">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-391">Taux moyen d’une vignette sortante pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-393">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-394">Taux de vignette sortante maximal pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-396">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-397">Des occurrences de Burst dans le taux de vignette sortante pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-399">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-400">Densité Burst dans le taux de vignette sortante pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-402">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-403">Durée Burst dans le taux de vignette sortante pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-405">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-406">Occurrences de l’espace dans le taux de vignette sortante de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-408">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-409">Densité de l’intervalle dans le taux de vignette sortante pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-411">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-412">Durée de l’intervalle dans le taux de vignette sortante pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-414">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-415">Taux total d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-417">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-418">taux moyen d’images sortantes pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-420">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-421">Taux maximal d’images sortant pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-423">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-424">Des occurrences de Burst dans le taux d’images sortant pour l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-426">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-427">Densité Burst dans le taux d’image sortant de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-429">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-430">Durée Burst dans le taux d’images sortant de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-432">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-433">Occurrences de l’espace dans le taux d’image sortant de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-435">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-436">Densité de l’intervalle dans le taux d’image sortant de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-438">float</span><span class="sxs-lookup"><span data-stu-id="74fc2-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-439">Durée de l’intervalle dans le taux d’image sortant de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="74fc2-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-441">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-442">Hauteur moyenne de la résolution vidéo, en pixels.</span><span class="sxs-lookup"><span data-stu-id="74fc2-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-444">int</span><span class="sxs-lookup"><span data-stu-id="74fc2-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-445">Largeur de résolution vidéo moyenne, en pixels.</span><span class="sxs-lookup"><span data-stu-id="74fc2-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-446"><strong>Entrant</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-447">bit</span><span class="sxs-lookup"><span data-stu-id="74fc2-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-448">Fréquence d’images moyenne (en images par seconde) pour les transmissions entrantes.</span><span class="sxs-lookup"><span data-stu-id="74fc2-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74fc2-449"><strong>Sortant</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-450">bit</span><span class="sxs-lookup"><span data-stu-id="74fc2-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-451">Fréquence d’images moyenne (en images par seconde) pour les transmissions sortantes.</span><span class="sxs-lookup"><span data-stu-id="74fc2-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74fc2-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="74fc2-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="74fc2-453">bit</span><span class="sxs-lookup"><span data-stu-id="74fc2-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74fc2-454">1 signifie que le sens du flux provient de l’appelant vers l’appel.</span><span class="sxs-lookup"><span data-stu-id="74fc2-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="74fc2-455">0: le sens du flux provient de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="74fc2-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

