---
title: 'Lync Server 2013 : table MediaLine'
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
ms.openlocfilehash: 84aa652a51934a8b513392869a0875f60689f759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="5d071-102">Table MediaLine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d071-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d071-103">_**Dernière modification de la rubrique :** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="5d071-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="5d071-104">Chaque enregistrement représente une ligne de support.</span><span class="sxs-lookup"><span data-stu-id="5d071-104">Each record represents one media line.</span></span> <span data-ttu-id="5d071-105">(Une session audio contient généralement un seul média audio.</span><span class="sxs-lookup"><span data-stu-id="5d071-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="5d071-106">Une session audio et vidéo (A/V) contient généralement une ligne de support audio et une ligne de support vidéo, bien que la session puisse contenir deux lignes de support vidéo si un appareil de conférence est utilisé ou si la vue de la Galerie est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5d071-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d071-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5d071-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5d071-109"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5d071-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d071-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5d071-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d071-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="5d071-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d071-114">Référencé à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-116">int</span><span class="sxs-lookup"><span data-stu-id="5d071-116">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="5d071-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d071-118">Référencé à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-120">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5d071-121">Primaire</span><span class="sxs-lookup"><span data-stu-id="5d071-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d071-122">0 correspond à l’audio principal, 1 à la vidéo principale et 2 à la vidéo panoramique, 3 au partage d’application/de bureau.</span><span class="sxs-lookup"><span data-stu-id="5d071-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="5d071-123">Cette étiquette doit être unique au sein d’une même session.</span><span class="sxs-lookup"><span data-stu-id="5d071-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-125">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-126">Cette colonne est présente, mais n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5d071-127">Les informations relatives à la connectivité utilisée pour une ligne multimédia sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="5d071-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-129">int</span><span class="sxs-lookup"><span data-stu-id="5d071-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-130">Informations sur le processus d’établissement de connectivité interactive (ICE) décrit dans bits Flags.</span><span class="sxs-lookup"><span data-stu-id="5d071-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="5d071-131">Pour plus d’informations, reportez-vous à la <em>spécification Quality of expérience Monitoring Server Protocol</em>, disponible en téléchargement.</span><span class="sxs-lookup"><span data-stu-id="5d071-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-133">int</span><span class="sxs-lookup"><span data-stu-id="5d071-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-134">Identique à CallerIceWarningFlags, mais sur le côté de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5d071-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="5d071-135">Pour plus d’informations, reportez-vous à la <em>spécification Quality of expérience Monitoring Server Protocol</em>, disponible en téléchargement.</span><span class="sxs-lookup"><span data-stu-id="5d071-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-136"><strong>Sécurité</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-137">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-138">Le profil de sécurité utilisé.</span><span class="sxs-lookup"><span data-stu-id="5d071-138">The security profile in use.</span></span> <span data-ttu-id="5d071-139">0 est AUCUN, 1 est SRTP, 2 est V1.</span><span class="sxs-lookup"><span data-stu-id="5d071-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-141">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-142">0 est UDP, 1 est TCP.</span><span class="sxs-lookup"><span data-stu-id="5d071-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-144">int</span><span class="sxs-lookup"><span data-stu-id="5d071-144">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-145">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-146">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-146">IP Address of the caller.</span></span> <span data-ttu-id="5d071-147">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d071-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-149">int</span><span class="sxs-lookup"><span data-stu-id="5d071-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-150">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-152">int</span><span class="sxs-lookup"><span data-stu-id="5d071-152">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-153"> Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-154">Sous-réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-154">The subnet of the caller.</span></span> <span data-ttu-id="5d071-155">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d071-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-157">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-158">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="5d071-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-160">int</span><span class="sxs-lookup"><span data-stu-id="5d071-160">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-161">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-162">Adresse MAC de l’appelant, référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-164">int</span><span class="sxs-lookup"><span data-stu-id="5d071-164">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-165">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-166">Adresse IP du service Edge A/V de Lync Server utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="5d071-167">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d071-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-169">int</span><span class="sxs-lookup"><span data-stu-id="5d071-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-170">Port utilisé sur le service Edge A/V par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-172">int</span><span class="sxs-lookup"><span data-stu-id="5d071-172">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-173">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-174">Appareil de capture utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-174">Capture device used by the caller.</span></span> <span data-ttu-id="5d071-175">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-177">int</span><span class="sxs-lookup"><span data-stu-id="5d071-177">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-178">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-179">Périphérique de rendu utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-179">Render device used by caller.</span></span> <span data-ttu-id="5d071-180">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-182">int</span><span class="sxs-lookup"><span data-stu-id="5d071-182">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-183">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-184">Pilote pour le périphérique de capture de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-186">int</span><span class="sxs-lookup"><span data-stu-id="5d071-186">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-187">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-188">Pilote pour le périphérique de rendu de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-190">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5d071-191">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-192">Indique la façon dont l’appelant s’est connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="5d071-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="5d071-193">Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="5d071-194">Les valeurs par défaut sont 0 pour une connexion filaire' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="5d071-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-196">int</span><span class="sxs-lookup"><span data-stu-id="5d071-196">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-197">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-198">Le BSSID de l’appelant si la connexion sans fil est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5d071-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="5d071-199">Référencé depuis la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-201">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-202">Le lien de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-202">The caller's link.</span></span> <span data-ttu-id="5d071-203">1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="5d071-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-205">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="5d071-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-206">Vitesse de la liaison réseau, en bits/s, pour le point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="5d071-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-208">int</span><span class="sxs-lookup"><span data-stu-id="5d071-208">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-209">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-210">Adresse IP du récepteur d’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-210">IP Address of the call receiver.</span></span> <span data-ttu-id="5d071-211">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d071-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-213">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-214">Port utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="5d071-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-216">int</span><span class="sxs-lookup"><span data-stu-id="5d071-216">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-217">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-218">Sous-réseau de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5d071-218">Subnet of callee.</span></span> <span data-ttu-id="5d071-219">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d071-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-221">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-222">1 signifie que le récepteur d’appels se trouve à l’intérieur du réseau d’entreprise, 0 signifie que le récepteur d’appels se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="5d071-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-224">int</span><span class="sxs-lookup"><span data-stu-id="5d071-224">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-225">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-226">Adresse MAC de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5d071-226">Callee Mac address.</span></span> <span data-ttu-id="5d071-227">Référencé à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-229">int</span><span class="sxs-lookup"><span data-stu-id="5d071-229">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-230">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-231">Adresse IP du service Edge A/V utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="5d071-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="5d071-232">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d071-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-234">int</span><span class="sxs-lookup"><span data-stu-id="5d071-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-235">Port utilisé sur le service Edge A/V par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="5d071-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-237">int</span><span class="sxs-lookup"><span data-stu-id="5d071-237">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-238">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-239">Appareil de capture utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="5d071-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="5d071-240">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-242">int</span><span class="sxs-lookup"><span data-stu-id="5d071-242">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-243">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-244">Périphérique de rendu utilisé par le récepteur d’appels.</span><span class="sxs-lookup"><span data-stu-id="5d071-244">Render device used by the call receiver.</span></span> <span data-ttu-id="5d071-245">Référencé à partir de la <a href="lync-server-2013-device-table.md">table Device dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-247">int</span><span class="sxs-lookup"><span data-stu-id="5d071-247">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-248">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-249">Pilote pour l’appareil de capture du récepteur de l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="5d071-250">Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d071-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5d071-253">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-254">Pilote pour le périphérique de rendu du récepteur d’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="5d071-255">Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-257">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5d071-258">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-259">Indique le mode de connexion de l’appelé au réseau.</span><span class="sxs-lookup"><span data-stu-id="5d071-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="5d071-260">Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="5d071-261">Les valeurs par défaut sont 0 pour une connexion filaire' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="5d071-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-263">int</span><span class="sxs-lookup"><span data-stu-id="5d071-263">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-264">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-265">De l’appelé BSSID si la connexion sans fil est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5d071-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="5d071-266">Référencé depuis la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-268">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-269">Le lien du récepteur d’appels ; 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="5d071-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-271">décimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="5d071-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-272">Vitesse de la liaison réseau, en BPS, pour le point de terminaison du récepteur d’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-274">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5d071-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-275">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="5d071-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-277">int</span><span class="sxs-lookup"><span data-stu-id="5d071-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-278">Il s’agit de la bande passante réelle appliquée au flux d’envoi donné en fonction de divers paramètres de stratégie (TURN, API, SDP, Server Policy, etc.).</span><span class="sxs-lookup"><span data-stu-id="5d071-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="5d071-279">À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="5d071-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="5d071-280">Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="5d071-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-282">type</span><span class="sxs-lookup"><span data-stu-id="5d071-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-283">Il s’agit de la source de la capacité de bande passante imposée.</span><span class="sxs-lookup"><span data-stu-id="5d071-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="5d071-284">Elle indique l’origine de la limite de bande passante ("Server Policy", "TURN Server", "modalité", etc.).</span><span class="sxs-lookup"><span data-stu-id="5d071-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="5d071-285">Référencé à partir de la <a href="lync-server-2013-appliedbandwidthsource-table.md">table table appliedbandwidthsource dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5d071-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-287">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-288">Indique si les mesures de l’appelant ont été reçues ; 1 est oui, la valeur null est non.</span><span class="sxs-lookup"><span data-stu-id="5d071-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-289"><strong>Appelé</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-290">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5d071-291">Indique si les mesures du récepteur d’appels ont été reçues ; 1 est oui, la valeur null est non.</span><span class="sxs-lookup"><span data-stu-id="5d071-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-293">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-294">Indique si le rapport est destiné à une partie de la session ou à la session complète.</span><span class="sxs-lookup"><span data-stu-id="5d071-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="5d071-295">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-297">légèrement</span><span class="sxs-lookup"><span data-stu-id="5d071-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-298">Indique si un appel a été classé comme un appel médiocre (valeur 1) ou un appel de bonne qualité (0).</span><span class="sxs-lookup"><span data-stu-id="5d071-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="5d071-299">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-301">Entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-302">Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="5d071-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="5d071-303">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-305">entier très petit</span><span class="sxs-lookup"><span data-stu-id="5d071-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d071-306">Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="5d071-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="5d071-307">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-309">int</span><span class="sxs-lookup"><span data-stu-id="5d071-309">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-310">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-311">Adresse IP réflexive de l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="5d071-312">Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="5d071-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="5d071-313">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-315">int</span><span class="sxs-lookup"><span data-stu-id="5d071-315">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-316">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-317">Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="5d071-318">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-320">int</span><span class="sxs-lookup"><span data-stu-id="5d071-320">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-321">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-322">Numéro de version du pilote WiFi employé par l’utilisateur qui a passé l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="5d071-323">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-325">int</span><span class="sxs-lookup"><span data-stu-id="5d071-325">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-326">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-327">Adresse IP réflexive de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="5d071-328">Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="5d071-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="5d071-329">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d071-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-331">int</span><span class="sxs-lookup"><span data-stu-id="5d071-331">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-332">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-333">Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="5d071-334">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d071-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5d071-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5d071-336">int</span><span class="sxs-lookup"><span data-stu-id="5d071-336">int</span></span></p></td>
<td><p><span data-ttu-id="5d071-337">Etranger</span><span class="sxs-lookup"><span data-stu-id="5d071-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d071-338">Numéro de version du pilote WiFi employé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="5d071-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="5d071-339">Cette chronique a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d071-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

