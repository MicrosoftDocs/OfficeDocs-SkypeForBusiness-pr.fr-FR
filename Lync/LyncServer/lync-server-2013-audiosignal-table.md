---
title: 'Lync Server 2013 : table table audiosignal'
description: 'Lync Server 2013 : table table audiosignal.'
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
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568760"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="39b80-103">Table table audiosignal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b80-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b80-104">_**Dernière modification de la rubrique :** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="39b80-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="39b80-105">Chaque enregistrement représente les mesures de signal audio pour un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="39b80-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="39b80-106">En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="39b80-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39b80-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="39b80-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="39b80-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="39b80-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39b80-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="39b80-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="39b80-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="39b80-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="39b80-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="39b80-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-116">int</span><span class="sxs-lookup"><span data-stu-id="39b80-116">int</span></span></p></td>
<td><p><span data-ttu-id="39b80-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="39b80-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="39b80-118">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="39b80-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="39b80-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="39b80-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="39b80-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="39b80-122">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="39b80-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-124">légèrement</span><span class="sxs-lookup"><span data-stu-id="39b80-124">bit</span></span></p></td>
<td><p><span data-ttu-id="39b80-125">Primaire</span><span class="sxs-lookup"><span data-stu-id="39b80-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="39b80-126">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="39b80-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="39b80-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="39b80-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-129">int</span><span class="sxs-lookup"><span data-stu-id="39b80-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-130">Représente le niveau de signal audio post-analogue de contrôle de gain.</span><span class="sxs-lookup"><span data-stu-id="39b80-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="39b80-131">L’unité de mesure est dBmo.</span><span class="sxs-lookup"><span data-stu-id="39b80-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="39b80-132">Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins.</span><span class="sxs-lookup"><span data-stu-id="39b80-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="39b80-133">Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="39b80-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-135">int</span><span class="sxs-lookup"><span data-stu-id="39b80-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-136">Voir SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="39b80-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-138">int</span><span class="sxs-lookup"><span data-stu-id="39b80-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-139">Représente le niveau de bruit post-analogique de contrôle de gain.</span><span class="sxs-lookup"><span data-stu-id="39b80-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="39b80-140">L’unité de mesure est dBmo.</span><span class="sxs-lookup"><span data-stu-id="39b80-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="39b80-141">Pour une qualité acceptable, il doit être inférieur à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="39b80-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="39b80-142">Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="39b80-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-144">int</span><span class="sxs-lookup"><span data-stu-id="39b80-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-145">Voir SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="39b80-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-147">int</span><span class="sxs-lookup"><span data-stu-id="39b80-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-148">Mesure d’amélioration de la perte d’écho.</span><span class="sxs-lookup"><span data-stu-id="39b80-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="39b80-149">L’unité de mesure est dB.</span><span class="sxs-lookup"><span data-stu-id="39b80-149">The unit for this metric is dB.</span></span> <span data-ttu-id="39b80-150">Des valeurs inférieures représentent moins d’écho.</span><span class="sxs-lookup"><span data-stu-id="39b80-150">Lower values represent less echo.</span></span> <span data-ttu-id="39b80-151">Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="39b80-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-153">int</span><span class="sxs-lookup"><span data-stu-id="39b80-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-154">Nombre moyen de problèmes par cinq minutes pour le rendu du haut-parleur.</span><span class="sxs-lookup"><span data-stu-id="39b80-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="39b80-155">Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="39b80-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="39b80-156">Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="39b80-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-158">int</span><span class="sxs-lookup"><span data-stu-id="39b80-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-159">Nombre moyen de problèmes par cinq minutes pour la capture du microphone.</span><span class="sxs-lookup"><span data-stu-id="39b80-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="39b80-160">Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="39b80-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="39b80-161">Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="39b80-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-163">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="39b80-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-164">Vitesse de dérive de l’horloge du microphone, par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="39b80-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-166">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="39b80-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-167">Taux de dérive de l’horloge du périphérique haut-parleur par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="39b80-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-169">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="39b80-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-170">Taux de dérive de l’horloge du périphérique haut-parleur par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="39b80-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="39b80-171">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="39b80-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-173">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="39b80-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-174">Nombre moyen d’erreurs d’horodatage de flux de rendu, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="39b80-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-176">type</span><span class="sxs-lookup"><span data-stu-id="39b80-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-177">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="39b80-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="39b80-178">Causes de l’entrée de commutateur vocal :</span><span class="sxs-lookup"><span data-stu-id="39b80-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="39b80-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="39b80-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="39b80-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="39b80-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="39b80-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="39b80-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="39b80-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="39b80-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="39b80-183">La cause peut être une combinaison de ces causes.</span><span class="sxs-lookup"><span data-stu-id="39b80-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="39b80-184">ENTER_VS_FORCEORCONVERGENCE ne peut être activé que par la fonction RegKey à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="39b80-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="39b80-185">Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-187">entier très petit</span><span class="sxs-lookup"><span data-stu-id="39b80-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-188">Causes d’un événement ECHO :</span><span class="sxs-lookup"><span data-stu-id="39b80-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="39b80-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="39b80-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="39b80-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="39b80-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="39b80-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="39b80-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="39b80-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="39b80-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="39b80-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="39b80-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="39b80-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="39b80-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="39b80-195">La cause peut être une combinaison de ces causes.</span><span class="sxs-lookup"><span data-stu-id="39b80-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-197">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="39b80-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-198">Pourcentage de temps pendant lequel l’écho a été détecté dans le flux de capture du microphone.</span><span class="sxs-lookup"><span data-stu-id="39b80-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="39b80-199">En règle générale, les valeurs sont faibles pour les casques ou les combinés, et supérieures pour les téléphones de haut-parleur ou les haut-parleurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="39b80-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="39b80-200">Pour les appareils qui prennent en charge l’annulation de l’écho acoustique intégré, des valeurs élevées indiquent une fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="39b80-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="39b80-201">Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="39b80-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-203">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="39b80-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-204">Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé.</span><span class="sxs-lookup"><span data-stu-id="39b80-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="39b80-205">Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="39b80-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-207">int</span><span class="sxs-lookup"><span data-stu-id="39b80-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-208">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle ; Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="39b80-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="39b80-209">L’unité de mesure est dBoV.</span><span class="sxs-lookup"><span data-stu-id="39b80-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="39b80-210">Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="39b80-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-212">int</span><span class="sxs-lookup"><span data-stu-id="39b80-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-213">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="39b80-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="39b80-214">Cela ne s’applique qu’au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="39b80-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="39b80-215">L’unité de mesure est dBoV.</span><span class="sxs-lookup"><span data-stu-id="39b80-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="39b80-216">Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="39b80-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-218">int</span><span class="sxs-lookup"><span data-stu-id="39b80-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-219">Contrôle de gain automatique (AGC) sur le côté serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="39b80-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-221">float</span><span class="sxs-lookup"><span data-stu-id="39b80-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="39b80-222">La moyenne quadratique (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="39b80-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-224">int</span><span class="sxs-lookup"><span data-stu-id="39b80-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-225">Niveau de signal reçu sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="39b80-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="39b80-226">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-228">int</span><span class="sxs-lookup"><span data-stu-id="39b80-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-229">Niveau de signal reçu sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="39b80-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="39b80-230">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-232">int</span><span class="sxs-lookup"><span data-stu-id="39b80-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-233">Niveau de bruit reçu sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="39b80-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="39b80-234">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-236">int</span><span class="sxs-lookup"><span data-stu-id="39b80-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-237">Niveau sonore reçu sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="39b80-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="39b80-238">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-240">int</span><span class="sxs-lookup"><span data-stu-id="39b80-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-241">Niveau de signal tel qu’il est envoyé sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="39b80-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="39b80-242">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-244">int</span><span class="sxs-lookup"><span data-stu-id="39b80-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-245">Niveau de signal tel qu’il est envoyé sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="39b80-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="39b80-246">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b80-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-248">int</span><span class="sxs-lookup"><span data-stu-id="39b80-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-249">Niveau de bruit tel qu’il est envoyé sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="39b80-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="39b80-250">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b80-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="39b80-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="39b80-252">int</span><span class="sxs-lookup"><span data-stu-id="39b80-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b80-253">Niveau de bruit tel qu’il est envoyé sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="39b80-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="39b80-254">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39b80-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

