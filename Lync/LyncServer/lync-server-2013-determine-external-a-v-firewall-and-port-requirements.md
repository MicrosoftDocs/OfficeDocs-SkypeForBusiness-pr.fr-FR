---
title: 'Lync Server 2013 : Définition de la configuration requise pour le pare-feu A/V et les ports'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="be283-102">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be283-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be283-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="be283-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="be283-104">Les communications audio/vidéo (A/V) peuvent être complexes.</span><span class="sxs-lookup"><span data-stu-id="be283-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="be283-105">En raison de la nature des protocoles utilisés dans A/V et de la manière dont les clients et les serveurs utilisent les protocoles, une section spéciale est garante d’expliquer les différences entre les versions client et serveur.</span><span class="sxs-lookup"><span data-stu-id="be283-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="be283-106">Utilisez le pare-feu A/V et la table de port suivants pour déterminer les exigences de pare-feu et les ports à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="be283-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="be283-107">Ensuite, examinez la terminologie de la traduction d’adresses réseau (NAT), car la traduction d’adresses réseau peut être implémentée de diverses manières.</span><span class="sxs-lookup"><span data-stu-id="be283-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="be283-108">Pour obtenir un exemple détaillé de paramètres de port de pare-feu, consultez les architectures de référence dans les [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="be283-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="be283-109">Utilisation générale des protocoles pour UDP et TCP dans le trafic audio/vidéo et multimédia</span><span class="sxs-lookup"><span data-stu-id="be283-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be283-110">Transport audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="be283-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="be283-111">Utilisation</span><span class="sxs-lookup"><span data-stu-id="be283-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be283-112">UDP</span><span class="sxs-lookup"><span data-stu-id="be283-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="be283-113">Protocole préféré de couche de transport pour le son et la vidéo</span><span class="sxs-lookup"><span data-stu-id="be283-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be283-114">TCP</span><span class="sxs-lookup"><span data-stu-id="be283-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="be283-115">Protocole de couche de transport de secours pour le son et la vidéo</span><span class="sxs-lookup"><span data-stu-id="be283-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="be283-116">Protocole requis pour le partage d’application sur Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be283-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="be283-117">Protocole requis pour le transfert de fichiers vers Lync Server 2010 et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be283-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="be283-118">Exigences relatives aux ports de pare-feu A/V externes pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="be283-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="be283-119">La configuration requise pour les ports de pare-feu pour les interfaces SIP et de conférence externes (et internes) est cohérente, quelle que soit la version de votre client ou la version du partenaire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="be283-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="be283-120">Le même type n’est pas vrai pour l’interface externe du périphérique audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="be283-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="be283-121">Dans le cadre de la Fédération avec Office Communications Server 2007, le service Edge A/V exige que les règles de pare-feu externe autorisent le trafic RTP/TCP et RTP/UDP dans les 50 000 à 59 999 par le biais de la plage de port.</span><span class="sxs-lookup"><span data-stu-id="be283-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="be283-122">Le tableau précédent part du principe que Lync Server 2013 est le principal partenaire de Fédération et qu’il est configuré pour communiquer avec l’un des autres types de partenaires de Fédération répertoriés.</span><span class="sxs-lookup"><span data-stu-id="be283-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="be283-123">La configuration de la plage de ports audio/vidéo de 50000-59,999 doit prendre en compte que la plage de port va contenir les ports sources pour les communications avec les partenaires de Fédération.</span><span class="sxs-lookup"><span data-stu-id="be283-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="be283-124">En détail, considérez qu’une communication est lancée à partir d’un partenaire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="be283-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="be283-125">La communication des ports de service Edge A/V dans la plage 50000-59,999 se connectera au port TCP 443 du service Edge A/V du partenaire.</span><span class="sxs-lookup"><span data-stu-id="be283-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="be283-126">À l’inverse, le trafic entrant vers votre service de port TCP 443 a un port source dans la plage comprise entre 50000 et 59,999.</span><span class="sxs-lookup"><span data-stu-id="be283-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="be283-127">Les pare-feu et les stratégies différents pour l’administration du pare-feu peuvent nécessiter la configuration de règles de destination uniquement, ou exiger la configuration de la source et de la destination.</span><span class="sxs-lookup"><span data-stu-id="be283-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="be283-128">S’il s’agit de la configuration requise pour les ports de destination uniquement, les exigences audio et vidéo sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="be283-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be283-129">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="be283-129">Source IP</span></span></th>
<th><span data-ttu-id="be283-130">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="be283-130">Destination IP</span></span></th>
<th><span data-ttu-id="be283-131">Port de destination</span><span class="sxs-lookup"><span data-stu-id="be283-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be283-132">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-133">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-133">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="be283-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be283-135">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-136">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-136">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="be283-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be283-138">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-138">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-139">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="be283-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be283-141">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-141">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-142">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="be283-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be283-144">Si vos stratégies nécessitent à la fois les définitions des règles de pare-feu entrant et sortant, les exigences audio et vidéo sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="be283-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be283-145">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="be283-145">Source IP</span></span></th>
<th><span data-ttu-id="be283-146">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="be283-146">Destination IP</span></span></th>
<th><span data-ttu-id="be283-147">Port source</span><span class="sxs-lookup"><span data-stu-id="be283-147">Source Port</span></span></th>
<th><span data-ttu-id="be283-148">Port de destination</span><span class="sxs-lookup"><span data-stu-id="be283-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be283-149">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-150">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-150">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-151">TCP 50 000 à 59 999</span><span class="sxs-lookup"><span data-stu-id="be283-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="be283-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="be283-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be283-153">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-154">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-154">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="be283-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="be283-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="be283-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be283-157">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-157">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-158">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-159">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-159">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="be283-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be283-161">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-161">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-162">Interface de service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="be283-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="be283-163">Indifférente</span><span class="sxs-lookup"><span data-stu-id="be283-163">Any</span></span></p></td>
<td><p><span data-ttu-id="be283-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="be283-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="be283-165">La configuration de Microsoft Office Communications Server 2007 nécessite une configuration légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="be283-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="be283-166">Les plages de port TCP et UDP de 50000-59,999 doivent être ouvertes en entrée et en sortie.</span><span class="sxs-lookup"><span data-stu-id="be283-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="be283-167">Cette condition est uniquement requise pour Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="be283-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="be283-168">Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013 nécessitent uniquement la plage TCP 50000-59,999 ouverte.</span><span class="sxs-lookup"><span data-stu-id="be283-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="be283-169">Configuration NAT requise pour le service Edge</span><span class="sxs-lookup"><span data-stu-id="be283-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="be283-170">Les exigences suivantes concernant tar s’appliquent si vous choisissez de configurer des adresses IP privées non routables pour le service Edge:</span><span class="sxs-lookup"><span data-stu-id="be283-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="be283-171">TAR ne peut être utilisée qu’avec l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="be283-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="be283-172">TAR n’est pas pris en charge avec une topologie de bord de l’équilibrage de charge matérielle (HLB).</span><span class="sxs-lookup"><span data-stu-id="be283-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="be283-173">TAR ne peut être utilisée que sur l’interface latérale externe.</span><span class="sxs-lookup"><span data-stu-id="be283-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="be283-174">TAR n’est pas pris en charge sur l’interface latérale interne.</span><span class="sxs-lookup"><span data-stu-id="be283-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="be283-175">TAR doit être symétrique pour le trafic entrant et sortant.</span><span class="sxs-lookup"><span data-stu-id="be283-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="be283-176">Pour le trafic provenant d’Internet, tar doit remplacer l’adresse IP de destination par l’adresse IP publique compatible NAT du service Edge A/V par son adresse IP externe.</span><span class="sxs-lookup"><span data-stu-id="be283-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="be283-177">L’adresse IP source doit rester intacte, de sorte que le service Edge A/V peut trouver le chemin multimédia optimal.</span><span class="sxs-lookup"><span data-stu-id="be283-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="be283-178">Par exemple, dans la direction entrante dans l’illustration ci-dessous, l’adresse IP publique 131.107.155.30 a été remplacée par l’adresse IP (privée) 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="be283-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="be283-179">L’adresse IP source reste inchangée.</span><span class="sxs-lookup"><span data-stu-id="be283-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="be283-180">Pour le trafic du service Edge A/V vers Internet, tar doit remplacer l’adresse IP source par l’adresse IP externe du service Edge A/V par l’adresse IP publique compatible NAT.</span><span class="sxs-lookup"><span data-stu-id="be283-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="be283-181">Par exemple, dans la direction sortante dans la figure ci-dessous, l’adresse IP (privée) 10.45.16.10 a été remplacée par l’adresse IP publique 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="be283-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="be283-182">**La figure ci-dessous montre comment tar modifie l’adresse IP de destination pour le trafic entrant et l’adresse IP source pour le trafic sortant.**</span><span class="sxs-lookup"><span data-stu-id="be283-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="be283-183">![Modification des adresses IP de destination/source] (images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modification des adresses IP de destination/source")</span><span class="sxs-lookup"><span data-stu-id="be283-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="be283-184">Les points clés sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="be283-184">The key points are:</span></span>

  - <span data-ttu-id="be283-185">Le trafic entrant sur le serveur exécutant le service Edge A/V, l’adresse IP source reste inchangée mais l’adresse IP de destination passe d' 131.107.155.30 à l’adresse IP traduite de 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="be283-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="be283-186">Le trafic sortant du serveur exécutant le service Edge A/V vers la station de travail, l’adresse IP source passe de l’adresse IP publique du serveur à l’adresse IP publique du serveur exécutant le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="be283-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="be283-187">L’adresse IP de destination reste l’adresse IP publique de la station de travail.</span><span class="sxs-lookup"><span data-stu-id="be283-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="be283-188">Une fois que le paquet A quitté le premier périphérique NAT en sortie, la règle sur le périphérique NAT change l’adresse IP source du serveur exécutant l’adresse IP de l’interface externe A/V (10.45.16.10) sur son adresse IP publique (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="be283-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

