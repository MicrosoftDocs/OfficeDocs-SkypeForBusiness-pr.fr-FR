---
title: 'Lync Server 2013 : Table AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="526b5-102">Table AudioClientEvent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="526b5-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="526b5-103">_**Dernière modification de la rubrique:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="526b5-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="526b5-104">Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio.</span><span class="sxs-lookup"><span data-stu-id="526b5-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="526b5-105">En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="526b5-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="526b5-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="526b5-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="526b5-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="526b5-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="526b5-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="526b5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="526b5-112">Principal</span><span class="sxs-lookup"><span data-stu-id="526b5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="526b5-113">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="526b5-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-115">int</span><span class="sxs-lookup"><span data-stu-id="526b5-115">int</span></span></p></td>
<td><p><span data-ttu-id="526b5-116">Principal</span><span class="sxs-lookup"><span data-stu-id="526b5-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="526b5-117">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="526b5-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="526b5-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="526b5-120">Principal</span><span class="sxs-lookup"><span data-stu-id="526b5-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="526b5-121">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="526b5-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-123">bit</span><span class="sxs-lookup"><span data-stu-id="526b5-123">bit</span></span></p></td>
<td><p><span data-ttu-id="526b5-124">Principal</span><span class="sxs-lookup"><span data-stu-id="526b5-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="526b5-125">0: données du destinataire</span><span class="sxs-lookup"><span data-stu-id="526b5-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="526b5-126">1: données de l’appelant</span><span class="sxs-lookup"><span data-stu-id="526b5-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-128">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-129">Pourcentage de session de déclenchement de l’événement NetworkSendQuality pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="526b5-130">La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son envoyé.</span><span class="sxs-lookup"><span data-stu-id="526b5-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-132">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-133">Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="526b5-134">La qualité du réseau en termes de gigue ou de perte de paquets est sérieuse et a un impact sur la qualité du son reçu.</span><span class="sxs-lookup"><span data-stu-id="526b5-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-136">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-137">Pourcentage de session le déclenchement de l’événement de temporisation a été déclenché pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-138">La latence du réseau est sérieuse et a un impact sur l’interface en empêchant les communications interactives</span><span class="sxs-lookup"><span data-stu-id="526b5-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-140">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-141">Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-142">La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.</span><span class="sxs-lookup"><span data-stu-id="526b5-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-144">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-145">Pourcentage de session de l’événement UC insuffisant déclenché pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-146">Il n’y a pas assez de cycles d’UC pour le traitement avec les modalités et applications en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="526b5-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="526b5-147">Cela entraîne une distorsion du canal audio.</span><span class="sxs-lookup"><span data-stu-id="526b5-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-149">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-150">Pourcentage de session de déclenchement de l’événement DeviceHalfDuplexAEC pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-151">Afin d’éviter l’écho, le système a entré Half duplex.</span><span class="sxs-lookup"><span data-stu-id="526b5-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-153">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-154">Pourcentage de session de déclenchement de l’événement DeviceRenderNotFunctioning pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-155">L’appareil de rendu actuellement utilisé pour la session ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="526b5-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="526b5-156">Cela peut entraîner des problèmes audio à sens unique.</span><span class="sxs-lookup"><span data-stu-id="526b5-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-158">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-159">Pourcentage de session de déclenchement de l’événement DeviceCaptureNotFunctioning pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-160">L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="526b5-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="526b5-161">Cela peut entraîner des problèmes audio à sens unique.</span><span class="sxs-lookup"><span data-stu-id="526b5-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-163">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-164">Pourcentage de session de déclenchement de l’événement DeviceGlitches pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-165">Il y a des problèmes importants dans le rendu du son qui engendre des distorsions.</span><span class="sxs-lookup"><span data-stu-id="526b5-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="526b5-166">Ces problèmes peuvent être causés par des problèmes de pilotes, des appels de procédures différées (DPC) Storm (pilotes) et une utilisation élevée de l’UC.</span><span class="sxs-lookup"><span data-stu-id="526b5-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-168">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-169">Pourcentage de session de déclenchement de l’événement DeviceLowSNR pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-170">La qualité de la capture est très médiocre, qu’elle soit très bruyante ou que l’utilisateur parle trop loin du microphone.</span><span class="sxs-lookup"><span data-stu-id="526b5-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="526b5-171">Cela entraînera une distorsion.</span><span class="sxs-lookup"><span data-stu-id="526b5-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-173">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-174">Pourcentage de session de déclenchement de l’événement DeviceLowSpeechLevel pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-175">Le niveau de voix de l’utilisateur est trop faible et le système ne peut plus l’augmenter.</span><span class="sxs-lookup"><span data-stu-id="526b5-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="526b5-176">Cela peut entraîner des distorsions ou une perception perçue comme un son à sens unique.</span><span class="sxs-lookup"><span data-stu-id="526b5-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-178">Décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-179">Pourcentage de session de déclenchement de l’événement DeviceClipping pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="526b5-180">Lorsque le son du microphone est proche de l’extrémité de la parole, la distorsion est audible en raison de l’écrêtage.</span><span class="sxs-lookup"><span data-stu-id="526b5-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="526b5-181">Il est important d’éviter une capture du microphone proche de la fin.</span><span class="sxs-lookup"><span data-stu-id="526b5-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-183">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-184">Pourcentage de session de déclenchement de l’événement DeviceEchoEvent pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-185">L’appareil ou la configuration entraîne un écho au-delà de la capacité du système à compenser.</span><span class="sxs-lookup"><span data-stu-id="526b5-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-187">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-188">Pourcentage de session de déclenchement de l’événement DeviceNearEndToEchoRatio pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-189">La parole de l’utilisateur est trop faible par rapport à l’écho capturé qui a un impact sur l’interface utilisateur, car il limite le niveau d’interruption d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="526b5-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="526b5-190">Réduire le volume des haut-parleurs, rapprochez le micro du contact.</span><span class="sxs-lookup"><span data-stu-id="526b5-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-192">int</span><span class="sxs-lookup"><span data-stu-id="526b5-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="526b5-193">Nombre de fois que l’événement DeviceMultipleEndpoints a été déclenché pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-194">Plusieurs points de terminaison audio au sein de la même session détectés et le système a compensé en réduisant le volume de rendu.</span><span class="sxs-lookup"><span data-stu-id="526b5-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-196">int</span><span class="sxs-lookup"><span data-stu-id="526b5-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="526b5-197">Nombre de fois que l’événement DeviceHowlingEvent a été déclenché pour l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="526b5-198">Boucle de commentaires audio détectée (provoquée par plusieurs points de terminaison partageant le chemin audio).</span><span class="sxs-lookup"><span data-stu-id="526b5-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="526b5-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-200">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="526b5-201">Pourcentage de session l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="526b5-202">L’appareil de rendu a été défini sur le volume zéro.</span><span class="sxs-lookup"><span data-stu-id="526b5-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="526b5-203">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="526b5-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="526b5-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="526b5-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="526b5-205">décimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="526b5-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="526b5-206">Pourcentage de session l’événement DeviceRenderMute a été déclenché pour être dans l’état «incorrect».</span><span class="sxs-lookup"><span data-stu-id="526b5-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="526b5-207">L’appareil de rendu a été coupé.</span><span class="sxs-lookup"><span data-stu-id="526b5-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="526b5-208">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="526b5-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

