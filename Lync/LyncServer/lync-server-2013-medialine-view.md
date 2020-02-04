---
title: 'Affichage Lync Server 2013 : MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="d4698-102">Affichage MediaLine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4698-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4698-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d4698-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d4698-104">Le mode MediaLine stocke les informations relatives à chaque ligne multimédia dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="d4698-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="d4698-105">Une seule session audio contient généralement une ligne multimédia audio.</span><span class="sxs-lookup"><span data-stu-id="d4698-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="d4698-106">Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d4698-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="d4698-107">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4698-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4698-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="d4698-108">Column</span></span></th>
<th><span data-ttu-id="d4698-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="d4698-109">Data Type</span></span></th>
<th><span data-ttu-id="d4698-110">taille</span><span class="sxs-lookup"><span data-stu-id="d4698-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4698-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="d4698-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="d4698-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d4698-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4698-113">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d4698-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="d4698-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="d4698-115">int</span><span class="sxs-lookup"><span data-stu-id="d4698-115">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-116">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d4698-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="d4698-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="d4698-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="d4698-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d4698-119">Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d4698-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d4698-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d4698-121">int</span><span class="sxs-lookup"><span data-stu-id="d4698-121">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-122">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="d4698-123">Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="d4698-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d4698-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d4698-125">int</span><span class="sxs-lookup"><span data-stu-id="d4698-125">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-126">Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="d4698-127">Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="d4698-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d4698-128">Security</span></span></p></td>
<td><p><span data-ttu-id="d4698-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="d4698-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d4698-130">Profil de sécurité en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="d4698-130">Security profile in use.</span></span> <span data-ttu-id="d4698-131">0 est aucun, 1 est SRTP, 2 est v1.</span><span class="sxs-lookup"><span data-stu-id="d4698-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-132">Transport</span><span class="sxs-lookup"><span data-stu-id="d4698-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="d4698-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="d4698-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d4698-134">Type de transport.</span><span class="sxs-lookup"><span data-stu-id="d4698-134">Transport type.</span></span> <span data-ttu-id="d4698-135">0 correspond au protocole UDP, 1 au port TCP.</span><span class="sxs-lookup"><span data-stu-id="d4698-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="d4698-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d4698-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-138">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-138">IP address of the caller.</span></span> <span data-ttu-id="d4698-139">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="d4698-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="d4698-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="d4698-141">int</span><span class="sxs-lookup"><span data-stu-id="d4698-141">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-142">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="d4698-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="d4698-144">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-144">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-145">Indique si l’appelant figure ou non dans le réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d4698-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="d4698-146">1 désigne l’appelant au sein du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d4698-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="d4698-147">0 signifie que l’appelant se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="d4698-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="d4698-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="d4698-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-150">Adresse MAC de l’interface réseau utilisée par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d4698-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d4698-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-153">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="d4698-154">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d4698-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d4698-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d4698-156">int</span><span class="sxs-lookup"><span data-stu-id="d4698-156">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-157">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="d4698-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d4698-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-160">Adresse IP de l’appelant communiquée par le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="d4698-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="d4698-161">Cette adresse peut être différente de l’CallerIPAddr si le client est situé derrière un NAT par exemple.</span><span class="sxs-lookup"><span data-stu-id="d4698-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d4698-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d4698-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-164">Nom de l’appareil de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="d4698-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d4698-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-167">Nom de l’appareil de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d4698-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d4698-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-170">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d4698-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d4698-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-173">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="d4698-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="d4698-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="d4698-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="d4698-176">Description du pilote WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="d4698-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="d4698-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-179">Version du pilote WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d4698-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="d4698-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-182">Détails de la connexion réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-182">Details of caller’s network connection.</span></span> <span data-ttu-id="d4698-183">Pour plus d’informations, voir la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d4698-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="d4698-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="d4698-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-186">Identifiant de l’ensemble de services standard utilisé par les appelants WiFi.</span><span class="sxs-lookup"><span data-stu-id="d4698-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="d4698-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="d4698-188">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-188">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-189">Indique si l’appelant s’est connecté via un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="d4698-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="d4698-190">1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="d4698-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="d4698-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d4698-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-193">Adresse IP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-193">IP address of the callee.</span></span> <span data-ttu-id="d4698-194">Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="d4698-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="d4698-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="d4698-196">int</span><span class="sxs-lookup"><span data-stu-id="d4698-196">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-197">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="d4698-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="d4698-199">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-199">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-200">Indique si l’appel est inclus dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d4698-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="d4698-201">1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.</span><span class="sxs-lookup"><span data-stu-id="d4698-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="d4698-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="d4698-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-204">Adresse MAC de l’interface réseau utilisée par le destinataire.</span><span class="sxs-lookup"><span data-stu-id="d4698-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d4698-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d4698-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-207">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="d4698-208">Pour plus d’informations, consultez la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d4698-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d4698-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d4698-210">int</span><span class="sxs-lookup"><span data-stu-id="d4698-210">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-211">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="d4698-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d4698-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-214">Adresse IP du destinataire indiquée par le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="d4698-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="d4698-215">Cette adresse peut être différente de l’CalleeIPAddr si le client est situé derrière un NAT par exemple.</span><span class="sxs-lookup"><span data-stu-id="d4698-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d4698-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d4698-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="d4698-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d4698-218">Nom de l’appareil de capture du destinataire.</span><span class="sxs-lookup"><span data-stu-id="d4698-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="d4698-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d4698-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-221">Nom de l’appareil de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d4698-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d4698-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-224">Nom du pilote de l’appareil de capture du appelé.</span><span class="sxs-lookup"><span data-stu-id="d4698-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d4698-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d4698-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-227">Nom du pilote du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="d4698-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="d4698-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-230">Description du pilote WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="d4698-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="d4698-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="d4698-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="d4698-233">Version du pilote WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d4698-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="d4698-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-236">Détails de la connexion réseau du destinataire.</span><span class="sxs-lookup"><span data-stu-id="d4698-236">Details of callee’s network connection.</span></span> <span data-ttu-id="d4698-237">Pour plus d’informations, voir la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d4698-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="d4698-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="d4698-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-240">Identificateur du jeu de service utilisé par la connexion WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d4698-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="d4698-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="d4698-242">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-242">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-243">Indique si l’appelant est connecté via un réseau privé virtuel.</span><span class="sxs-lookup"><span data-stu-id="d4698-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="d4698-244">1 est un réseau privé virtuel (VPN), 0 est non VPN.</span><span class="sxs-lookup"><span data-stu-id="d4698-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="d4698-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="d4698-246">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d4698-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d4698-247">La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="d4698-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="d4698-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="d4698-249">int</span><span class="sxs-lookup"><span data-stu-id="d4698-249">int</span></span></p></td>
<td><p><span data-ttu-id="d4698-250">Il s’agit de la bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.).</span><span class="sxs-lookup"><span data-stu-id="d4698-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="d4698-251">Cela ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="d4698-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="d4698-252">Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="d4698-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="d4698-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="d4698-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4698-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4698-255">Source de la bande passante imposée.</span><span class="sxs-lookup"><span data-stu-id="d4698-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="d4698-256">Il décrit l’emplacement vers lequel la limite de bande passante provient (par exemple, « serveur de stratégie », « activer le serveur » ou « modalité »).</span><span class="sxs-lookup"><span data-stu-id="d4698-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-257">Appelant</span><span class="sxs-lookup"><span data-stu-id="d4698-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="d4698-258">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-258">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-259">Indique si les mesures de l’appelant ont été reçues ; 1 est oui, 0 est non.</span><span class="sxs-lookup"><span data-stu-id="d4698-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-260">Appelé</span><span class="sxs-lookup"><span data-stu-id="d4698-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="d4698-261">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-261">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-262">Indique si les mesures du destinataire de l’appel ont été reçues. 1 est oui, 0 est non.</span><span class="sxs-lookup"><span data-stu-id="d4698-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="d4698-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="d4698-264">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-264">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-265">Indique s’il s’agit d’une portion de l’appel ou de l’appel complet.</span><span class="sxs-lookup"><span data-stu-id="d4698-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="d4698-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="d4698-267">bit</span><span class="sxs-lookup"><span data-stu-id="d4698-267">bit</span></span></p></td>
<td><p><span data-ttu-id="d4698-268">Indique si un appel a été considéré comme un appel médiocre (1) ou comme bon appel (0).</span><span class="sxs-lookup"><span data-stu-id="d4698-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4698-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="d4698-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="d4698-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="d4698-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d4698-271">Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).</span><span class="sxs-lookup"><span data-stu-id="d4698-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4698-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="d4698-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="d4698-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="d4698-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d4698-274">Indique si l’utilisateur s’est connecté au réseau à l’aide du protocole ICE (établissement d’une connexion Internet).</span><span class="sxs-lookup"><span data-stu-id="d4698-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

