---
title: 'Lync Server 2013 : table MediaLine'
description: 'Lync Server 2013 : table MediaLine.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572110"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="3cc72-103">Table MediaLine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cc72-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc72-104">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="3cc72-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="3cc72-105">Chaque enregistrement représente une ligne de support.</span><span class="sxs-lookup"><span data-stu-id="3cc72-105">Each record represents one media line.</span></span> <span data-ttu-id="3cc72-106">(Une session audio contient généralement un seul média audio.</span><span class="sxs-lookup"><span data-stu-id="3cc72-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="3cc72-107">Une session audio et vidéo (A/V) contient généralement une ligne de support audio et une ligne de support vidéo, bien que la session puisse contenir deux lignes de support vidéo si un appareil de conférence est utilisé ou si la vue de la Galerie est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3cc72-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cc72-108"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3cc72-109"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3cc72-110"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3cc72-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3cc72-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="3cc72-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="3cc72-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="3cc72-115">Référencé à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-117">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-117">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-118">Primaire</span><span class="sxs-lookup"><span data-stu-id="3cc72-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="3cc72-119">Référencé à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-121">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3cc72-122">Primaire</span><span class="sxs-lookup"><span data-stu-id="3cc72-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="3cc72-123">0 correspond à l’audio principal, 1 à la vidéo principale et 2 à la vidéo panoramique, 3 au partage d’application/de bureau.</span><span class="sxs-lookup"><span data-stu-id="3cc72-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="3cc72-124">Cette étiquette doit être unique au sein d’une même session.</span><span class="sxs-lookup"><span data-stu-id="3cc72-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-126">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-127">Cette colonne est présente, mais n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="3cc72-128">Les informations relatives à la connectivité utilisée pour une ligne multimédia sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="3cc72-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-130">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-131">Informations sur le processus d’établissement de connectivité interactive (ICE) décrit dans bits Flags.</span><span class="sxs-lookup"><span data-stu-id="3cc72-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="3cc72-132">Pour plus d’informations, reportez-vous à la <em>spécification Quality of expérience Monitoring Server Protocol</em>, disponible en téléchargement.</span><span class="sxs-lookup"><span data-stu-id="3cc72-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-134">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-135">Identique à CallerIceWarningFlags, mais sur le côté de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="3cc72-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="3cc72-136">Pour plus d’informations, reportez-vous à la <em>spécification Quality of expérience Monitoring Server Protocol</em>, disponible en téléchargement.</span><span class="sxs-lookup"><span data-stu-id="3cc72-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-137"><strong>Sécurité</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-138">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-139">Le profil de sécurité utilisé.</span><span class="sxs-lookup"><span data-stu-id="3cc72-139">The security profile in use.</span></span> <span data-ttu-id="3cc72-140">0 est AUCUN, 1 est SRTP, 2 est V1.</span><span class="sxs-lookup"><span data-stu-id="3cc72-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-142">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-143">0 est UDP, 1 est TCP.</span><span class="sxs-lookup"><span data-stu-id="3cc72-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-145">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-145">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-146">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-147">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-147">IP Address of the caller.</span></span> <span data-ttu-id="3cc72-148">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3cc72-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-150">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-151">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-153">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-153">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-154"> Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-155">Sous-réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-155">The subnet of the caller.</span></span> <span data-ttu-id="3cc72-156">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3cc72-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-158">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-159">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="3cc72-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-161">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-161">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-162">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-163">Adresse MAC de l’appelant, référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-165">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-165">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-166">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-167">Adresse IP du service Edge A/V de Lync Server utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="3cc72-168">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3cc72-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-170">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-171">Port utilisé sur le service Edge A/V par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-173">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-173">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-174">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-175">Appareil de capture utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-175">Capture device used by the caller.</span></span> <span data-ttu-id="3cc72-176">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-178">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-178">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-179">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-180">Périphérique de rendu utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-180">Render device used by caller.</span></span> <span data-ttu-id="3cc72-181">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-183">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-183">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-184">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-185">Pilote pour le périphérique de capture de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-187">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-187">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-188">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-189">Pilote pour le périphérique de rendu de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-191">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3cc72-192">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-193">Indique la façon dont l’appelant s’est connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="3cc72-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="3cc72-194">Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="3cc72-195">Les valeurs par défaut sont 0 pour une connexion filaire' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="3cc72-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-197">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-197">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-198">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-199">Le BSSID de l’appelant si la connexion sans fil est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3cc72-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="3cc72-200">Référencé depuis la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-202">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-203">Le lien de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-203">The caller's link.</span></span> <span data-ttu-id="3cc72-204">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="3cc72-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-206">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="3cc72-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-207">Vitesse de la liaison réseau, en bits/s, pour le point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3cc72-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-209">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-209">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-210">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-211">Adresse IP du récepteur d’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-211">IP Address of the call receiver.</span></span> <span data-ttu-id="3cc72-212">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3cc72-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-214">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-215">Port utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="3cc72-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-217">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-217">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-218">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-219">Sous-réseau de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="3cc72-219">Subnet of callee.</span></span> <span data-ttu-id="3cc72-220">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3cc72-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-222">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-223">1 signifie que le récepteur d’appels se trouve à l’intérieur du réseau d’entreprise, 0 signifie que le récepteur d’appels se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="3cc72-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-225">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-225">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-226">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-227">Adresse MAC de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="3cc72-227">Callee Mac address.</span></span> <span data-ttu-id="3cc72-228">Référencé à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-230">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-230">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-231">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-232">Adresse IP du service Edge A/V utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="3cc72-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="3cc72-233">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3cc72-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-235">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-236">Port utilisé sur le service Edge A/V par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="3cc72-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-238">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-238">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-239">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-240">Appareil de capture utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="3cc72-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="3cc72-241">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-243">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-243">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-244">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-245">Périphérique de rendu utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="3cc72-245">Render device used by the call receiver.</span></span> <span data-ttu-id="3cc72-246">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-248">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-248">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-249">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-250">Pilote pour l’appareil de capture du récepteur de l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="3cc72-251">Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3cc72-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3cc72-254">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-255">Pilote pour le périphérique de rendu du récepteur d’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="3cc72-256">Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-258">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3cc72-259">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-260">Indique le mode de connexion de l’appelé au réseau.</span><span class="sxs-lookup"><span data-stu-id="3cc72-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="3cc72-261">Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="3cc72-262">Les valeurs par défaut sont 0 pour une connexion filaire' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="3cc72-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-264">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-264">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-265">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-266">De l’appelé BSSID si la connexion sans fil est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3cc72-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="3cc72-267">Référencé depuis la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-269">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-270">Le lien du récepteur d’appels ; 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="3cc72-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-272">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="3cc72-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-273">Vitesse de la liaison réseau, en BPS, pour le point de terminaison du récepteur d’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-275">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="3cc72-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-276">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="3cc72-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-278">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-279">Il s’agit de la bande passante réelle appliquée au flux d’envoi donné en fonction de divers paramètres de stratégie (TURN, API, SDP, Server Policy, etc.).</span><span class="sxs-lookup"><span data-stu-id="3cc72-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="3cc72-280">À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="3cc72-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="3cc72-281">Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="3cc72-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-283">type</span><span class="sxs-lookup"><span data-stu-id="3cc72-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-284">Il s’agit de la source de la capacité de bande passante imposée.</span><span class="sxs-lookup"><span data-stu-id="3cc72-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="3cc72-285">Elle indique l’origine de la limite de bande passante ("Server Policy", "TURN Server", "modalité", etc.).</span><span class="sxs-lookup"><span data-stu-id="3cc72-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="3cc72-286">Référencé à partir de la <a href="lync-server-2013-appliedbandwidthsource-table.md">table table appliedbandwidthsource dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3cc72-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-288">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-289">Indique si les mesures de l’appelant ont été reçues ; 1 est oui, la valeur null est non.</span><span class="sxs-lookup"><span data-stu-id="3cc72-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-290"><strong>Appelé</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-291">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3cc72-292">Indique si les mesures du récepteur d’appels ont été reçues ; 1 est oui, la valeur null est non.</span><span class="sxs-lookup"><span data-stu-id="3cc72-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-294">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-295">Indique si le rapport est destiné à une partie de la session ou à la session complète.</span><span class="sxs-lookup"><span data-stu-id="3cc72-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="3cc72-296">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-298">légèrement</span><span class="sxs-lookup"><span data-stu-id="3cc72-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-299">Indique si un appel a été classé comme un appel médiocre (valeur 1) ou un appel de bonne qualité (0).</span><span class="sxs-lookup"><span data-stu-id="3cc72-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="3cc72-300">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-302">Entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-303">Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3cc72-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="3cc72-304">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-306">entier très petit</span><span class="sxs-lookup"><span data-stu-id="3cc72-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3cc72-307">Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3cc72-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="3cc72-308">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-310">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-310">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-311">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-312">Adresse IP réflexive de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="3cc72-313">Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="3cc72-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="3cc72-314">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-316">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-316">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-317">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-318">Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="3cc72-319">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-321">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-321">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-322">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-323">Numéro de version du pilote WiFi employé par l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="3cc72-324">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-326">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-326">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-327">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-328">Adresse IP réflexive de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="3cc72-329">Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="3cc72-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="3cc72-330">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc72-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-332">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-332">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-333">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-334">Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="3cc72-335">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc72-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3cc72-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3cc72-337">int</span><span class="sxs-lookup"><span data-stu-id="3cc72-337">int</span></span></p></td>
<td><p><span data-ttu-id="3cc72-338">Etranger</span><span class="sxs-lookup"><span data-stu-id="3cc72-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3cc72-339">Numéro de version du pilote WiFi employé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="3cc72-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="3cc72-340">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc72-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

