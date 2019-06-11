---
title: 'Lync Server 2013 : Table MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="11833-102">Table MediaLine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11833-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11833-103">_**Dernière modification de la rubrique:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="11833-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="11833-104">Chaque enregistrement représente une ligne multimédia.</span><span class="sxs-lookup"><span data-stu-id="11833-104">Each record represents one media line.</span></span> <span data-ttu-id="11833-105">(Une session audio est généralement composée d’une seule ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="11833-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="11833-106">Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.</span><span class="sxs-lookup"><span data-stu-id="11833-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11833-107"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="11833-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="11833-108"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="11833-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="11833-109"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="11833-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="11833-110"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="11833-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11833-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="11833-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="11833-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="11833-113">Principal</span><span class="sxs-lookup"><span data-stu-id="11833-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="11833-114">Fait référence à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="11833-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-116">int</span><span class="sxs-lookup"><span data-stu-id="11833-116">int</span></span></p></td>
<td><p><span data-ttu-id="11833-117">Principal</span><span class="sxs-lookup"><span data-stu-id="11833-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="11833-118">Fait référence à partir de la <a href="lync-server-2013-session-table.md">table de session dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="11833-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="11833-121">Principal</span><span class="sxs-lookup"><span data-stu-id="11833-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="11833-122">0 correspond au son principal, 1 correspond à la vidéo principale et 2 correspond à la vidéo panoramique, 3 au partage d’applications et de bureau.</span><span class="sxs-lookup"><span data-stu-id="11833-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="11833-123">Cette étiquette doit être unique au sein d’une même session.</span><span class="sxs-lookup"><span data-stu-id="11833-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="11833-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-126">Cette colonne est présente mais n’est pas utilisée dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="11833-127">Les informations relatives à la connectivité utilisée pour une ligne multimédia sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="11833-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="11833-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-129">int</span><span class="sxs-lookup"><span data-stu-id="11833-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-130">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs de bits.</span><span class="sxs-lookup"><span data-stu-id="11833-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="11833-131">Pour plus d’informations, reportez-vous à la <em>spécification qualité de l’expérimentation du protocole serveur</em>, disponible au téléchargement.</span><span class="sxs-lookup"><span data-stu-id="11833-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="11833-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-133">int</span><span class="sxs-lookup"><span data-stu-id="11833-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-134">Identique à CallerIceWarningFlags, mais au côté de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="11833-135">Pour plus d’informations, reportez-vous à la <em>spécification qualité de l’expérimentation du protocole serveur</em>, disponible au téléchargement.</span><span class="sxs-lookup"><span data-stu-id="11833-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-136"><strong>Sécurité</strong></span><span class="sxs-lookup"><span data-stu-id="11833-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-138">Profil de sécurité utilisé.</span><span class="sxs-lookup"><span data-stu-id="11833-138">The security profile in use.</span></span> <span data-ttu-id="11833-139">0 est aucun, 1 est SRTP, 2 est v1.</span><span class="sxs-lookup"><span data-stu-id="11833-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="11833-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-142">0 correspond au protocole UDP, 1 au port TCP.</span><span class="sxs-lookup"><span data-stu-id="11833-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="11833-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-144">int</span><span class="sxs-lookup"><span data-stu-id="11833-144">int</span></span></p></td>
<td><p><span data-ttu-id="11833-145">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-146">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-146">IP Address of the caller.</span></span> <span data-ttu-id="11833-147">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11833-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="11833-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-149">int</span><span class="sxs-lookup"><span data-stu-id="11833-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-150">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="11833-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-152">int</span><span class="sxs-lookup"><span data-stu-id="11833-152">int</span></span></p></td>
<td><p><span data-ttu-id="11833-153"> Externes</span><span class="sxs-lookup"><span data-stu-id="11833-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-154">Sous-réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-154">The subnet of the caller.</span></span> <span data-ttu-id="11833-155">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11833-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="11833-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-157">bit</span><span class="sxs-lookup"><span data-stu-id="11833-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-158">1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="11833-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="11833-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-160">int</span><span class="sxs-lookup"><span data-stu-id="11833-160">int</span></span></p></td>
<td><p><span data-ttu-id="11833-161">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-162">Adresse MAC de l’appelant, référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="11833-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-164">int</span><span class="sxs-lookup"><span data-stu-id="11833-164">int</span></span></p></td>
<td><p><span data-ttu-id="11833-165">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-166">Adresse IP du service Edge A/V du serveur Lync utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="11833-167">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11833-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="11833-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-169">int</span><span class="sxs-lookup"><span data-stu-id="11833-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-170">Port utilisé par l’appelant sur le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="11833-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="11833-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-172">int</span><span class="sxs-lookup"><span data-stu-id="11833-172">int</span></span></p></td>
<td><p><span data-ttu-id="11833-173">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-174">Appareil de capture utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-174">Capture device used by the caller.</span></span> <span data-ttu-id="11833-175">Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="11833-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-177">int</span><span class="sxs-lookup"><span data-stu-id="11833-177">int</span></span></p></td>
<td><p><span data-ttu-id="11833-178">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-179">Périphérique de rendu utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-179">Render device used by caller.</span></span> <span data-ttu-id="11833-180">Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="11833-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-182">int</span><span class="sxs-lookup"><span data-stu-id="11833-182">int</span></span></p></td>
<td><p><span data-ttu-id="11833-183">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-184">Pilote pour l’appareil de capture de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="11833-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-186">int</span><span class="sxs-lookup"><span data-stu-id="11833-186">int</span></span></p></td>
<td><p><span data-ttu-id="11833-187">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-188">Pilote pour l’appareil de rendu de l’appelant, référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="11833-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="11833-191">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-192">Indique la manière dont l’appelant s’est connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="11833-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="11833-193">Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="11833-194">Les valeurs par défaut sont 0 pour une connexion câblée' 1 pour une connexion WiFi; et 3 pour une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="11833-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="11833-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-196">int</span><span class="sxs-lookup"><span data-stu-id="11833-196">int</span></span></p></td>
<td><p><span data-ttu-id="11833-197">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-198">BSSID de l’appelant, si la technologie sans fil est utilisée.</span><span class="sxs-lookup"><span data-stu-id="11833-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="11833-199">Référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="11833-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-201">bit</span><span class="sxs-lookup"><span data-stu-id="11833-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-202">Le lien de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-202">The caller's link.</span></span> <span data-ttu-id="11833-203">1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="11833-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="11833-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-205">décimale (18, 0)</span><span class="sxs-lookup"><span data-stu-id="11833-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-206">La vitesse de connexion du réseau, en BPS, pour le point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="11833-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-208">int</span><span class="sxs-lookup"><span data-stu-id="11833-208">int</span></span></p></td>
<td><p><span data-ttu-id="11833-209">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-210">Adresse IP du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-210">IP Address of the call receiver.</span></span> <span data-ttu-id="11833-211">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11833-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="11833-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-213">bit</span><span class="sxs-lookup"><span data-stu-id="11833-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-214">Port utilisé par le destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="11833-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-216">int</span><span class="sxs-lookup"><span data-stu-id="11833-216">int</span></span></p></td>
<td><p><span data-ttu-id="11833-217">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-218">Sous-réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="11833-218">Subnet of callee.</span></span> <span data-ttu-id="11833-219">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11833-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="11833-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-221">bit</span><span class="sxs-lookup"><span data-stu-id="11833-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-222">1 signifie que le destinataire de l’appel se trouve à l’intérieur du réseau d’entreprise, 0 correspond au destinataire de l’appel hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="11833-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="11833-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-224">int</span><span class="sxs-lookup"><span data-stu-id="11833-224">int</span></span></p></td>
<td><p><span data-ttu-id="11833-225">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-226">Adresse MAC du destinataire.</span><span class="sxs-lookup"><span data-stu-id="11833-226">Callee Mac address.</span></span> <span data-ttu-id="11833-227">Fait référence à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="11833-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-229">int</span><span class="sxs-lookup"><span data-stu-id="11833-229">int</span></span></p></td>
<td><p><span data-ttu-id="11833-230">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-231">Adresse IP du service Edge A/V utilisée par le destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="11833-232">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="11833-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="11833-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-234">int</span><span class="sxs-lookup"><span data-stu-id="11833-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-235">Port utilisé sur le service Edge A/V par le destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="11833-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-237">int</span><span class="sxs-lookup"><span data-stu-id="11833-237">int</span></span></p></td>
<td><p><span data-ttu-id="11833-238">externes</span><span class="sxs-lookup"><span data-stu-id="11833-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-239">Appareil de capture utilisé par le destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="11833-240">Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="11833-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-242">int</span><span class="sxs-lookup"><span data-stu-id="11833-242">int</span></span></p></td>
<td><p><span data-ttu-id="11833-243">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-244">Périphérique de rendu utilisé par le destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-244">Render device used by the call receiver.</span></span> <span data-ttu-id="11833-245">Fait référence à partir de la <a href="lync-server-2013-device-table.md">table de périphériques dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="11833-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-247">int</span><span class="sxs-lookup"><span data-stu-id="11833-247">int</span></span></p></td>
<td><p><span data-ttu-id="11833-248">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-249">Pilote de l’appareil de capture du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="11833-250">Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="11833-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="11833-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11833-253">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-254">Pilote de l’appareil de rendu du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="11833-255">Référencé à partir de la <a href="lync-server-2013-devicedriver-table.md">table DeviceDriver dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="11833-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="11833-258">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-259">Indique la manière dont l’appelant s’est connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="11833-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="11833-260">Les valeurs sont obtenues à partir de la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="11833-261">Les valeurs par défaut sont 0 pour une connexion câblée' 1 pour une connexion WiFi; et 3 pour une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="11833-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="11833-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-263">int</span><span class="sxs-lookup"><span data-stu-id="11833-263">int</span></span></p></td>
<td><p><span data-ttu-id="11833-264">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-265">Le BSSID de l’appelant si la technologie sans fil est utilisée.</span><span class="sxs-lookup"><span data-stu-id="11833-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="11833-266">Référencée à partir de la <a href="lync-server-2013-macaddress-table.md">table MacAddress dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="11833-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-268">bit</span><span class="sxs-lookup"><span data-stu-id="11833-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-269">Le lien du destinataire de l’appel; 1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="11833-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="11833-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-271">décimale (18, 0)</span><span class="sxs-lookup"><span data-stu-id="11833-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-272">La vitesse de connexion du réseau, en BPS, pour le point de terminaison du destinataire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="11833-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-274">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="11833-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-275">La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="11833-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="11833-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-277">int</span><span class="sxs-lookup"><span data-stu-id="11833-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-278">Il s’agit de la bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="11833-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="11833-279">Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="11833-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="11833-280">Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="11833-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="11833-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-282">type</span><span class="sxs-lookup"><span data-stu-id="11833-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-283">Il s’agit de la source de la bande passante qui est imposée.</span><span class="sxs-lookup"><span data-stu-id="11833-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="11833-284">Il décrit l’emplacement à partir duquel la limite de bande passante provient («serveur de stratégie», «activer le serveur», «modalité», etc.).</span><span class="sxs-lookup"><span data-stu-id="11833-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="11833-285">Fait référence à partir de la <a href="lync-server-2013-appliedbandwidthsource-table.md">table AppliedBandwidthSource dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11833-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-286"><strong>Appelant</strong></span><span class="sxs-lookup"><span data-stu-id="11833-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-287">bit</span><span class="sxs-lookup"><span data-stu-id="11833-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-288">Indique si les mesures de l’appelant ont été reçues; 1 est oui, la valeur null est non.</span><span class="sxs-lookup"><span data-stu-id="11833-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-289"><strong>Appelé</strong></span><span class="sxs-lookup"><span data-stu-id="11833-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-290">bit</span><span class="sxs-lookup"><span data-stu-id="11833-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11833-291">Indique si les mesures du destinataire de l’appel ont été reçues. 1 est oui, la valeur null est non.</span><span class="sxs-lookup"><span data-stu-id="11833-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="11833-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-293">bit</span><span class="sxs-lookup"><span data-stu-id="11833-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-294">Indique si l’état correspond à une partie de la session ou à la session complète.</span><span class="sxs-lookup"><span data-stu-id="11833-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="11833-295">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="11833-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-297">bit</span><span class="sxs-lookup"><span data-stu-id="11833-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-298">Indique si un appel a été considéré comme un appel médiocre (valeur de 1) ou comme bon appel (0).</span><span class="sxs-lookup"><span data-stu-id="11833-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="11833-299">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="11833-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-301">Sa</span><span class="sxs-lookup"><span data-stu-id="11833-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-302">Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).</span><span class="sxs-lookup"><span data-stu-id="11833-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="11833-303">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="11833-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="11833-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11833-306">Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).</span><span class="sxs-lookup"><span data-stu-id="11833-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="11833-307">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="11833-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-309">int</span><span class="sxs-lookup"><span data-stu-id="11833-309">int</span></span></p></td>
<td><p><span data-ttu-id="11833-310">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-311">Adresse IP réflexive de l’utilisateur qui a placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="11833-312">Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="11833-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="11833-313">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="11833-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-315">int</span><span class="sxs-lookup"><span data-stu-id="11833-315">int</span></span></p></td>
<td><p><span data-ttu-id="11833-316">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-317">Description de l’appareil pour le pilote WiFi utilisé par l’utilisateur qui a placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="11833-318">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="11833-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-320">int</span><span class="sxs-lookup"><span data-stu-id="11833-320">int</span></span></p></td>
<td><p><span data-ttu-id="11833-321">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-322">Numéro de version du pilote WiFi utilisé par l’utilisateur qui a placé l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="11833-323">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="11833-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-325">int</span><span class="sxs-lookup"><span data-stu-id="11833-325">int</span></span></p></td>
<td><p><span data-ttu-id="11833-326">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-327">Adresse IP réflexive de l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="11833-328">Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="11833-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="11833-329">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11833-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="11833-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-331">int</span><span class="sxs-lookup"><span data-stu-id="11833-331">int</span></span></p></td>
<td><p><span data-ttu-id="11833-332">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-333">Description de l’appareil pour le pilote WiFi utilisé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="11833-334">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11833-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="11833-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="11833-336">int</span><span class="sxs-lookup"><span data-stu-id="11833-336">int</span></span></p></td>
<td><p><span data-ttu-id="11833-337">Externes</span><span class="sxs-lookup"><span data-stu-id="11833-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="11833-338">Numéro de version du pilote WiFi utilisé par l’utilisateur qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="11833-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="11833-339">Cette colonne a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11833-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

