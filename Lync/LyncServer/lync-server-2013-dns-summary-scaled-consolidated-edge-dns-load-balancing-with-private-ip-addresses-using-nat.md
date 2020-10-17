---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la traduction d’adresses réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 269d5a687baba53ed0bd60d4854b79643f23f0e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532121"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="70462-102">Résumé DNS-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70462-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70462-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="70462-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="70462-104">Les exigences liées aux enregistrements DNS pour l’accès à distance à Lync Server 2013 sont relativement simples par rapport à celles des certificats et des ports.</span><span class="sxs-lookup"><span data-stu-id="70462-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="70462-105">De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de l’activation de la Fédération.</span><span class="sxs-lookup"><span data-stu-id="70462-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="70462-106">Pour plus d’informations sur les exigences DNS de Lync 2013, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70462-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="70462-107">Pour plus d’informations sur la configuration automatique des clients Lync 2013 si le DNS split-brain n’est pas configuré, consultez la section « Configuration automatique sans DNS split brain » dans [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70462-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="70462-108">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée indiquée dans la figure Topologie Edge consolidée unique.</span><span class="sxs-lookup"><span data-stu-id="70462-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="70462-109">Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="70462-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="70462-110">Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="70462-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="70462-111">IMPORTANT : configuration requise pour la carte réseau de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="70462-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="70462-112">Pour éviter les problèmes de routage, vérifiez qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="70462-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="70462-113">Par exemple, comme illustré dans la figure du scénario de serveur Edge consolidé ajusté dans le [serveur Edge consolidé ajusté, l’équilibrage de charge DNS avec des adresses IP privées utilisant la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), la passerelle par défaut pointerait vers le pare-feu externe.</span><span class="sxs-lookup"><span data-stu-id="70462-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="70462-114">Vous pouvez configurer deux cartes réseau dans chacun de vos serveurs Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="70462-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="70462-115">**Carte réseau 1 - nœud 1 (interface interne)**</span><span class="sxs-lookup"><span data-stu-id="70462-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="70462-116">Interface interne avec 172.25.33.10 affecté.</span><span class="sxs-lookup"><span data-stu-id="70462-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="70462-117">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="70462-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="70462-118">Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="70462-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="70462-119">**Carte réseau 1 - nœud 2 (interface interne)**</span><span class="sxs-lookup"><span data-stu-id="70462-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="70462-120">Interface interne avec 172.25.33.11 affecté.</span><span class="sxs-lookup"><span data-stu-id="70462-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="70462-121">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="70462-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="70462-122">Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="70462-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="70462-123">**Carte réseau 2 - nœud 1 (interface externe)**</span><span class="sxs-lookup"><span data-stu-id="70462-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="70462-124">Trois adresses IP privées sont attribuées à cette carte réseau, par exemple 10.45.16.10 pour le serveur Edge d’accès, 10.45.16.20 pour la conférence Web, et 10.45.16.30 pour le serveur Edge AV.</span><span class="sxs-lookup"><span data-stu-id="70462-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="70462-p104">Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Bien que les adresses IP soient enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. Le fait d’affecter aux ports les valeurs 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V, par exemple, peut générer des problèmes pour les utilisateurs distants se trouvant derrière un pare-feu qui n’autorise pas le trafic sur 5061/TCP et 444/TCP. Par ailleurs, l’utilisation de trois adresses IP distinctes facilite le dépannage puisqu’il est possible d’appliquer un filtre selon l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="70462-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="70462-130">L’adresse IP publique du serveur Edge d’accès est principale avec la passerelle par défaut définie sur le routeur intégré (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="70462-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="70462-131">Les adresses IP privées de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés du **protocole Internet version 4 (TCP/IPv4)** et du **protocole Internet version 6 (TCP/IPv6)** des **Propriétés de connexion au réseau local** dans Windows Server.</span><span class="sxs-lookup"><span data-stu-id="70462-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="70462-132">**Carte réseau 2 - nœud 2 (interface externe)**</span><span class="sxs-lookup"><span data-stu-id="70462-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="70462-133">Trois adresses IP privées sont attribuées à cette carte réseau, par exemple 10.45.16.11 pour le serveur Edge d’accès, 10.45.16.21 pour la conférence Web, 10.45.16.31 pour le serveur Edge AV.</span><span class="sxs-lookup"><span data-stu-id="70462-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="70462-134">L’adresse IP publique du serveur Edge d’accès est principale avec la passerelle par défaut définie sur le routeur intégré (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="70462-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="70462-135">Les adresses IP privées de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés du **protocole Internet version 4 (TCP/IPv4)** et du **protocole Internet version 6 (TCP/IPv6)** des **Propriétés de connexion au réseau local** dans Windows Server.</span><span class="sxs-lookup"><span data-stu-id="70462-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="70462-136">La configuration du serveur Edge avec deux cartes réseau est l’une des deux options.</span><span class="sxs-lookup"><span data-stu-id="70462-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="70462-137">L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="70462-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="70462-138">Le principal avantage de cette option est une carte réseau distincte par serveur de serveur Edge et une collecte de données potentiellement plus concise lorsque la résolution des problèmes est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="70462-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="70462-139">Enregistrements DNS requis pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de l’interface NAT (exemple)</span><span class="sxs-lookup"><span data-stu-id="70462-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70462-140">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="70462-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="70462-141">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="70462-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="70462-142">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="70462-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="70462-143">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="70462-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70462-144">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="70462-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70462-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-146">131.107.155.10 et 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="70462-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="70462-147">Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="70462-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70462-148">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="70462-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70462-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-150">131.107.155.20 et 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="70462-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="70462-151">Interface externe de serveur Edge de conférence web</span><span class="sxs-lookup"><span data-stu-id="70462-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70462-152">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="70462-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70462-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-154">131.107.155.30 et 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="70462-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="70462-155">Interface externe de serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="70462-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70462-156">DNS externe/SRV/443</span><span class="sxs-lookup"><span data-stu-id="70462-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="70462-157">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="70462-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-159">Interface externe du serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="70462-159">Access Edge external interface.</span></span> <span data-ttu-id="70462-160">Nécessaire pour que la configuration automatique des clients Lync 2013 et Lync 2010 fonctionne en externe.</span><span class="sxs-lookup"><span data-stu-id="70462-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="70462-161">Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="70462-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70462-162">DNS externe/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="70462-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="70462-163">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="70462-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-165">Interface externe du serveur Edge d’accès SIP.</span><span class="sxs-lookup"><span data-stu-id="70462-165">SIP Access Edge external interface.</span></span> <span data-ttu-id="70462-166">Obligatoire pour la découverte DNS automatique des partenaires fédérés connus sous le nom de « domaine SIP autorisé » (appelé fédération étendue dans les versions précédentes).</span><span class="sxs-lookup"><span data-stu-id="70462-166">Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="70462-167">Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</span><span class="sxs-lookup"><span data-stu-id="70462-167">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70462-168">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="70462-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70462-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="70462-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="70462-170">172.25.33.10 et 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="70462-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="70462-171">Interface interne de serveur Edge consolidé</span><span class="sxs-lookup"><span data-stu-id="70462-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="70462-172">Enregistrements requis pour la fédération</span><span class="sxs-lookup"><span data-stu-id="70462-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70462-173">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="70462-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="70462-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="70462-174">FQDN</span></span></th>
<th><span data-ttu-id="70462-175">Adresse IP/Enregistrement d’hôte FQDN</span><span class="sxs-lookup"><span data-stu-id="70462-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="70462-176">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="70462-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70462-177">DNS externe/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="70462-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="70462-178">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="70462-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-180">Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique de votre fédération par d’autres partenaires de fédération potentiels, elle est aussi connue sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="70462-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="70462-181">Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push.</span><span class="sxs-lookup"><span data-stu-id="70462-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="70462-182">Résumé DNS : connectivité de la messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="70462-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70462-183">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="70462-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="70462-184">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="70462-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="70462-185">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="70462-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="70462-186">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="70462-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70462-187">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="70462-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70462-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-189">Interface du service Edge d’accès</span><span class="sxs-lookup"><span data-stu-id="70462-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="70462-190">Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="70462-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="70462-191">Résumé DNS pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="70462-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70462-192">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="70462-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="70462-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="70462-193">FQDN</span></span></th>
<th><span data-ttu-id="70462-194">Adresse IP/Enregistrement d’hôte FQDN</span><span class="sxs-lookup"><span data-stu-id="70462-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="70462-195">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="70462-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70462-196">DNS externe/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="70462-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="70462-197">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="70462-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70462-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70462-199">Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération autant que nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés dans la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée à l’utilisateur à extension Lync.</span><span class="sxs-lookup"><span data-stu-id="70462-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="70462-200">Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP.</span><span class="sxs-lookup"><span data-stu-id="70462-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="70462-201">Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</span><span class="sxs-lookup"><span data-stu-id="70462-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70462-202">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="70462-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70462-203">xmpp.contoso.com (par exemple)</span><span class="sxs-lookup"><span data-stu-id="70462-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="70462-204">Adresse IP du service Edge d’accès sur votre serveur Edge ou le pool de serveurs Edge qui héberge le proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="70462-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="70462-205">Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="70462-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="70462-206">En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</span><span class="sxs-lookup"><span data-stu-id="70462-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

