---
title: 'Lync Server 2013 : vue MediaLine'
description: 'Lync Server 2013 : vue MediaLine.'
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568680"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="f4e0c-103">Vue MediaLine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e0c-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e0c-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f4e0c-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f4e0c-105">La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="f4e0c-106">Une session audio contient généralement une ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="f4e0c-107">Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="f4e0c-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4e0c-109">Colonne</span><span class="sxs-lookup"><span data-stu-id="f4e0c-109">Column</span></span></th>
<th><span data-ttu-id="f4e0c-110">Type de données</span><span class="sxs-lookup"><span data-stu-id="f4e0c-110">Data Type</span></span></th>
<th><span data-ttu-id="f4e0c-111">détails</span><span class="sxs-lookup"><span data-stu-id="f4e0c-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="f4e0c-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f4e0c-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-114">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="f4e0c-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-116">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-116">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-117">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="f4e0c-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-119">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f4e0c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-120">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="f4e0c-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-122">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-122">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p102">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="f4e0c-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-126">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-126">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p103">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f4e0c-129">Security</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-130">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f4e0c-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p104">Le profil de sécurité en cours d’utilisation. 0 est AUCUN, 1 est SRTP, 2 est V1.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-133">Transport</span><span class="sxs-lookup"><span data-stu-id="f4e0c-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-134">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f4e0c-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p105">Type de transport. 0 est UDP, 1 est TCP.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="f4e0c-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p106">Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="f4e0c-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-142">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-142">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-143">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="f4e0c-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-145">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-145">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p107">Indique si l’appelant se trouve ou non à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant est à l’intérieur du réseau de l’entreprise. 0 indique que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="f4e0c-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-151">Adresse MAC ou interface réseau utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="f4e0c-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-154">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="f4e0c-155">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4e0c-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="f4e0c-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-157">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-157">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-158">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="f4e0c-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-161">Adresse IP de l’appelant indiquée par le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="f4e0c-162">Cette adresse peut être différente de CallerIPAddr si le client se trouve derrière un dispositif NAT par exemple.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="f4e0c-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-165">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="f4e0c-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-168">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="f4e0c-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-171">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="f4e0c-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-174">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="f4e0c-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="f4e0c-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-177">Description du pilote Wifi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="f4e0c-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-180">Version du pilote Wifi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="f4e0c-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-183">Détails de la connexion réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-183">Details of caller’s network connection.</span></span> <span data-ttu-id="f4e0c-184">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4e0c-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="f4e0c-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-187">Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="f4e0c-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-189">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-189">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p111">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel, 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="f4e0c-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-194">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-194">IP address of the callee.</span></span> <span data-ttu-id="f4e0c-195">il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="f4e0c-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-197">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-197">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-198">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="f4e0c-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-200">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-200">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p113">Indique si l’appelé se trouve ou non à l’intérieur du réseau de l’entreprise. 1 signifie que l’appelé est à l’intérieur du réseau de l’entreprise, 0 indique que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="f4e0c-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-205">Adresse MAC ou interface réseau utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="f4e0c-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-208">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="f4e0c-209">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4e0c-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="f4e0c-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-211">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-211">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-212">Port utilisé sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="f4e0c-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-215">Adresse IP de l’appelé indiquée par le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="f4e0c-216">Cette adresse peut être différente de CallerIPAddr  si le client se trouve derrière un dispositif NAT par exemple.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="f4e0c-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-219">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="f4e0c-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-222">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="f4e0c-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-225">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="f4e0c-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-228">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="f4e0c-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-231">Description du pilote Wifi de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="f4e0c-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="f4e0c-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-234">Version du pilote Wifi de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="f4e0c-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-237">Détails de la connexion réseau de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-237">Details of callee’s network connection.</span></span> <span data-ttu-id="f4e0c-238">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f4e0c-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="f4e0c-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-241">Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="f4e0c-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-243">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-243">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p117">Indique si l’appelé s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non-VPN.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="f4e0c-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-247">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-248">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="f4e0c-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="f4e0c-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-250">int</span><span class="sxs-lookup"><span data-stu-id="f4e0c-250">int</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p118">Bande passante effectivement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="f4e0c-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4e0c-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-p119">Source de la capacité de bande passante imposée. Elle décrit l’origine de la limite de la bande passante (par exemple, « Serveur de stratégie », « Serveur TURN » ou « Modalité »).</span><span class="sxs-lookup"><span data-stu-id="f4e0c-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-258">Appelant</span><span class="sxs-lookup"><span data-stu-id="f4e0c-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-259">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-259">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-260">Indique si des mesures ont été reçues de la part de l’appelant ; 1 pour oui, 0 pour non.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-261">Appelé</span><span class="sxs-lookup"><span data-stu-id="f4e0c-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-262">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-262">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-263">Indique si des mesures ont été reçues de la part du récepteur de l’appel ; 1 pour oui, 0 pour non.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="f4e0c-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-265">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-265">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-266">Indique si le rapport s’applique à une partie de l’appel ou à l’intégralité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f4e0c-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="f4e0c-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-268">légèrement</span><span class="sxs-lookup"><span data-stu-id="f4e0c-268">bit</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-269">Indique si un appel a été classé comme médiocre (1) ou bon (0).</span><span class="sxs-lookup"><span data-stu-id="f4e0c-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4e0c-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="f4e0c-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-271">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f4e0c-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-272">Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="f4e0c-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4e0c-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="f4e0c-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-274">entier très petit</span><span class="sxs-lookup"><span data-stu-id="f4e0c-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4e0c-275">Indique si l’utilisateur appelé s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="f4e0c-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

