---
title: 'Lync Server 2013 : table table audioclientevent'
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
ms.openlocfilehash: 53f43bdae2fd134e851c93be958aa671657489e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="6d063-102">Table table audioclientevent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d063-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d063-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="6d063-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="6d063-104">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio.</span><span class="sxs-lookup"><span data-stu-id="6d063-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="6d063-105">En règle générale, un appel dispose de deux enregistrements, un pour l’appelant et un pour l’appelé.</span><span class="sxs-lookup"><span data-stu-id="6d063-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d063-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6d063-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6d063-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6d063-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d063-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="6d063-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6d063-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="6d063-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6d063-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6d063-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-115">int</span><span class="sxs-lookup"><span data-stu-id="6d063-115">int</span></span></p></td>
<td><p><span data-ttu-id="6d063-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="6d063-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6d063-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6d063-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="6d063-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6d063-120">Primaire</span><span class="sxs-lookup"><span data-stu-id="6d063-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="6d063-121">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6d063-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-123">légèrement</span><span class="sxs-lookup"><span data-stu-id="6d063-123">bit</span></span></p></td>
<td><p><span data-ttu-id="6d063-124">Primaire</span><span class="sxs-lookup"><span data-stu-id="6d063-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="6d063-125">0 : données de l’appelé</span><span class="sxs-lookup"><span data-stu-id="6d063-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="6d063-126">1 : données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="6d063-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-128">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-129">Pourcentage de la session l’événement NetworkSendQuality a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="6d063-130">La qualité du réseau en termes de gigue ou de perte de paquets est importante et influe sur la qualité de l’audio envoyé.</span><span class="sxs-lookup"><span data-stu-id="6d063-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-132">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-133">Pourcentage de la session l’événement ReceiveSendQuality a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="6d063-134">La qualité du réseau en termes de gigue ou de perte de paquets est importante et a un impact sur la qualité de l’audio reçu.</span><span class="sxs-lookup"><span data-stu-id="6d063-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-136">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-137">Pourcentage de la session l’événement de retard a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-138">La latence du réseau est importante et a un impact sur l’expérience en empêchant la communication interactive</span><span class="sxs-lookup"><span data-stu-id="6d063-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-140">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-141">Pourcentage de la session l’événement LowBandwidth a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-142">La bande passante disponible est insuffisante pour une expérience vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="6d063-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-144">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-145">Pourcentage de la session l’événement d’UC insuffisant a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-146">Il n’y a pas suffisamment de cycles d’UC pour le traitement avec les modalités et les applications en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="6d063-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="6d063-147">Cela provoque des distorsions avec le canal audio.</span><span class="sxs-lookup"><span data-stu-id="6d063-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-149">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-150">Pourcentage de la session l’événement DeviceHalfDuplexAEC a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-151">Afin d’empêcher l’écho, le système est entré en semi-duplex.</span><span class="sxs-lookup"><span data-stu-id="6d063-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-153">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-154">Pourcentage de la session l’événement DeviceRenderNotFunctioning a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-155">Le périphérique de rendu actuellement utilisé pour la session ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="6d063-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="6d063-156">Cela peut entraîner des problèmes audio à sens unique.</span><span class="sxs-lookup"><span data-stu-id="6d063-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-158">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-159">Pourcentage de la session l’événement DeviceCaptureNotFunctioning a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-160">L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="6d063-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="6d063-161">Cela peut entraîner des problèmes audio à sens unique.</span><span class="sxs-lookup"><span data-stu-id="6d063-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-163">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-164">Pourcentage de la session l’événement DeviceGlitches a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-165">Il y a des problèmes sérieux dans le rendu de l’audio qui provoque des déformations.</span><span class="sxs-lookup"><span data-stu-id="6d063-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="6d063-166">Ces problèmes peuvent être causés par des problèmes de pilote, des appels de procédure différées (pilotes) et une utilisation intensive du processeur.</span><span class="sxs-lookup"><span data-stu-id="6d063-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-168">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-169">Pourcentage de la session l’événement DeviceLowSNR a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-170">La qualité de capture est très médiocre, soit très bruyante, soit l’utilisateur parle trop loin du microphone.</span><span class="sxs-lookup"><span data-stu-id="6d063-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="6d063-171">Cela entraînera des distorsions.</span><span class="sxs-lookup"><span data-stu-id="6d063-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-173">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-174">Pourcentage de la session l’événement DeviceLowSpeechLevel a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-175">Le niveau de voix de l’utilisateur est trop bas et le système ne peut plus en augmenter.</span><span class="sxs-lookup"><span data-stu-id="6d063-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="6d063-176">Cela peut entraîner des distorsions ou un affichage audio unidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="6d063-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-178">Décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-179">Pourcentage de la session l’événement DeviceClipping a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="6d063-180">Lorsque le microphone est terminé par des éléments vocaux de proximité, l’extrémité n’entend pas les distorsions dues à l’écrêtage.</span><span class="sxs-lookup"><span data-stu-id="6d063-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="6d063-181">Il est important d’éviter la détourage du microphone de bas.</span><span class="sxs-lookup"><span data-stu-id="6d063-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-183">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-184">Pourcentage de la session l’événement écho a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-185">Le périphérique ou le programme d’installation provoque un écho au-delà de la capacité du système à compenser.</span><span class="sxs-lookup"><span data-stu-id="6d063-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-187">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-188">Pourcentage de la session l’événement DeviceNearEndToEchoRatio a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-189">La voix de l’utilisateur est trop faible par rapport à l’écho capturé, ce qui a un impact sur l’expérience des utilisateurs, car il limite la facilité d’interruption d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d063-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="6d063-190">Réduire le volume des haut-parleurs, rapprochez le microphone du contacteur.</span><span class="sxs-lookup"><span data-stu-id="6d063-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-192">int</span><span class="sxs-lookup"><span data-stu-id="6d063-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d063-193">Nombre de fois au cours d’une session l’événement DeviceMultipleEndpoints a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-194">Plusieurs points de terminaison audio de la même session ont été détectés et le système a compensé en réduisant le volume de rendu.</span><span class="sxs-lookup"><span data-stu-id="6d063-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-196">int</span><span class="sxs-lookup"><span data-stu-id="6d063-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d063-197">Nombre de fois au cours d’une session l’événement DeviceHowlingEvent a été déclenché pour l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="6d063-198">Boucle audio de commentaire détectée (causée par plusieurs points de terminaison partageant le chemin audio).</span><span class="sxs-lookup"><span data-stu-id="6d063-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d063-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-200">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d063-201">Pourcentage de la session l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="6d063-202">Le périphérique de rendu a été défini sur zéro volume.</span><span class="sxs-lookup"><span data-stu-id="6d063-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="6d063-203">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d063-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d063-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6d063-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d063-205">décimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6d063-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d063-206">Pourcentage de la session l’événement DeviceRenderMute a été déclenché pour être dans l’état « incorrect ».</span><span class="sxs-lookup"><span data-stu-id="6d063-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="6d063-207">Le périphérique de rendu a été muet.</span><span class="sxs-lookup"><span data-stu-id="6d063-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="6d063-208">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d063-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

