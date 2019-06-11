---
title: 'Lync Server 2013 : Vue d’ensemble des types d’adresse IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="76ad2-102">Vue d’ensemble des types d’adresse IP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76ad2-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76ad2-103">_**Dernière modification de la rubrique:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="76ad2-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="76ad2-104">Trois options s’offrent à vous lorsque vous configurez les adresses IP dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76ad2-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="76ad2-105">Vous pouvez configurer Lync Server 2013 de manière à prendre en charge uniquement le protocole IP version 4 (IPv4), uniquement le protocole IPv4 version 6 (IPv6) ou une combinaison des deux (appelé *pile double*).</span><span class="sxs-lookup"><span data-stu-id="76ad2-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="76ad2-106">Chaque type de configuration implique certains problèmes à prendre en considération :</span><span class="sxs-lookup"><span data-stu-id="76ad2-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="76ad2-107">**IPv4 uniquement**   IPv6 a été créé, car le monde ne dispose plus d’adresses IPv4.</span><span class="sxs-lookup"><span data-stu-id="76ad2-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="76ad2-108">Au final, IPv6 sera entièrement pris en charge partout mais, pour l’instant, de nombreuses sociétés et périphériques avec lesquels votre entreprise peut avoir à communiquer ne prennent pas encore en charge IPv6, et ce pour encore quelque temps.</span><span class="sxs-lookup"><span data-stu-id="76ad2-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="76ad2-109">Une configuration IPv4 uniquement permet de s’assurer que votre implémentation Lync Server peut communiquer avec la plupart des appareils existants.</span><span class="sxs-lookup"><span data-stu-id="76ad2-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="76ad2-110">\*\*\*\*   Pour le moment, le protocole IPv6 ne peut pas être associé à de nombreux périphériques existants.</span><span class="sxs-lookup"><span data-stu-id="76ad2-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="76ad2-111">\*\*\*\*   Stack Double Stack est un réseau sur lequel les adresses IPv4 et IPv6 sont activées.</span><span class="sxs-lookup"><span data-stu-id="76ad2-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="76ad2-112">Cette configuration est prise en charge dans Lync Server 2013, car dans la plupart des cas, le passage de l’intégralité du protocole IPv4 au protocole IPv6 complet nécessite plusieurs années.</span><span class="sxs-lookup"><span data-stu-id="76ad2-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="76ad2-113">Les sections suivantes décrivent la compatibilité entre ces trois configurations pour différentes fonctionnalités de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76ad2-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76ad2-p104">La configuration client ou serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou en laboratoire. La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production.</span><span class="sxs-lookup"><span data-stu-id="76ad2-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="76ad2-116">Enregistrement client</span><span class="sxs-lookup"><span data-stu-id="76ad2-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76ad2-117">Réseau de point de terminaison client</span><span class="sxs-lookup"><span data-stu-id="76ad2-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="76ad2-118">Réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="76ad2-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-122">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-123">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-125">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-126">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-127">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-130">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="76ad2-133">Client P2P</span><span class="sxs-lookup"><span data-stu-id="76ad2-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="76ad2-p105">Les communications P2P incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers. Lorsque les deux clients sont enregistrés, les combinaisons suivantes sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="76ad2-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76ad2-136">Point de terminaison client 1</span><span class="sxs-lookup"><span data-stu-id="76ad2-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="76ad2-137">Point de terminaison client 2</span><span class="sxs-lookup"><span data-stu-id="76ad2-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-141">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-142">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-143">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-145">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="76ad2-148">Téléconférence</span><span class="sxs-lookup"><span data-stu-id="76ad2-148">Conferencing</span></span>

