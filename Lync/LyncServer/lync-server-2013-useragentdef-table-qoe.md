---
title: 'Lync Server 2013 : table useragentdef table (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7294c70a0ebfd49f954bbe911d2fccb81d79fa54
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530101"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="d69db-102">Table useragentdef table (QoE) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69db-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d69db-103">_**Dernière modification de la rubrique :** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="d69db-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="d69db-104">Le tableau table useragentdef mappe les identificateurs de l’agent utilisateur aux noms descriptifs de l’agent.</span><span class="sxs-lookup"><span data-stu-id="d69db-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="d69db-105">Les agents utilisateurs sont des clients logiciels utilisés pour se connecter à Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d69db-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d69db-106">UAType</span><span class="sxs-lookup"><span data-stu-id="d69db-106">UAType</span></span></th>
<th><span data-ttu-id="d69db-107">UAName</span><span class="sxs-lookup"><span data-stu-id="d69db-107">UAName</span></span></th>
<th><span data-ttu-id="d69db-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="d69db-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d69db-109">0,1</span><span class="sxs-lookup"><span data-stu-id="d69db-109">1</span></span></p></td>
<td><p><span data-ttu-id="d69db-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="d69db-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="d69db-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="d69db-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-112">n°2</span><span class="sxs-lookup"><span data-stu-id="d69db-112">2</span></span></p></td>
<td><p><span data-ttu-id="d69db-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="d69db-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="d69db-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="d69db-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-115">4 </span><span class="sxs-lookup"><span data-stu-id="d69db-115">4</span></span></p></td>
<td><p><span data-ttu-id="d69db-116">O</span><span class="sxs-lookup"><span data-stu-id="d69db-116">OC</span></span></p></td>
<td><p><span data-ttu-id="d69db-117">O</span><span class="sxs-lookup"><span data-stu-id="d69db-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-118">8 </span><span class="sxs-lookup"><span data-stu-id="d69db-118">8</span></span></p></td>
<td><p><span data-ttu-id="d69db-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d69db-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="d69db-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d69db-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-121">16 </span><span class="sxs-lookup"><span data-stu-id="d69db-121">16</span></span></p></td>
<td><p><span data-ttu-id="d69db-122">LMC</span><span class="sxs-lookup"><span data-stu-id="d69db-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="d69db-123">LMC</span><span class="sxs-lookup"><span data-stu-id="d69db-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-124">32</span><span class="sxs-lookup"><span data-stu-id="d69db-124">32</span></span></p></td>
<td><p><span data-ttu-id="d69db-125">DVT</span><span class="sxs-lookup"><span data-stu-id="d69db-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="d69db-126">DVT</span><span class="sxs-lookup"><span data-stu-id="d69db-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-127">64</span><span class="sxs-lookup"><span data-stu-id="d69db-127">64</span></span></p></td>
<td><p><span data-ttu-id="d69db-128">MM</span><span class="sxs-lookup"><span data-stu-id="d69db-128">MM</span></span></p></td>
<td><p><span data-ttu-id="d69db-129">MM</span><span class="sxs-lookup"><span data-stu-id="d69db-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-130">64</span><span class="sxs-lookup"><span data-stu-id="d69db-130">64</span></span></p></td>
<td><p><span data-ttu-id="d69db-131">McDonald</span><span class="sxs-lookup"><span data-stu-id="d69db-131">MC</span></span></p></td>
<td><p><span data-ttu-id="d69db-132">MM</span><span class="sxs-lookup"><span data-stu-id="d69db-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-133">128</span><span class="sxs-lookup"><span data-stu-id="d69db-133">128</span></span></p></td>
<td><p><span data-ttu-id="d69db-134">Attendant</span><span class="sxs-lookup"><span data-stu-id="d69db-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="d69db-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="d69db-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-136">256</span><span class="sxs-lookup"><span data-stu-id="d69db-136">256</span></span></p></td>
<td><p><span data-ttu-id="d69db-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="d69db-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="d69db-138">DÉDIÉ</span><span class="sxs-lookup"><span data-stu-id="d69db-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-139">512</span><span class="sxs-lookup"><span data-stu-id="d69db-139">512</span></span></p></td>
<td><p><span data-ttu-id="d69db-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="d69db-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="d69db-141">CAA</span><span class="sxs-lookup"><span data-stu-id="d69db-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-142">512</span><span class="sxs-lookup"><span data-stu-id="d69db-142">512</span></span></p></td>
<td><p><span data-ttu-id="d69db-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="d69db-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="d69db-144">CAA</span><span class="sxs-lookup"><span data-stu-id="d69db-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-145">1024</span><span class="sxs-lookup"><span data-stu-id="d69db-145">1024</span></span></p></td>
<td><p><span data-ttu-id="d69db-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="d69db-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="d69db-147">ÉCHOUÉ</span><span class="sxs-lookup"><span data-stu-id="d69db-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-148">1032</span><span class="sxs-lookup"><span data-stu-id="d69db-148">1032</span></span></p></td>
<td><p><span data-ttu-id="d69db-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="d69db-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="d69db-150">CPS</span><span class="sxs-lookup"><span data-stu-id="d69db-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-151">1040</span><span class="sxs-lookup"><span data-stu-id="d69db-151">1040</span></span></p></td>
<td><p><span data-ttu-id="d69db-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="d69db-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="d69db-153">AS</span><span class="sxs-lookup"><span data-stu-id="d69db-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-154">2048</span><span class="sxs-lookup"><span data-stu-id="d69db-154">2048</span></span></p></td>
<td><p><span data-ttu-id="d69db-155">Microsoft. RTC. applications. CCS</span><span class="sxs-lookup"><span data-stu-id="d69db-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="d69db-156">Network</span><span class="sxs-lookup"><span data-stu-id="d69db-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-157">16386</span><span class="sxs-lookup"><span data-stu-id="d69db-157">16386</span></span></p></td>
<td><p><span data-ttu-id="d69db-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="d69db-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="d69db-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="d69db-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-160">16387</span><span class="sxs-lookup"><span data-stu-id="d69db-160">16387</span></span></p></td>
<td><p><span data-ttu-id="d69db-161">CWA</span><span class="sxs-lookup"><span data-stu-id="d69db-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="d69db-162">CWA</span><span class="sxs-lookup"><span data-stu-id="d69db-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-163">16388</span><span class="sxs-lookup"><span data-stu-id="d69db-163">16388</span></span></p></td>
<td><p><span data-ttu-id="d69db-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="d69db-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="d69db-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="d69db-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-166">16389</span><span class="sxs-lookup"><span data-stu-id="d69db-166">16389</span></span></p></td>
<td><p><span data-ttu-id="d69db-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="d69db-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="d69db-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="d69db-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-169">16393</span><span class="sxs-lookup"><span data-stu-id="d69db-169">16393</span></span></p></td>
<td><p><span data-ttu-id="d69db-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="d69db-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="d69db-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="d69db-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-172">16395</span><span class="sxs-lookup"><span data-stu-id="d69db-172">16395</span></span></p></td>
<td><p><span data-ttu-id="d69db-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="d69db-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="d69db-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="d69db-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-175">16396</span><span class="sxs-lookup"><span data-stu-id="d69db-175">16396</span></span></p></td>
<td><p><span data-ttu-id="d69db-176">ER</span><span class="sxs-lookup"><span data-stu-id="d69db-176">ST</span></span></p></td>
<td><p><span data-ttu-id="d69db-177">ER</span><span class="sxs-lookup"><span data-stu-id="d69db-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-178">16397</span><span class="sxs-lookup"><span data-stu-id="d69db-178">16397</span></span></p></td>
<td><p><span data-ttu-id="d69db-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="d69db-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="d69db-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="d69db-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-181">16398</span><span class="sxs-lookup"><span data-stu-id="d69db-181">16398</span></span></p></td>
<td><p><span data-ttu-id="d69db-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="d69db-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="d69db-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="d69db-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-184">16399</span><span class="sxs-lookup"><span data-stu-id="d69db-184">16399</span></span></p></td>
<td><p><span data-ttu-id="d69db-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="d69db-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="d69db-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="d69db-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-187">16400</span><span class="sxs-lookup"><span data-stu-id="d69db-187">16400</span></span></p></td>
<td><p><span data-ttu-id="d69db-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="d69db-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="d69db-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="d69db-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-190">16401</span><span class="sxs-lookup"><span data-stu-id="d69db-190">16401</span></span></p></td>
<td><p><span data-ttu-id="d69db-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="d69db-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="d69db-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="d69db-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-193">16402</span><span class="sxs-lookup"><span data-stu-id="d69db-193">16402</span></span></p></td>
<td><p><span data-ttu-id="d69db-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="d69db-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="d69db-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="d69db-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-196">16403</span><span class="sxs-lookup"><span data-stu-id="d69db-196">16403</span></span></p></td>
<td><p><span data-ttu-id="d69db-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="d69db-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="d69db-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="d69db-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-199">16404</span><span class="sxs-lookup"><span data-stu-id="d69db-199">16404</span></span></p></td>
<td><p><span data-ttu-id="d69db-200">PIEC</span><span class="sxs-lookup"><span data-stu-id="d69db-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="d69db-201">PIEC</span><span class="sxs-lookup"><span data-stu-id="d69db-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-202">16405</span><span class="sxs-lookup"><span data-stu-id="d69db-202">16405</span></span></p></td>
<td><p><span data-ttu-id="d69db-203">LWA</span><span class="sxs-lookup"><span data-stu-id="d69db-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="d69db-204">LWA</span><span class="sxs-lookup"><span data-stu-id="d69db-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-205">16406</span><span class="sxs-lookup"><span data-stu-id="d69db-205">16406</span></span></p></td>
<td><p><span data-ttu-id="d69db-206">OWA</span><span class="sxs-lookup"><span data-stu-id="d69db-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="d69db-207">OWA</span><span class="sxs-lookup"><span data-stu-id="d69db-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-208">16407</span><span class="sxs-lookup"><span data-stu-id="d69db-208">16407</span></span></p></td>
<td><p><span data-ttu-id="d69db-209">AOC</span><span class="sxs-lookup"><span data-stu-id="d69db-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="d69db-210">AOC</span><span class="sxs-lookup"><span data-stu-id="d69db-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-211">16408</span><span class="sxs-lookup"><span data-stu-id="d69db-211">16408</span></span></p></td>
<td><p><span data-ttu-id="d69db-212">GCC</span><span class="sxs-lookup"><span data-stu-id="d69db-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="d69db-213">GCC</span><span class="sxs-lookup"><span data-stu-id="d69db-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-214">16409</span><span class="sxs-lookup"><span data-stu-id="d69db-214">16409</span></span></p></td>
<td><p><span data-ttu-id="d69db-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="d69db-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="d69db-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="d69db-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-217">16410</span><span class="sxs-lookup"><span data-stu-id="d69db-217">16410</span></span></p></td>
<td><p><span data-ttu-id="d69db-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="d69db-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="d69db-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="d69db-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69db-220">32769</span><span class="sxs-lookup"><span data-stu-id="d69db-220">32769</span></span></p></td>
<td><p><span data-ttu-id="d69db-221">Passerelle</span><span class="sxs-lookup"><span data-stu-id="d69db-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="d69db-222">Passerelle</span><span class="sxs-lookup"><span data-stu-id="d69db-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69db-223">32770</span><span class="sxs-lookup"><span data-stu-id="d69db-223">32770</span></span></p></td>
<td><p><span data-ttu-id="d69db-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="d69db-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="d69db-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="d69db-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

