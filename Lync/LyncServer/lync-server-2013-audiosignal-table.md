---
title: 'Lync Server 2013 : table AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="d7f0f-102">Table AudioSignal de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7f0f-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7f0f-103">_**Dernière modification de la rubrique :** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="d7f0f-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="d7f0f-104">Chaque enregistrement représente les métriques du signal audio pour un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="d7f0f-105">En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7f0f-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d7f0f-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d7f0f-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d7f0f-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d7f0f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-112">Principal</span><span class="sxs-lookup"><span data-stu-id="d7f0f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-113">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-115">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-115">int</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-116">Principal</span><span class="sxs-lookup"><span data-stu-id="d7f0f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-117">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7f0f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-120">Principal</span><span class="sxs-lookup"><span data-stu-id="d7f0f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-121">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-123">bit</span><span class="sxs-lookup"><span data-stu-id="d7f0f-123">bit</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-124">Principal</span><span class="sxs-lookup"><span data-stu-id="d7f0f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="d7f0f-125">0 : données du destinataire</span><span class="sxs-lookup"><span data-stu-id="d7f0f-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="d7f0f-126">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="d7f0f-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-128">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-129">Représente le niveau du signal audio après le contrôle du gain.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="d7f0f-130">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d7f0f-131">Pour une qualité acceptable, il devrait représenter au moins 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="d7f0f-132">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-134">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-135">Voir SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-137">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-138">Représente le niveau de bruit sonore du contrôle post-analogue.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="d7f0f-139">L’unité de cette métrique est dBmo.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d7f0f-140">Pour une qualité acceptable, elle doit être inférieure à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="d7f0f-141">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-143">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-144">Voir SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-146">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-147">Métrique d’amélioration de retour d’écho.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="d7f0f-148">L’unité de cette métrique est dB.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-148">The unit for this metric is dB.</span></span> <span data-ttu-id="d7f0f-149">Les valeurs inférieures représentent moins d’écho.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-149">Lower values represent less echo.</span></span> <span data-ttu-id="d7f0f-150">Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-152">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-153">Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="d7f0f-154">Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="d7f0f-155">Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-157">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-158">Moyenne des problèmes par cinq minutes pour la capture du micro.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="d7f0f-159">Pour une qualité optimale, il devrait être inférieur à une par cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="d7f0f-160">Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-162">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="d7f0f-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-163">Taux d’horloge de l’horloge du périphérique microphone par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-165">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="d7f0f-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-166">Taux d’horloge du périphérique de haut-parleurs par rapport à l’horloge du processeur.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-168">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="d7f0f-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-169">Taux d’horloge du périphérique de haut-parleurs par rapport à l’horloge du processeur.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="d7f0f-170">Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-172">décimale (9 ; 2)</span><span class="sxs-lookup"><span data-stu-id="d7f0f-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-173">Erreur d’horodatage moyenne du flux de rendu du présentateur, en millisecondes, au cours des dernières 20 secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-175">type</span><span class="sxs-lookup"><span data-stu-id="d7f0f-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-176">Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="d7f0f-177">Causes de l’entrée du commutateur vocal :</span><span class="sxs-lookup"><span data-stu-id="d7f0f-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="d7f0f-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="d7f0f-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="d7f0f-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d7f0f-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d7f0f-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="d7f0f-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="d7f0f-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d7f0f-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d7f0f-182">La cause peut être une combinaison de ces causes individuelles.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="d7f0f-183">ENTER_VS_FORCEORCONVERGENCE ne peut être activé qu’à l’aide de RegKey à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="d7f0f-184">Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7f0f-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-187">Causes d’un événement ECHO :</span><span class="sxs-lookup"><span data-stu-id="d7f0f-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="d7f0f-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="d7f0f-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="d7f0f-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d7f0f-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d7f0f-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="d7f0f-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="d7f0f-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d7f0f-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d7f0f-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="d7f0f-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="d7f0f-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="d7f0f-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="d7f0f-194">La cause peut être une combinaison de ces causes individuelles.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-196">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="d7f0f-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-p109">Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-202">décimale (5 ; 2)</span><span class="sxs-lookup"><span data-stu-id="d7f0f-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-203">Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="d7f0f-204">Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-206">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-207">Reçu le niveau du signal sur le serveur de médiation de la passerelle ; Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="d7f0f-208">L’unité de cette valeur est dBoV.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d7f0f-209">Pour une qualité optimale, la plage acceptable doit être comprise entre [-30 et-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-211">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-212">Reçu le niveau du signal sur le serveur de médiation de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="d7f0f-213">Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="d7f0f-214">L’unité de cette valeur est dBoV.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d7f0f-215">Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-217">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-218">Contrôle automatique de gain sur le côté serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-220">float</span><span class="sxs-lookup"><span data-stu-id="d7f0f-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d7f0f-221">Le carré moyen racine (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-223">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-224">Niveau du signal reçu sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d7f0f-225">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-227">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-228">Niveau du signal reçu sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d7f0f-229">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-231">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-232">Niveau sonore reçu sur canal 1.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d7f0f-233">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-235">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-236">Niveau sonore reçu sur canal 2.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d7f0f-237">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-239">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-240">Niveau du signal envoyé sur canal 1.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d7f0f-241">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-243">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-244">Niveau du signal envoyé sur canal 2.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d7f0f-245">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f0f-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-247">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-248">Niveau sonore tel qu’il est envoyé sur canal 1.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d7f0f-249">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f0f-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d7f0f-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d7f0f-251">int</span><span class="sxs-lookup"><span data-stu-id="d7f0f-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d7f0f-252">Niveau sonore tel qu’il est envoyé sur canal 2.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d7f0f-253">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d7f0f-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