<span data-ttu-id="76ad2-149">Les conférences incluent l’audio/la vidéo, le partage d’application et la collaboration sur les données (tableau blanc et partage de fichiers).</span><span class="sxs-lookup"><span data-stu-id="76ad2-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76ad2-150">Réseau de point de terminaison client</span><span class="sxs-lookup"><span data-stu-id="76ad2-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="76ad2-151">Réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="76ad2-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-155">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-156">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-158">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-159">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-160">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-163">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="76ad2-166">Serveur de médiation/RTC</span><span class="sxs-lookup"><span data-stu-id="76ad2-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="76ad2-167">Lync Server 2013 ne prend pas en charge la dérivation multimédia pour les appels de réseau téléphonique commuté (PSTN) si le trafic provient d’une interface IPv6.</span><span class="sxs-lookup"><span data-stu-id="76ad2-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="76ad2-168">Si la déviation du trafic multimédia est requise, nous recommandons que la passerelle RTC soit configurée sur IPv4.</span><span class="sxs-lookup"><span data-stu-id="76ad2-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76ad2-169">Interface principale\*</span><span class="sxs-lookup"><span data-stu-id="76ad2-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="76ad2-170">Interface RTC (sur le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="76ad2-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="76ad2-171">Paramètre de passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="76ad2-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-173">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-175">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-176">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-178">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-179">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76ad2-181">\*L’interface principale est l’interface qui communique avec les composants serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="76ad2-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="76ad2-182">Communications P2P d’utilisateur distant</span><span class="sxs-lookup"><span data-stu-id="76ad2-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="76ad2-183">Les communications P2P avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="76ad2-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76ad2-184">Réseau d’utilisateur distant</span><span class="sxs-lookup"><span data-stu-id="76ad2-184">Remote user network</span></span></th>
<th><span data-ttu-id="76ad2-185">Serveur Edge (périmètre externe)</span><span class="sxs-lookup"><span data-stu-id="76ad2-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="76ad2-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-188">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="76ad2-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-190">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="76ad2-191">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-193">Double pile</span><span class="sxs-lookup"><span data-stu-id="76ad2-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="76ad2-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="76ad2-196">Configuration des pools frontal et Edge</span><span class="sxs-lookup"><span data-stu-id="76ad2-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="76ad2-197">Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontal et le pool de serveurs Edge interne.</span><span class="sxs-lookup"><span data-stu-id="76ad2-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="76ad2-198">Matrice de pool frontal et de pool Edge (périmètre interne)</span><span class="sxs-lookup"><span data-stu-id="76ad2-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="76ad2-199"><strong>Pool Edge : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-200"><strong>Pool Edge : Double pile</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-201"><strong>Pool Edge : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-202"><strong>Pool frontal : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-203">Oui</span><span class="sxs-lookup"><span data-stu-id="76ad2-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-204">Oui</span><span class="sxs-lookup"><span data-stu-id="76ad2-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-205">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-206"><strong>Pool frontal : Double pile</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-207">Oui </span><span class="sxs-lookup"><span data-stu-id="76ad2-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-208">Oui</span><span class="sxs-lookup"><span data-stu-id="76ad2-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-209">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-210"><strong>Pool frontal : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-211">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-211">No</span></span></p></td>
<td><p><span data-ttu-id="76ad2-212">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-212">No</span></span></p></td>
<td><p><span data-ttu-id="76ad2-213">Oui\*</span><span class="sxs-lookup"><span data-stu-id="76ad2-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76ad2-214">\*Utilisez cette combinaison uniquement dans un environnement Lab.</span><span class="sxs-lookup"><span data-stu-id="76ad2-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="76ad2-215">Le tableau ci-dessous représente une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.</span><span class="sxs-lookup"><span data-stu-id="76ad2-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="76ad2-216">Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)</span><span class="sxs-lookup"><span data-stu-id="76ad2-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="76ad2-217"><strong>Pool Edge (périmètre externe) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-218"><strong>Pool Edge (périmètre externe) : Double pile</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-219"><strong>Pool Edge (périmètre externe) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-220"><strong>Pool Edge (périmètre interne) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-221">Oui</span><span class="sxs-lookup"><span data-stu-id="76ad2-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-222">Oui</span><span class="sxs-lookup"><span data-stu-id="76ad2-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-223">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ad2-224"><strong>Pool Edge (périmètre interne) : Double pile</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-225">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-225">No</span></span></p></td>
<td><p><span data-ttu-id="76ad2-226">Oui</span><span class="sxs-lookup"><span data-stu-id="76ad2-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="76ad2-227">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ad2-228"><strong>Pool Edge (périmètre interne) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="76ad2-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="76ad2-229">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-229">No</span></span></p></td>
<td><p><span data-ttu-id="76ad2-230">Non</span><span class="sxs-lookup"><span data-stu-id="76ad2-230">No</span></span></p></td>
<td><p><span data-ttu-id="76ad2-231">Oui\*</span><span class="sxs-lookup"><span data-stu-id="76ad2-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76ad2-232">\*Utilisez cette combinaison uniquement dans un environnement Lab.</span><span class="sxs-lookup"><span data-stu-id="76ad2-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="76ad2-233">Prise en charge Voix Entreprise pour IPv6 avancée</span><span class="sxs-lookup"><span data-stu-id="76ad2-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="76ad2-234">Les déploiements qui incluent le service Contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1), ou la déviation du trafic multimédia doivent être configurés sur une implémentation IPv4 uniquement ou double pile.</span><span class="sxs-lookup"><span data-stu-id="76ad2-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76ad2-235">Dans un déploiement à double empilage, même si un client Lync se connecte à un serveur Lync à l’aide du protocole IPv6, Lync fera tout particulièrement un effort pour mapper une adresse IPv4 appropriée à la prise en charge de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="76ad2-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="76ad2-236">Le service d’information d’emplacement avec les adresses IPv6 n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="76ad2-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="76ad2-p107">La messagerie unifiée Exchange (UM) ne prend pas en charge IPv6. Pour cette fonctionnalité, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6. L’utilisation d’IPv6 peut entraîner des échecs lorsque les appels sont envoyés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="76ad2-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="76ad2-240">Autres fonctionnalités de Lync Server 2013 prises en charge pour IPv6</span><span class="sxs-lookup"><span data-stu-id="76ad2-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="76ad2-241">Outre les fonctionnalités et composants mentionnés précédemment, Lync Server 2013 prend en charge le protocole IPv6 pour les fonctionnalités suivantes:</span><span class="sxs-lookup"><span data-stu-id="76ad2-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="76ad2-242">**Conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="76ad2-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="76ad2-243">Vous pouvez configurer le protocole IPv6 pour une conversation permanente à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="76ad2-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="76ad2-244">Pour plus d’informations sur la configuration d’une conversation permanente, voir la documentation déploiement d’un serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="76ad2-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="76ad2-245">**Rapports de qualité de l’expérience (QoE) et d’enregistrement des détails des appels**</span><span class="sxs-lookup"><span data-stu-id="76ad2-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="76ad2-246">Les rapports de suivi comportent l’adresse IP telle que stockée dans la base de données du serveur de suivi, qu’elle soit de type IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="76ad2-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

