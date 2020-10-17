---
title: 'Lync Server 2013 : table table audioclientevent'
description: 'Lync Server 2013 : table table audioclientevent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568780"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="1680e-103">Table table audioclientevent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1680e-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1680e-104">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="1680e-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="1680e-105">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio.</span><span class="sxs-lookup"><span data-stu-id="1680e-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="1680e-106">En règle générale, un appel dispose de deux enregistrements, un pour l’appelant et un pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="1680e-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1680e-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1680e-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1680e-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1680e-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1680e-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1680e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1680e-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="1680e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1680e-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1680e-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-116">int</span><span class="sxs-lookup"><span data-stu-id="1680e-116">int</span></span></p></td>
<td><p><span data-ttu-id="1680e-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="1680e-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="1680e-118">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1680e-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="1680e-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1680e-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="1680e-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="1680e-122">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1680e-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-124">légèrement</span><span class="sxs-lookup"><span data-stu-id="1680e-124">bit</span></span></p></td>
<td><p><span data-ttu-id="1680e-125">Primaire</span><span class="sxs-lookup"><span data-stu-id="1680e-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="1680e-126">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="1680e-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="1680e-127">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="1680e-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-129">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-130">Pourcentage de la session l’événement NetworkSendQuality a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="1680e-131">La qualité du réseau en termes de gigue ou de perte de paquets est importante et influe sur la qualité de l’audio envoyé.</span><span class="sxs-lookup"><span data-stu-id="1680e-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-133">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-134">Pourcentage de la session l’événement ReceiveSendQuality a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="1680e-135">La qualité du réseau en termes de gigue ou de perte de paquets est importante et a un impact sur la qualité de l’audio reçu.</span><span class="sxs-lookup"><span data-stu-id="1680e-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-137">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-138">Pourcentage de la session l’événement de retard a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-139">La latence du réseau est importante et a un impact sur l’expérience en empêchant la communication interactive</span><span class="sxs-lookup"><span data-stu-id="1680e-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-141">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-142">Pourcentage de la session l’événement LowBandwidth a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-143">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="1680e-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-145">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-146">Pourcentage de la session l’événement d’UC insuffisant a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-147">Il n’y a pas suffisamment de cycles d’UC pour le traitement avec les modalités et les applications en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="1680e-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="1680e-148">Cela provoque des distorsions avec le canal audio.</span><span class="sxs-lookup"><span data-stu-id="1680e-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-150">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-151">Pourcentage de la session l’événement DeviceHalfDuplexAEC a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-152">Afin d’empêcher l’écho, le système est entré en semi-duplex.</span><span class="sxs-lookup"><span data-stu-id="1680e-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-154">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-155">Pourcentage de la session l’événement DeviceRenderNotFunctioning a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-156">Le périphérique de rendu actuellement utilisé pour la session ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="1680e-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="1680e-157">Cela peut entraîner des problèmes audio à sens unique.</span><span class="sxs-lookup"><span data-stu-id="1680e-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-159">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-160">Pourcentage de la session l’événement DeviceCaptureNotFunctioning a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-161">L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="1680e-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="1680e-162">Cela peut entraîner des problèmes audio à sens unique.</span><span class="sxs-lookup"><span data-stu-id="1680e-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-164">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-165">Pourcentage de la session l’événement DeviceGlitches a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-166">Il y a des problèmes sérieux dans le rendu de l’audio qui provoque des déformations.</span><span class="sxs-lookup"><span data-stu-id="1680e-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="1680e-167">Ces problèmes peuvent être causés par des problèmes de pilote, des appels de procédure différées (pilotes) et une utilisation intensive du processeur.</span><span class="sxs-lookup"><span data-stu-id="1680e-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-169">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-170">Pourcentage de la session l’événement DeviceLowSNR a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-171">La qualité de capture est très médiocre, soit très bruyante, soit l’utilisateur parle trop loin du microphone.</span><span class="sxs-lookup"><span data-stu-id="1680e-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="1680e-172">Cela entraînera des distorsions.</span><span class="sxs-lookup"><span data-stu-id="1680e-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-174">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-175">Pourcentage de la session l’événement DeviceLowSpeechLevel a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-176">Le niveau de voix de l’utilisateur est trop bas et le système ne peut plus en augmenter.</span><span class="sxs-lookup"><span data-stu-id="1680e-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="1680e-177">Cela peut entraîner des distorsions ou un affichage audio unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="1680e-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-179">Décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-180">Pourcentage de la session l’événement DeviceClipping a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="1680e-181">Lorsque le microphone est terminé par des éléments vocaux de proximité, l’extrémité n’entend pas les distorsions dues à l’écrêtage.</span><span class="sxs-lookup"><span data-stu-id="1680e-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="1680e-182">Il est important d’éviter la détourage du microphone de bas.</span><span class="sxs-lookup"><span data-stu-id="1680e-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-184">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-185">Pourcentage de la session l’événement écho a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-186">Le périphérique ou le programme d’installation provoque un écho au-delà de la capacité du système à compenser.</span><span class="sxs-lookup"><span data-stu-id="1680e-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-188">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-189">Pourcentage de la session l’événement DeviceNearEndToEchoRatio a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-190">La voix de l’utilisateur est trop faible par rapport à l’écho capturé, ce qui a un impact sur l’expérience des utilisateurs, car il limite la facilité d’interruption d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1680e-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="1680e-191">Réduire le volume des haut-parleurs, rapprochez le microphone du contacteur.</span><span class="sxs-lookup"><span data-stu-id="1680e-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-193">int</span><span class="sxs-lookup"><span data-stu-id="1680e-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1680e-194">Nombre de fois au cours d’une session l’événement DeviceMultipleEndpoints a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-195">Plusieurs points de terminaison audio de la même session ont été détectés et le système a compensé en réduisant le volume de rendu.</span><span class="sxs-lookup"><span data-stu-id="1680e-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-197">int</span><span class="sxs-lookup"><span data-stu-id="1680e-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1680e-198">Nombre de fois au cours d’une session l’événement DeviceHowlingEvent a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="1680e-199">Boucle audio de commentaire détectée (causée par plusieurs points de terminaison partageant le chemin audio).</span><span class="sxs-lookup"><span data-stu-id="1680e-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1680e-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-201">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1680e-202">Pourcentage de la session l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="1680e-203">Le périphérique de rendu a été défini sur zéro volume.</span><span class="sxs-lookup"><span data-stu-id="1680e-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="1680e-204">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1680e-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1680e-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="1680e-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="1680e-206">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1680e-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1680e-207">Pourcentage de la session l’événement DeviceRenderMute a été déclenché pour être dans l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="1680e-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="1680e-208">Le périphérique de rendu a été muet.</span><span class="sxs-lookup"><span data-stu-id="1680e-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="1680e-209">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1680e-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

