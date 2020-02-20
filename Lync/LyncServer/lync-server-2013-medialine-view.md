---
title: 'Lync Server 2013 : vue MediaLine'
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
ms.openlocfilehash: bc36c1a853e51ba1b47de785006f3bf6fa33d462
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="83ef7-102">Vue MediaLine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83ef7-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83ef7-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="83ef7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="83ef7-104">La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="83ef7-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="83ef7-105">Une session audio contient généralement une ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="83ef7-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="83ef7-106">Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="83ef7-107">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83ef7-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83ef7-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="83ef7-108">Column</span></span></th>
<th><span data-ttu-id="83ef7-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="83ef7-109">Data Type</span></span></th>
<th><span data-ttu-id="83ef7-110">détails</span><span class="sxs-lookup"><span data-stu-id="83ef7-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="83ef7-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="83ef7-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="83ef7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="83ef7-113">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="83ef7-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="83ef7-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="83ef7-115">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-115">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-116">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="83ef7-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="83ef7-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="83ef7-118">entier très petit</span><span class="sxs-lookup"><span data-stu-id="83ef7-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83ef7-119">Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="83ef7-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="83ef7-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="83ef7-121">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-121">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p102">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="83ef7-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="83ef7-125">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-125">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p103">Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="83ef7-128">Security</span></span></p></td>
<td><p><span data-ttu-id="83ef7-129">entier très petit</span><span class="sxs-lookup"><span data-stu-id="83ef7-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p104">Le profil de sécurité en cours d’utilisation. 0 est AUCUN, 1 est SRTP, 2 est V1.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-132">Transport</span><span class="sxs-lookup"><span data-stu-id="83ef7-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="83ef7-133">entier très petit</span><span class="sxs-lookup"><span data-stu-id="83ef7-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p105">Type de transport. 0 est UDP, 1 est TCP.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="83ef7-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83ef7-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p106">Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="83ef7-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="83ef7-141">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-141">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-142">Port utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="83ef7-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="83ef7-144">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-144">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p107">Indique si l’appelant se trouve ou non à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant est à l’intérieur du réseau de l’entreprise. 0 indique que l’appelant se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="83ef7-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="83ef7-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-150">Adresse MAC ou interface réseau utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="83ef7-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83ef7-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-153">Adresse IP du service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="83ef7-154">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83ef7-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="83ef7-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="83ef7-156">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-156">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-157">Port utilisé sur le service Edge A/V utilisé par l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="83ef7-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83ef7-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-160">Adresse IP de l’appelant indiquée par le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="83ef7-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="83ef7-161">Cette adresse peut être différente de CallerIPAddr si le client se trouve derrière un dispositif NAT par exemple.</span><span class="sxs-lookup"><span data-stu-id="83ef7-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="83ef7-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="83ef7-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-164">Nom du périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="83ef7-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="83ef7-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-167">Nom du périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="83ef7-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83ef7-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-170">Nom du pilote de périphérique de capture de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="83ef7-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83ef7-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-173">Nom du pilote de périphérique de rendu de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="83ef7-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="83ef7-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="83ef7-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="83ef7-176">Description du pilote Wifi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="83ef7-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="83ef7-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-179">Version du pilote Wifi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="83ef7-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="83ef7-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-182">Détails de la connexion réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-182">Details of caller’s network connection.</span></span> <span data-ttu-id="83ef7-183">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83ef7-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="83ef7-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="83ef7-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-186">Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="83ef7-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="83ef7-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="83ef7-188">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-188">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p111">Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel, 0 pour un réseau non VPN.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="83ef7-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83ef7-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-193">Adresse IP de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-193">IP address of the callee.</span></span> <span data-ttu-id="83ef7-194">il peut s’agir d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="83ef7-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="83ef7-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="83ef7-196">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-196">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-197">Port utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="83ef7-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="83ef7-199">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-199">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p113">Indique si l’appelé se trouve ou non à l’intérieur du réseau de l’entreprise. 1 signifie que l’appelé est à l’intérieur du réseau de l’entreprise, 0 indique que l’appelé se trouve à l’extérieur du réseau.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="83ef7-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="83ef7-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-204">Adresse MAC ou interface réseau utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="83ef7-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83ef7-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-207">Adresse IP du service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="83ef7-208">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-ipaddress-table.md">table IPAddress dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83ef7-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="83ef7-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="83ef7-210">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-210">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-211">Port utilisé sur le service Edge A/V utilisé par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="83ef7-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83ef7-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-214">Adresse IP de l’appelé indiquée par le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="83ef7-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="83ef7-215">Cette adresse peut être différente de CallerIPAddr  si le client se trouve derrière un dispositif NAT par exemple.</span><span class="sxs-lookup"><span data-stu-id="83ef7-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="83ef7-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="83ef7-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="83ef7-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-218">Nom du périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="83ef7-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="83ef7-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-221">Nom du périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="83ef7-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83ef7-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-224">Nom du pilote de périphérique de capture de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="83ef7-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83ef7-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-227">Nom du pilote de périphérique de rendu de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="83ef7-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="83ef7-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-230">Description du pilote Wifi de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="83ef7-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="83ef7-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="83ef7-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="83ef7-233">Version du pilote Wifi de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="83ef7-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="83ef7-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-236">Détails de la connexion réseau de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-236">Details of callee’s network connection.</span></span> <span data-ttu-id="83ef7-237">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-networkconnectiondetail-table.md">table NetworkConnectionDetail dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83ef7-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="83ef7-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="83ef7-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-240">Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelé.</span><span class="sxs-lookup"><span data-stu-id="83ef7-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="83ef7-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="83ef7-242">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-242">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p117">Indique si l’appelé s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non-VPN.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="83ef7-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="83ef7-246">décimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="83ef7-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-247">Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).</span><span class="sxs-lookup"><span data-stu-id="83ef7-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="83ef7-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-249">int</span><span class="sxs-lookup"><span data-stu-id="83ef7-249">int</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p118">Bande passante effectivement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="83ef7-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-253">Table appliedbandwidthsource</span><span class="sxs-lookup"><span data-stu-id="83ef7-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="83ef7-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83ef7-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83ef7-p119">Source de la capacité de bande passante imposée. Elle décrit l’origine de la limite de la bande passante (par exemple, « Serveur de stratégie », « Serveur TURN » ou « Modalité »).</span><span class="sxs-lookup"><span data-stu-id="83ef7-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-257">Appelant</span><span class="sxs-lookup"><span data-stu-id="83ef7-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="83ef7-258">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-258">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-259">Indique si des mesures ont été reçues de la part de l’appelant ; 1 pour oui, 0 pour non.</span><span class="sxs-lookup"><span data-stu-id="83ef7-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-260">Appelé</span><span class="sxs-lookup"><span data-stu-id="83ef7-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="83ef7-261">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-261">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-262">Indique si des mesures ont été reçues de la part du récepteur de l’appel ; 1 pour oui, 0 pour non.</span><span class="sxs-lookup"><span data-stu-id="83ef7-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="83ef7-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="83ef7-264">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-264">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-265">Indique si le rapport s’applique à une partie de l’appel ou à l’intégralité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="83ef7-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="83ef7-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="83ef7-267">légèrement</span><span class="sxs-lookup"><span data-stu-id="83ef7-267">bit</span></span></p></td>
<td><p><span data-ttu-id="83ef7-268">Indique si un appel a été classé comme médiocre (1) ou bon (0).</span><span class="sxs-lookup"><span data-stu-id="83ef7-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83ef7-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="83ef7-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="83ef7-270">entier très petit</span><span class="sxs-lookup"><span data-stu-id="83ef7-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83ef7-271">Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="83ef7-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83ef7-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="83ef7-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="83ef7-273">entier très petit</span><span class="sxs-lookup"><span data-stu-id="83ef7-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83ef7-274">Indique si l’utilisateur appelé s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="83ef7-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

