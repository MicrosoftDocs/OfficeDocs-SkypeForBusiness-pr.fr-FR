---
title: 'Lync Server 2013 : table table audiosignal'
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
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="237a2-102">Table table audiosignal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="237a2-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="237a2-103">_**Dernière modification de la rubrique :** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="237a2-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="237a2-104">Chaque enregistrement représente les mesures de signal audio pour un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="237a2-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="237a2-105">En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="237a2-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="237a2-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="237a2-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="237a2-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="237a2-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="237a2-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="237a2-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="237a2-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="237a2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="237a2-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="237a2-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-115">int</span><span class="sxs-lookup"><span data-stu-id="237a2-115">int</span></span></p></td>
<td><p><span data-ttu-id="237a2-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="237a2-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="237a2-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="237a2-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="237a2-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="237a2-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="237a2-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="237a2-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="237a2-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-123">légèrement</span><span class="sxs-lookup"><span data-stu-id="237a2-123">bit</span></span></p></td>
<td><p><span data-ttu-id="237a2-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="237a2-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="237a2-125">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="237a2-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="237a2-126">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="237a2-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-128">int</span><span class="sxs-lookup"><span data-stu-id="237a2-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-129">Représente le niveau de signal audio post-analogue de contrôle de gain.</span><span class="sxs-lookup"><span data-stu-id="237a2-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="237a2-130">L’unité de mesure est dBmo.</span><span class="sxs-lookup"><span data-stu-id="237a2-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="237a2-131">Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins.</span><span class="sxs-lookup"><span data-stu-id="237a2-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="237a2-132">Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="237a2-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-134">int</span><span class="sxs-lookup"><span data-stu-id="237a2-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-135">Voir SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="237a2-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-137">int</span><span class="sxs-lookup"><span data-stu-id="237a2-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-138">Représente le niveau de bruit post-analogique de contrôle de gain.</span><span class="sxs-lookup"><span data-stu-id="237a2-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="237a2-139">L’unité de mesure est dBmo.</span><span class="sxs-lookup"><span data-stu-id="237a2-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="237a2-140">Pour une qualité acceptable, il doit être inférieur à 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="237a2-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="237a2-141">Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="237a2-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-143">int</span><span class="sxs-lookup"><span data-stu-id="237a2-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-144">Voir SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="237a2-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-146">int</span><span class="sxs-lookup"><span data-stu-id="237a2-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-147">Mesure d’amélioration de la perte d’écho.</span><span class="sxs-lookup"><span data-stu-id="237a2-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="237a2-148">L’unité de mesure est dB.</span><span class="sxs-lookup"><span data-stu-id="237a2-148">The unit for this metric is dB.</span></span> <span data-ttu-id="237a2-149">Des valeurs inférieures représentent moins d’écho.</span><span class="sxs-lookup"><span data-stu-id="237a2-149">Lower values represent less echo.</span></span> <span data-ttu-id="237a2-150">Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="237a2-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-152">int</span><span class="sxs-lookup"><span data-stu-id="237a2-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-153">Nombre moyen de problèmes par cinq minutes pour le rendu du haut-parleur.</span><span class="sxs-lookup"><span data-stu-id="237a2-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="237a2-154">Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="237a2-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="237a2-155">Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="237a2-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-157">int</span><span class="sxs-lookup"><span data-stu-id="237a2-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-158">Nombre moyen de problèmes par cinq minutes pour la capture du microphone.</span><span class="sxs-lookup"><span data-stu-id="237a2-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="237a2-159">Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="237a2-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="237a2-160">Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="237a2-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-162">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="237a2-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-163">Vitesse de dérive de l’horloge du microphone, par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="237a2-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-165">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="237a2-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-166">Taux de dérive de l’horloge du périphérique haut-parleur par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="237a2-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-168">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="237a2-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-169">Taux de dérive de l’horloge du périphérique haut-parleur par rapport à l’horloge de l’UC.</span><span class="sxs-lookup"><span data-stu-id="237a2-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="237a2-170">Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="237a2-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-172">décimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="237a2-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-173">Nombre moyen d’erreurs d’horodatage de flux de rendu, en millisecondes, au cours des 20 dernières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="237a2-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-175">type</span><span class="sxs-lookup"><span data-stu-id="237a2-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-176">Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée.</span><span class="sxs-lookup"><span data-stu-id="237a2-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="237a2-177">Causes de l’entrée de commutateur vocal :</span><span class="sxs-lookup"><span data-stu-id="237a2-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="237a2-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="237a2-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="237a2-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="237a2-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="237a2-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="237a2-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="237a2-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="237a2-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="237a2-182">La cause peut être une combinaison de ces causes.</span><span class="sxs-lookup"><span data-stu-id="237a2-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="237a2-183">ENTER_VS_FORCEORCONVERGENCE ne peut être activé que par la fonction RegKey à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="237a2-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="237a2-184">Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-186">entier très petit</span><span class="sxs-lookup"><span data-stu-id="237a2-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-187">Causes d’un événement ECHO :</span><span class="sxs-lookup"><span data-stu-id="237a2-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="237a2-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="237a2-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="237a2-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="237a2-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="237a2-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="237a2-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="237a2-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="237a2-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="237a2-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="237a2-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="237a2-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="237a2-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="237a2-194">La cause peut être une combinaison de ces causes.</span><span class="sxs-lookup"><span data-stu-id="237a2-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-196">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="237a2-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-197">Pourcentage de temps pendant lequel l’écho a été détecté dans le flux de capture du microphone.</span><span class="sxs-lookup"><span data-stu-id="237a2-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="237a2-198">En règle générale, les valeurs sont faibles pour les casques ou les combinés, et supérieures pour les téléphones de haut-parleur ou les haut-parleurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="237a2-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="237a2-199">Pour les appareils qui prennent en charge l’annulation de l’écho acoustique intégré, des valeurs élevées indiquent une fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="237a2-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="237a2-200">Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="237a2-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-202">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="237a2-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-203">Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé.</span><span class="sxs-lookup"><span data-stu-id="237a2-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="237a2-204">Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="237a2-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-206">int</span><span class="sxs-lookup"><span data-stu-id="237a2-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-207">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle ; Cela s’applique uniquement au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="237a2-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="237a2-208">L’unité de mesure est dBoV.</span><span class="sxs-lookup"><span data-stu-id="237a2-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="237a2-209">Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="237a2-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-211">int</span><span class="sxs-lookup"><span data-stu-id="237a2-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-212">Niveau de signal reçu sur le serveur de médiation à partir de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="237a2-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="237a2-213">Cela ne s’applique qu’au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="237a2-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="237a2-214">L’unité de mesure est dBoV.</span><span class="sxs-lookup"><span data-stu-id="237a2-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="237a2-215">Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="237a2-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-217">int</span><span class="sxs-lookup"><span data-stu-id="237a2-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-218">Contrôle de gain automatique (AGC) sur le côté serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="237a2-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-220">flottant</span><span class="sxs-lookup"><span data-stu-id="237a2-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="237a2-221">La moyenne quadratique (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="237a2-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-223">int</span><span class="sxs-lookup"><span data-stu-id="237a2-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-224">Niveau de signal reçu sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="237a2-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="237a2-225">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-227">int</span><span class="sxs-lookup"><span data-stu-id="237a2-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-228">Niveau de signal reçu sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="237a2-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="237a2-229">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-231">int</span><span class="sxs-lookup"><span data-stu-id="237a2-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-232">Niveau de bruit reçu sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="237a2-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="237a2-233">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-235">int</span><span class="sxs-lookup"><span data-stu-id="237a2-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-236">Niveau sonore reçu sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="237a2-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="237a2-237">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-239">int</span><span class="sxs-lookup"><span data-stu-id="237a2-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-240">Niveau de signal tel qu’il est envoyé sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="237a2-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="237a2-241">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-243">int</span><span class="sxs-lookup"><span data-stu-id="237a2-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-244">Niveau de signal tel qu’il est envoyé sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="237a2-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="237a2-245">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237a2-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-247">int</span><span class="sxs-lookup"><span data-stu-id="237a2-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-248">Niveau de bruit tel qu’il est envoyé sur le canal 1.</span><span class="sxs-lookup"><span data-stu-id="237a2-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="237a2-249">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237a2-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="237a2-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="237a2-251">int</span><span class="sxs-lookup"><span data-stu-id="237a2-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="237a2-252">Niveau de bruit tel qu’il est envoyé sur le canal 2.</span><span class="sxs-lookup"><span data-stu-id="237a2-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="237a2-253">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="237a2-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

