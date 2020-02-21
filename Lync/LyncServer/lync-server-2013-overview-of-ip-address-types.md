---
title: 'Lync Server 2013 : vue d’ensemble des types d’adresses IP'
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
ms.openlocfilehash: 417b304825da6a611ccfdaf3521b2d9571cd4756
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="d418f-102">Vue d’ensemble des types d’adresses IP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d418f-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d418f-103">_**Dernière modification de la rubrique :** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="d418f-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="d418f-104">Vous disposez de trois options lors de la configuration des adresses IP dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d418f-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="d418f-105">Vous pouvez configurer Lync Server 2013 pour prendre en charge uniquement IP version 4 (IPv4), uniquement IP version 6 (IPv6), ou une combinaison des deux (appelée *double pile*).</span><span class="sxs-lookup"><span data-stu-id="d418f-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="d418f-106">Il existe plusieurs problèmes à prendre en compte pour chaque type de configuration :</span><span class="sxs-lookup"><span data-stu-id="d418f-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="d418f-107">**IPv4 uniquement**   IPv6 a été créé car le monde a des adresses IPv4 insuffisantes.</span><span class="sxs-lookup"><span data-stu-id="d418f-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="d418f-108">Au final, IPv6 sera entièrement pris en charge dans le monde entier, mais pour l’instant, de nombreuses sociétés et appareils dont votre entreprise peut avoir besoin de communiquer ne prennent pas encore en charge IPv6, et peuvent ne pas prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="d418f-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="d418f-109">Une configuration IPv4 uniquement permet de s’assurer que votre implémentation Lync Server peut communiquer avec la plupart des périphériques existants.</span><span class="sxs-lookup"><span data-stu-id="d418f-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="d418f-110">**IPv6 uniquement**   inversement, une implémentation complète d’IPv6, à ce stade, exclut la communication avec de nombreux appareils existants.</span><span class="sxs-lookup"><span data-stu-id="d418f-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="d418f-111">**La double**   pile double pile est un réseau où les adresses IPv4 et IPv6 sont activées.</span><span class="sxs-lookup"><span data-stu-id="d418f-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="d418f-112">Cette configuration est prise en charge dans Lync Server 2013 car, dans la plupart des cas, la transition de Full-IPv4 à Full-IPv6 prend plusieurs années.</span><span class="sxs-lookup"><span data-stu-id="d418f-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="d418f-113">Les sections suivantes décrivent la compatibilité entre ces trois configurations pour différentes fonctionnalités Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d418f-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d418f-114">La configuration du client ou du serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="d418f-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="d418f-115">La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production.</span><span class="sxs-lookup"><span data-stu-id="d418f-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="d418f-116">Inscription du client</span><span class="sxs-lookup"><span data-stu-id="d418f-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d418f-117">Réseau de point de terminaison client</span><span class="sxs-lookup"><span data-stu-id="d418f-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="d418f-118">Réseau de serveurs</span><span class="sxs-lookup"><span data-stu-id="d418f-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d418f-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-120">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-121">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-122">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-123">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-124">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-125">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-126">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-127">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-130">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="d418f-133">Client d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="d418f-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="d418f-134">Les communications d’égal à égal incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d418f-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="d418f-135">Une fois que les deux clients ont été correctement enregistrés, les combinaisons suivantes sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="d418f-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d418f-136">Point de terminaison du client 1</span><span class="sxs-lookup"><span data-stu-id="d418f-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="d418f-137">Point de terminaison client 2</span><span class="sxs-lookup"><span data-stu-id="d418f-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d418f-138">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-139">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-140">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-141">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-142">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-143">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-145">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="d418f-148">Vidéoconférence</span><span class="sxs-lookup"><span data-stu-id="d418f-148">Conferencing</span></span>

