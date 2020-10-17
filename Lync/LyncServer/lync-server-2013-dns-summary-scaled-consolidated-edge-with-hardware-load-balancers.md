---
title: Résumé des enregistrements DNS-serveur Edge consolidé ajusté avec programmes d’équilibrage de la charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5847a43c6d07cf188c97cd8de6a47dfb83e1468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501281"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="9504d-102">Résumé des enregistrements DNS-serveur Edge consolidé ajusté avec programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9504d-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9504d-103">_**Dernière modification de la rubrique :** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="9504d-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="9504d-104">Les exigences liées aux enregistrements DNS pour l’accès à distance à Lync Server 2013 sont relativement simples par rapport à celles des certificats et des ports.</span><span class="sxs-lookup"><span data-stu-id="9504d-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="9504d-105">De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de l’activation de la Fédération.</span><span class="sxs-lookup"><span data-stu-id="9504d-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="9504d-106">Pour plus d’informations sur les exigences DNS de Lync 2013, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9504d-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9504d-107">Pour plus d’informations sur la configuration automatique des clients Lync 2013 si le DNS split-brain n’est pas configuré, consultez la section « Configuration automatique sans DNS split brain » dans [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9504d-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="9504d-108">Le tableau suivant contient une synthèse des enregistrements DNS requis pour prendre en charge le serveur Edge consolidé ajusté (avec équilibrage de charge matérielle) présenté dans la figure.</span><span class="sxs-lookup"><span data-stu-id="9504d-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="9504d-109">Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync.</span><span class="sxs-lookup"><span data-stu-id="9504d-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="9504d-110">Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="9504d-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="9504d-111">IMPORTANT : configuration requise pour la carte réseau de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9504d-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="9504d-112">Pour éviter les problèmes de routage, vérifiez qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="9504d-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="9504d-113">Par exemple, comme illustré dans la figure du scénario de serveur Edge consolidé ajusté dans le [serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), la passerelle par défaut pointe vers le pare-feu externe.</span><span class="sxs-lookup"><span data-stu-id="9504d-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="9504d-114">Vous pouvez configurer deux cartes réseau dans chacun de vos serveurs Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="9504d-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="9504d-115">**Carte réseau 1 (interface interne)**</span><span class="sxs-lookup"><span data-stu-id="9504d-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="9504d-116">Interface interne avec 172.25.33.10 affecté.</span><span class="sxs-lookup"><span data-stu-id="9504d-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="9504d-117">Aucune passerelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="9504d-117">No default gateway.</span></span>
    
    <span data-ttu-id="9504d-118">Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne du serveur Edge et les réseaux qui contiennent des clients ou des serveurs Lync Server exécutant Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="9504d-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="9504d-119">**Carte réseau 2 (interface externe)**</span><span class="sxs-lookup"><span data-stu-id="9504d-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="9504d-120">Trois adresses IP publiques sont attribuées à cette carte réseau, par exemple 131.107.155.10 pour le service Edge d’accès, 131.107.155.20 pour le service Edge de conférence Web, 131.107.155.30 pour le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="9504d-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9504d-121">Les adresses IP affectées aux interfaces réseau externes réelles du serveur Edge peuvent être tributaires de l’équilibreur de charge matériel que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="9504d-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="9504d-122">Reportez-vous à la documentation de votre équilibreur de charge matérielle pour comprendre l’adresse IP réelle requise.</span><span class="sxs-lookup"><span data-stu-id="9504d-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="9504d-123">Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge.</span><span class="sxs-lookup"><span data-stu-id="9504d-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="9504d-124">Bien que les adresses IP soient enregistrées, les numéros de port doivent être différents pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="9504d-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="9504d-125">Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic.</span><span class="sxs-lookup"><span data-stu-id="9504d-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="9504d-126">La modification des valeurs de port à (par exemple) 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence Web et 443/TCP pour le service Edge A/V pourrait entraîner des problèmes pour les utilisateurs distants où un pare-feu dont ils sont derrière n’autorise pas le trafic sur 5061/TCP et 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="9504d-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="9504d-127">Par ailleurs, l’utilisation de trois adresses IP distinctes facilite le dépannage puisqu’il est possible d’appliquer un filtre selon l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="9504d-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="9504d-128">L’adresse IP du service Edge d’accès est principale avec la passerelle par défaut définie sur le routeur accessible sur Internet (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="9504d-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="9504d-129">Service Edge de conférence Web et adresses IP du service Edge A/V secondaires.</span><span class="sxs-lookup"><span data-stu-id="9504d-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="9504d-130">La configuration du serveur Edge avec deux cartes réseau est l’une des deux options.</span><span class="sxs-lookup"><span data-stu-id="9504d-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="9504d-131">L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="9504d-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="9504d-132">Le principal avantage de cette option est une carte réseau distincte par serveur de serveur Edge et une collecte de données potentiellement plus concise lorsque la résolution des problèmes est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="9504d-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="9504d-133">Enregistrements DNS requis pour le serveur Edge consolidé ajusté, équilibrage de charge matérielle (exemple)</span><span class="sxs-lookup"><span data-stu-id="9504d-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9504d-134">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="9504d-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="9504d-135">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="9504d-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="9504d-136">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="9504d-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="9504d-137">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="9504d-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9504d-138">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="9504d-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9504d-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9504d-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="9504d-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="9504d-141">Interface externe du service Edge d’accès (contoso).</span><span class="sxs-lookup"><span data-stu-id="9504d-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="9504d-142">Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</span><span class="sxs-lookup"><span data-stu-id="9504d-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9504d-143">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="9504d-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9504d-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9504d-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="9504d-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="9504d-146">Interface externe du service Edge de conférence Web</span><span class="sxs-lookup"><span data-stu-id="9504d-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9504d-147">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="9504d-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9504d-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9504d-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="9504d-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="9504d-150">Interface externe du service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="9504d-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9504d-151">DNS externe/SRV/443</span><span class="sxs-lookup"><span data-stu-id="9504d-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="9504d-152">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9504d-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9504d-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-154">Interface externe du service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="9504d-154">Access Edge service external interface.</span></span> <span data-ttu-id="9504d-155">Nécessaire pour que la configuration automatique des clients Lync 2013 et Lync 2010 fonctionne en externe.</span><span class="sxs-lookup"><span data-stu-id="9504d-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="9504d-156">Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="9504d-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9504d-157">DNS externe/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="9504d-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="9504d-158">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="9504d-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9504d-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9504d-160">Interface externe du service Edge d’accès SIP requise pour la découverte DNS automatique des partenaires fédérés connus sous le nom de « domaine SIP autorisé » (appelée fédération étendue dans les versions précédentes).</span><span class="sxs-lookup"><span data-stu-id="9504d-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="9504d-161">Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs de Lync et des clients mobiles Microsoft Lync qui utilisent le service de notifications ou le service de notification poussé Apple.</span><span class="sxs-lookup"><span data-stu-id="9504d-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9504d-162">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="9504d-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="9504d-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9504d-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9504d-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="9504d-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="9504d-165">Interface interne de serveur Edge consolidé</span><span class="sxs-lookup"><span data-stu-id="9504d-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

