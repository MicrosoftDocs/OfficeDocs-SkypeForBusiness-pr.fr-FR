---
title: 'Lync Server 2013 : déterminer les exigences en matière de port et de pare-feu A/V externe'
description: 'Lync Server 2013 : déterminer les exigences en matière de port et de pare-feu A/V externe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550930"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="57ae8-103">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ae8-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57ae8-104">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="57ae8-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="57ae8-105">La communication audio/vidéo (A/V) peut être complexe.</span><span class="sxs-lookup"><span data-stu-id="57ae8-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="57ae8-106">En raison de la nature des protocoles utilisés dans A/V et de la façon dont les clients et les serveurs utilisent les protocoles, une section spéciale permet d’expliquer les différences entre les versions client et serveur.</span><span class="sxs-lookup"><span data-stu-id="57ae8-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="57ae8-107">Utilisez le pare-feu A/V et le tableau de ports suivants pour déterminer les exigences de pare-feu et les ports à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="57ae8-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="57ae8-108">Consultez ensuite la terminologie propre à la traduction d’adresses réseau (NAT, Network Address Translation), car cette fonctionnalité peut être implémentée de nombreuses façons.</span><span class="sxs-lookup"><span data-stu-id="57ae8-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="57ae8-109">Pour obtenir un exemple détaillé des paramètres de port de pare-feu, consultez la rubrique architectures de référence dans [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="57ae8-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="57ae8-110">Utilisation générale du protocole pour UDP et TCP dans le trafic audio/vidéo et multimédia</span><span class="sxs-lookup"><span data-stu-id="57ae8-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57ae8-111">Transport audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="57ae8-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="57ae8-112">Utilisation</span><span class="sxs-lookup"><span data-stu-id="57ae8-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57ae8-113">DATAGRAMME</span><span class="sxs-lookup"><span data-stu-id="57ae8-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="57ae8-114">Protocole de couche de transport préféré pour l’audio et la vidéo</span><span class="sxs-lookup"><span data-stu-id="57ae8-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57ae8-115">TCP</span><span class="sxs-lookup"><span data-stu-id="57ae8-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="57ae8-116">Protocole de couche transport de secours pour l’audio et la vidéo</span><span class="sxs-lookup"><span data-stu-id="57ae8-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="57ae8-117">Protocole de couche transport requis pour le partage d’application vers Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ae8-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="57ae8-118">Protocole de couche transport requis pour le transfert de fichiers vers Lync Server 2010 et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ae8-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="57ae8-119">Conditions requises pour les ports du pare-feu A/V externe pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="57ae8-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="57ae8-120">Les exigences de port de pare-feu pour les interfaces SIP et de conférence externes (et internes) sont cohérentes, quelle que soit la version de votre client ou la version du partenaire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="57ae8-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="57ae8-121">Il en est de même pour l’interface externe du serveur Edge audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="57ae8-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="57ae8-122">Pour la Fédération avec Office Communications Server 2007, le service Edge A/V exige que les règles de pare-feu externes autorisent le trafic RTP/TCP et RTP/UDP dans la plage de ports 50 000 à 59 999 pour circuler dans les deux directions.</span><span class="sxs-lookup"><span data-stu-id="57ae8-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="57ae8-123">Le tableau précédent part du principe que Lync Server 2013 est le partenaire de Fédération principal et qu’il est configuré pour communiquer avec l’un des autres types de partenaires de Fédération énumérés.</span><span class="sxs-lookup"><span data-stu-id="57ae8-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="57ae8-124">La configuration de la plage de ports audio/vidéo de 50000-000-59 999 doit prendre en compte que la plage de ports contiendra les ports sources des communications vers les partenaires de Fédération.</span><span class="sxs-lookup"><span data-stu-id="57ae8-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="57ae8-125">En détail, considérez qu’une communication est initiée à partir d’un partenaire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="57ae8-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="57ae8-126">La communication des ports de service Edge A/V dans la plage 50 000-000-59 999 se connectera au port TCP 443 attendu du service Edge A/V du partenaire.</span><span class="sxs-lookup"><span data-stu-id="57ae8-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="57ae8-127">À l’inverse, le trafic entrant vers votre port de service Edge A/V TCP 443 aura un port source dans la plage de 50000-000-59 999.</span><span class="sxs-lookup"><span data-stu-id="57ae8-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="57ae8-128">Différents pare-feu et stratégies pour l’administration du pare-feu peuvent nécessiter que seules des règles de destination soient configurées, ou exiger la configuration de la source et de la destination.</span><span class="sxs-lookup"><span data-stu-id="57ae8-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="57ae8-129">Si votre configuration requise concerne uniquement les ports de destination, les exigences audio/vidéo sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="57ae8-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57ae8-130">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="57ae8-130">Source IP</span></span></th>
<th><span data-ttu-id="57ae8-131">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="57ae8-131">Destination IP</span></span></th>
<th><span data-ttu-id="57ae8-132">Port de destination</span><span class="sxs-lookup"><span data-stu-id="57ae8-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57ae8-133">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-134">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-134">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="57ae8-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57ae8-136">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-137">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-137">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="57ae8-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57ae8-139">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-139">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-140">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="57ae8-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57ae8-142">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-142">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-143">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="57ae8-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57ae8-145">Si vos stratégies nécessitent à la fois des définitions de règles de pare-feu entrantes et sortantes, les exigences audio/vidéo sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="57ae8-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57ae8-146">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="57ae8-146">Source IP</span></span></th>
<th><span data-ttu-id="57ae8-147">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="57ae8-147">Destination IP</span></span></th>
<th><span data-ttu-id="57ae8-148">Port source</span><span class="sxs-lookup"><span data-stu-id="57ae8-148">Source Port</span></span></th>
<th><span data-ttu-id="57ae8-149">Port de destination</span><span class="sxs-lookup"><span data-stu-id="57ae8-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57ae8-150">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-151">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-151">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-152">TCP 50000-000-59 999</span><span class="sxs-lookup"><span data-stu-id="57ae8-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="57ae8-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="57ae8-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57ae8-154">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-155">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-155">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="57ae8-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="57ae8-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="57ae8-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57ae8-158">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-158">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-159">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-160">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-160">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="57ae8-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57ae8-162">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-162">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-163">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="57ae8-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="57ae8-164">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="57ae8-164">Any</span></span></p></td>
<td><p><span data-ttu-id="57ae8-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="57ae8-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="57ae8-166">Microsoft Office Communications Server 2007 nécessite une configuration légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="57ae8-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="57ae8-167">La plage de ports TCP et UDP de 50000 000-59 999 doit être ouverte et sortante.</span><span class="sxs-lookup"><span data-stu-id="57ae8-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="57ae8-168">Cette exigence est uniquement destinée à Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="57ae8-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="57ae8-169">Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013 nécessitent uniquement une plage TCP de 50000 000-59 999 ouvertes.</span><span class="sxs-lookup"><span data-stu-id="57ae8-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="57ae8-170">Configuration NAT requise pour le service Edge</span><span class="sxs-lookup"><span data-stu-id="57ae8-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="57ae8-171">Les conditions suivantes de l’interface NAT s’appliquent si vous choisissez de configurer des adresses IP privées non routables pour le service Edge :</span><span class="sxs-lookup"><span data-stu-id="57ae8-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="57ae8-172">La conversion d’adresses réseau ne peut être utilisée qu’avec l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="57ae8-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="57ae8-173">NAT n’est pas pris en charge avec une topologie Edge d’équilibrage de la charge matérielle (charge matérielle).</span><span class="sxs-lookup"><span data-stu-id="57ae8-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="57ae8-174">La conversion d’adresses réseau (NAT) ne peut être utilisée que sur l’interface Edge externe.</span><span class="sxs-lookup"><span data-stu-id="57ae8-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="57ae8-175">NAT n’est pas pris en charge sur l’interface interne Edge.</span><span class="sxs-lookup"><span data-stu-id="57ae8-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="57ae8-176">La conversion d’adresses réseau (NAT) doit être symétrique pour le trafic entrant et sortant.</span><span class="sxs-lookup"><span data-stu-id="57ae8-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="57ae8-177">Pour le trafic provenant d’Internet, tar doit modifier l’adresse IP de destination à partir de l’adresse IP publique à extension NAT du service Edge A/V vers son adresse IP externe.</span><span class="sxs-lookup"><span data-stu-id="57ae8-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="57ae8-178">L’adresse IP source doit rester intacte, de sorte que le service Edge A/V puisse trouver le chemin multimédia optimal.</span><span class="sxs-lookup"><span data-stu-id="57ae8-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="57ae8-179">Par exemple, dans la direction entrante dans la figure ci-dessous, l’adresse IP publique 131.107.155.30 a été remplacée par l’adresse IP externe (privée) 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="57ae8-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="57ae8-180">L’adresse IP source est restée inchangée.</span><span class="sxs-lookup"><span data-stu-id="57ae8-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="57ae8-181">Pour le trafic depuis le service Edge A/V vers Internet, tar doit modifier l’adresse IP source de l’adresse IP externe du service Edge A/V vers l’adresse IP publique à extension NAT.</span><span class="sxs-lookup"><span data-stu-id="57ae8-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="57ae8-182">Par exemple, dans la direction sortante dans la figure ci-dessous, l’adresse IP externe (privée) 10.45.16.10 a été remplacée par l’adresse IP publique 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="57ae8-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="57ae8-183">**La figure ci-dessous montre comment NAT modifie l’adresse IP de destination pour le trafic entrant et l’adresse IP source pour le trafic sortant.**</span><span class="sxs-lookup"><span data-stu-id="57ae8-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="57ae8-184">![Modification des adresses IP source/destination](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modification des adresses IP source/destination")</span><span class="sxs-lookup"><span data-stu-id="57ae8-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="57ae8-185">Les principaux points sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="57ae8-185">The key points are:</span></span>

  - <span data-ttu-id="57ae8-186">Trafic entrant sur le serveur qui exécute le service Edge A/V, l’adresse IP source ne change pas, mais l’adresse IP de destination passe de 131.107.155.30 à l’adresse IP traduite de 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="57ae8-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="57ae8-187">Trafic sortant du serveur qui exécute le service Edge A/V vers le poste de travail, l’adresse IP source passe de l’adresse IP publique du serveur à l’adresse IP publique du serveur exécutant le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="57ae8-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="57ae8-188">L’adresse IP de destination conserve l’adresse IP publique de la station de travail.</span><span class="sxs-lookup"><span data-stu-id="57ae8-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="57ae8-189">Une fois que le paquet quitte le premier périphérique NAT, la règle sur le périphérique NAT modifie l’adresse IP source du serveur exécutant l’adresse IP de l’interface externe du service Edge A/V (10.45.16.10) en son adresse IP publique (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="57ae8-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

