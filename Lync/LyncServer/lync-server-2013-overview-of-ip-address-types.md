---
title: 'Lync Server 2013 : vue d’ensemble des types d’adresses IP'
description: 'Lync Server 2013 : vue d’ensemble des types d’adresses IP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559220"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="9014d-103">Vue d’ensemble des types d’adresses IP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9014d-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9014d-104">_**Dernière modification de la rubrique :** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="9014d-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="9014d-105">Vous disposez de trois options lors de la configuration des adresses IP dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9014d-105">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="9014d-106">Vous pouvez configurer Lync Server 2013 pour prendre en charge uniquement IP version 4 (IPv4), uniquement IP version 6 (IPv6), ou une combinaison des deux (appelée *double pile*).</span><span class="sxs-lookup"><span data-stu-id="9014d-106">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="9014d-107">Il existe plusieurs problèmes à prendre en compte pour chaque type de configuration :</span><span class="sxs-lookup"><span data-stu-id="9014d-107">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="9014d-108">**IPv4 uniquement**     IPv6 a été créé car le monde a des adresses IPv4 insuffisantes.</span><span class="sxs-lookup"><span data-stu-id="9014d-108">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="9014d-109">Au final, IPv6 sera entièrement pris en charge dans le monde entier, mais pour l’instant, de nombreuses sociétés et appareils dont votre entreprise peut avoir besoin de communiquer ne prennent pas encore en charge IPv6, et peuvent ne pas prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="9014d-109">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="9014d-110">Une configuration IPv4 uniquement permet de s’assurer que votre implémentation Lync Server peut communiquer avec la plupart des périphériques existants.</span><span class="sxs-lookup"><span data-stu-id="9014d-110">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="9014d-111">**IPv6 uniquement**     Inversement, une implémentation complète de IPv6, pour le moment, exclut la communication avec de nombreux appareils existants.</span><span class="sxs-lookup"><span data-stu-id="9014d-111">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="9014d-112">**Double pile**     Une double pile est un réseau où les adresses IPv4 et IPv6 sont activées.</span><span class="sxs-lookup"><span data-stu-id="9014d-112">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="9014d-113">Cette configuration est prise en charge dans Lync Server 2013 car, dans la plupart des cas, la transition de Full-IPv4 à Full-IPv6 prend plusieurs années.</span><span class="sxs-lookup"><span data-stu-id="9014d-113">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="9014d-114">Les sections suivantes décrivent la compatibilité entre ces trois configurations pour différentes fonctionnalités Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9014d-114">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9014d-115">La configuration du client ou du serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="9014d-115">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="9014d-116">La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production.</span><span class="sxs-lookup"><span data-stu-id="9014d-116">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="9014d-117">Inscription du client</span><span class="sxs-lookup"><span data-stu-id="9014d-117">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9014d-118">Réseau de point de terminaison client</span><span class="sxs-lookup"><span data-stu-id="9014d-118">Client endpoint network</span></span></th>
<th><span data-ttu-id="9014d-119">Réseau de serveurs</span><span class="sxs-lookup"><span data-stu-id="9014d-119">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9014d-120">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-120">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-121">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-121">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-122">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-122">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-123">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-123">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-124">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-124">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-125">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-125">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-126">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-126">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-127">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-127">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-128">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-128">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-129">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-130">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-131">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-131">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-132">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-133">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="9014d-134">Client d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="9014d-134">Peer-to-Peer Client</span></span>

<span data-ttu-id="9014d-135">Les communications d’égal à égal incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9014d-135">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="9014d-136">Une fois que les deux clients ont été correctement enregistrés, les combinaisons suivantes sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="9014d-136">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9014d-137">Point de terminaison du client 1</span><span class="sxs-lookup"><span data-stu-id="9014d-137">Client endpoint 1</span></span></th>
<th><span data-ttu-id="9014d-138">Point de terminaison client 2</span><span class="sxs-lookup"><span data-stu-id="9014d-138">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9014d-139">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-139">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-140">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-140">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-141">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-141">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-142">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-142">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-143">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-143">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-144">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-144">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-145">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-146">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-146">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-147">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-148">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="9014d-149">Conférence</span><span class="sxs-lookup"><span data-stu-id="9014d-149">Conferencing</span></span>