<span data-ttu-id="d418f-149">La Conférence comprend l’audio/vidéo, le partage d’application et la collaboration de données (tableau blanc et partage de fichiers).</span><span class="sxs-lookup"><span data-stu-id="d418f-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d418f-150">Réseau de point de terminaison client</span><span class="sxs-lookup"><span data-stu-id="d418f-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="d418f-151">Réseau de serveurs</span><span class="sxs-lookup"><span data-stu-id="d418f-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d418f-152">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-153">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-154">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-155">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-156">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-157">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-158">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-159">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-160">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-163">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="d418f-166">Serveur de médiation/RTC</span><span class="sxs-lookup"><span data-stu-id="d418f-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="d418f-167">Lync Server 2013 ne prend pas en charge la déviation du trafic multimédia pour les appels de réseau téléphonique commuté (PSTN) si le trafic se fait via une interface IPv6.</span><span class="sxs-lookup"><span data-stu-id="d418f-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="d418f-168">Si la déviation du trafic multimédia est requise, nous vous recommandons de configurer la passerelle PSTN sur IPv4.</span><span class="sxs-lookup"><span data-stu-id="d418f-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d418f-169">Interface principale \*</span><span class="sxs-lookup"><span data-stu-id="d418f-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="d418f-170">Interface PSTN (sur le serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="d418f-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="d418f-171">Paramètre de passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="d418f-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d418f-172">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-173">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-174">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-175">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-176">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-177">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-178">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-179">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d418f-181">\*L’interface principale est l’interface qui communique avec les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d418f-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="d418f-182">Communications P2P des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="d418f-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="d418f-183">Les communications P2P avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d418f-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d418f-184">Réseau d’utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="d418f-184">Remote user network</span></span></th>
<th><span data-ttu-id="d418f-185">Serveur Edge (périmètre externe)</span><span class="sxs-lookup"><span data-stu-id="d418f-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d418f-186">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d418f-187">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-188">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-189">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-190">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d418f-191">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-193">Double pile</span><span class="sxs-lookup"><span data-stu-id="d418f-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d418f-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="d418f-196">Configuration des pools frontaux et des pools de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="d418f-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="d418f-197">Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontaux et le pool de serveurs Edge interne.</span><span class="sxs-lookup"><span data-stu-id="d418f-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="d418f-198">Matrice des pools frontaux et des pools de serveurs Edge (périmètre interne)</span><span class="sxs-lookup"><span data-stu-id="d418f-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="d418f-199"><strong>Pool Edge : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-200"><strong>Pool de serveurs Edge : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-201"><strong>Pool de serveurs Edge : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-202"><strong>Pool frontal : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-203">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-204">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-205">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-206"><strong>Pool frontal : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-207">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-208">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-209">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-210"><strong>Pool frontal : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-211">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-211">No</span></span></p></td>
<td><p><span data-ttu-id="d418f-212">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-212">No</span></span></p></td>
<td><p><span data-ttu-id="d418f-213">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d418f-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d418f-214">\*Utilisez cette combinaison uniquement dans un environnement de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="d418f-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="d418f-215">Le tableau suivant est une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.</span><span class="sxs-lookup"><span data-stu-id="d418f-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="d418f-216">Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)</span><span class="sxs-lookup"><span data-stu-id="d418f-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="d418f-217"><strong>Pool Edge (périmètre externe) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-218"><strong>Pool Edge (périmètre externe) : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-219"><strong>Pool Edge (périmètre externe) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-220"><strong>Pool Edge (périmètre interne) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-221">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-222">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-223">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d418f-224"><strong>Pool Edge (périmètre interne) : double pile</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-225">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-225">No</span></span></p></td>
<td><p><span data-ttu-id="d418f-226">Oui</span><span class="sxs-lookup"><span data-stu-id="d418f-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="d418f-227">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d418f-228"><strong>Pool Edge (périmètre interne) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d418f-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="d418f-229">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-229">No</span></span></p></td>
<td><p><span data-ttu-id="d418f-230">Non</span><span class="sxs-lookup"><span data-stu-id="d418f-230">No</span></span></p></td>
<td><p><span data-ttu-id="d418f-231">Oui\*</span><span class="sxs-lookup"><span data-stu-id="d418f-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d418f-232">\*Utilisez cette combinaison uniquement dans un environnement de laboratoire.</span><span class="sxs-lookup"><span data-stu-id="d418f-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="d418f-233">Prise en charge avancée de voix entreprise pour IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="d418f-234">Les déploiements qui incluent le contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1) ou la déviation du trafic multimédia doivent être configurés en tant que protocole IPv4 uniquement ou en tant qu’implémentation à double pile.</span><span class="sxs-lookup"><span data-stu-id="d418f-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d418f-235">Dans un déploiement à double pile, même si un client Lync se connecte à un serveur Lync à l’aide D’ipv6, Lync permettra de mapper une adresse IPv4 appropriée pour prendre en charge E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d418f-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="d418f-236">Le service d’informations d’emplacement avec des adresses IPv6 n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d418f-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="d418f-237">La messagerie unifiée Exchange ne prend pas en charge IPv6.</span><span class="sxs-lookup"><span data-stu-id="d418f-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="d418f-238">Pour la messagerie unifiée Exchange, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="d418f-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="d418f-239">L’utilisation D’ipv6 peut entraîner un échec lorsque des appels sont envoyés à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d418f-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="d418f-240">Autres fonctionnalités de prise en charge de Lync Server 2013 pour IPv6</span><span class="sxs-lookup"><span data-stu-id="d418f-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="d418f-241">Outre les fonctionnalités et composants mentionnés précédemment, Lync Server 2013 prend en charge IPv6 pour les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="d418f-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="d418f-242">**Conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="d418f-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="d418f-243">Vous configurez IPv6 pour la conversation permanente à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d418f-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="d418f-244">Pour plus d’informations sur la configuration de la conversation permanente, voir la documentation sur le déploiement du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="d418f-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="d418f-245">**Rapports sur la qualité de l’expérience et l’enregistrement des détails des appels (CDR)**</span><span class="sxs-lookup"><span data-stu-id="d418f-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="d418f-246">Les rapports de surveillance incluent l’adresse IP telle qu’elle est stockée dans la base de données du serveur de surveillance, qu’elle soit de type IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="d418f-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