<span data-ttu-id="9014d-150">La Conférence comprend l’audio/vidéo, le partage d’application et la collaboration de données (tableau blanc et partage de fichiers).</span><span class="sxs-lookup"><span data-stu-id="9014d-150">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9014d-151">Réseau de point de terminaison client</span><span class="sxs-lookup"><span data-stu-id="9014d-151">Client endpoint network</span></span></th>
<th><span data-ttu-id="9014d-152">Réseau de serveurs</span><span class="sxs-lookup"><span data-stu-id="9014d-152">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9014d-153">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-153">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-154">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-154">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-155">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-155">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-156">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-156">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-157">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-157">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-158">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-158">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-159">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-159">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-160">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-160">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-161">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-161">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-162">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-163">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-164">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-164">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-165">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-166">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="9014d-167">Serveur de médiation/RTC</span><span class="sxs-lookup"><span data-stu-id="9014d-167">Mediation Server/PSTN</span></span>

<span data-ttu-id="9014d-168">Lync Server 2013 ne prend pas en charge la déviation du trafic multimédia pour les appels de réseau téléphonique commuté (PSTN) si le trafic se fait via une interface IPv6.</span><span class="sxs-lookup"><span data-stu-id="9014d-168">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="9014d-169">Si la déviation du trafic multimédia est requise, nous vous recommandons de configurer la passerelle PSTN sur IPv4.</span><span class="sxs-lookup"><span data-stu-id="9014d-169">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9014d-170">Interface principale \*</span><span class="sxs-lookup"><span data-stu-id="9014d-170">Primary interface\*</span></span></th>
<th><span data-ttu-id="9014d-171">Interface PSTN (sur le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="9014d-171">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="9014d-172">Paramètre de passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="9014d-172">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9014d-173">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-173">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-174">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-174">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-175">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-175">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-176">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-177">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-178">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-178">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-179">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-180">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-181">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-181">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9014d-182">\* L’interface principale est l’interface qui communique avec les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9014d-182">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="9014d-183">Communications P2P des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="9014d-183">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="9014d-184">Les communications P2P avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9014d-184">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9014d-185">Réseau d’utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="9014d-185">Remote user network</span></span></th>
<th><span data-ttu-id="9014d-186">Serveur Edge (périmètre externe)</span><span class="sxs-lookup"><span data-stu-id="9014d-186">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9014d-187">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-187">IPv4</span></span></p></td>
<td><p><span data-ttu-id="9014d-188">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-188">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-189">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-189">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-190">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-190">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-191">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-191">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="9014d-192">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-192">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-193">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-193">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-194">Double pile</span><span class="sxs-lookup"><span data-stu-id="9014d-194">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-195">IPv6</span></span></p></td>
<td><p><span data-ttu-id="9014d-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-196">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="9014d-197">Configuration des pools frontaux et des pools de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="9014d-197">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="9014d-198">Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontaux et le pool de serveurs Edge interne.</span><span class="sxs-lookup"><span data-stu-id="9014d-198">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="9014d-199">Matrice des pools frontaux et des pools de serveurs Edge (périmètre interne)</span><span class="sxs-lookup"><span data-stu-id="9014d-199">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="9014d-200"><strong>Pool Edge : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-200"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-201"><strong>Pool de serveurs Edge : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-201"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-202"><strong>Pool de serveurs Edge : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-202"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-203"><strong>Pool frontal : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-203"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-204">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-205">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-206">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-206">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-207"><strong>Pool frontal : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-207"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-208">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-209">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-210">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-210">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-211"><strong>Pool frontal : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-211"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-212">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-212">No</span></span></p></td>
<td><p><span data-ttu-id="9014d-213">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-213">No</span></span></p></td>
<td><p><span data-ttu-id="9014d-214">Oui\*</span><span class="sxs-lookup"><span data-stu-id="9014d-214">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9014d-215">\* Utilisez cette combinaison uniquement dans un environnement de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="9014d-215">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="9014d-216">Le tableau suivant est une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.</span><span class="sxs-lookup"><span data-stu-id="9014d-216">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="9014d-217">Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)</span><span class="sxs-lookup"><span data-stu-id="9014d-217">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="9014d-218"><strong>Pool Edge (périmètre externe) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-218"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-219"><strong>Pool Edge (périmètre externe) : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-219"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-220"><strong>Pool Edge (périmètre externe) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-220"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-221"><strong>Pool Edge (périmètre interne) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-221"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-222">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-223">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-224">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-224">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9014d-225"><strong>Pool Edge (périmètre interne) : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-225"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-226">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-226">No</span></span></p></td>
<td><p><span data-ttu-id="9014d-227">Oui</span><span class="sxs-lookup"><span data-stu-id="9014d-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="9014d-228">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-228">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9014d-229"><strong>Pool Edge (périmètre interne) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="9014d-229"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="9014d-230">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-230">No</span></span></p></td>
<td><p><span data-ttu-id="9014d-231">Non</span><span class="sxs-lookup"><span data-stu-id="9014d-231">No</span></span></p></td>
<td><p><span data-ttu-id="9014d-232">Oui\*</span><span class="sxs-lookup"><span data-stu-id="9014d-232">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9014d-233">\* Utilisez cette combinaison uniquement dans un environnement de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="9014d-233">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="9014d-234">Prise en charge avancée de voix entreprise pour IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-234">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="9014d-235">Les déploiements qui incluent le contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1) ou la déviation du trafic multimédia doivent être configurés en tant que protocole IPv4 uniquement ou en tant qu’implémentation à double pile.</span><span class="sxs-lookup"><span data-stu-id="9014d-235">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9014d-236">Dans un déploiement à double pile, même si un client Lync se connecte à un serveur Lync à l’aide D’ipv6, Lync permettra de mapper une adresse IPv4 appropriée pour prendre en charge E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9014d-236">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="9014d-237">Le service d’informations d’emplacement avec des adresses IPv6 n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9014d-237">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="9014d-238">La messagerie unifiée Exchange ne prend pas en charge IPv6.</span><span class="sxs-lookup"><span data-stu-id="9014d-238">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="9014d-239">Pour la messagerie unifiée Exchange, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="9014d-239">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="9014d-240">L’utilisation D’ipv6 peut entraîner un échec lorsque des appels sont envoyés à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="9014d-240">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="9014d-241">Autres fonctionnalités de prise en charge de Lync Server 2013 pour IPv6</span><span class="sxs-lookup"><span data-stu-id="9014d-241">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="9014d-242">Outre les fonctionnalités et composants mentionnés précédemment, Lync Server 2013 prend en charge IPv6 pour les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="9014d-242">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="9014d-243">**Conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="9014d-243">**Persistent Chat**</span></span>
    
    <span data-ttu-id="9014d-244">Vous configurez IPv6 pour la conversation permanente à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9014d-244">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="9014d-245">Pour plus d’informations sur la configuration de la conversation permanente, voir la documentation sur le déploiement du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9014d-245">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="9014d-246">**Rapports sur la qualité de l’expérience et l’enregistrement des détails des appels (CDR)**</span><span class="sxs-lookup"><span data-stu-id="9014d-246">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="9014d-247">Les rapports de surveillance incluent l’adresse IP telle qu’elle est stockée dans la base de données du serveur de surveillance, qu’elle soit de type IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="9014d-247">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

