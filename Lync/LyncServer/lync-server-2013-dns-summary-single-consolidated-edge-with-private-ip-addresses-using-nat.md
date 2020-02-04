---
title: Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3276219fb4c2227cde75cf9a5d3a47616c03336d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="bee43-102">Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bee43-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bee43-103">_**Dernière modification de la rubrique :** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="bee43-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="bee43-104">Les exigences d’enregistrements DNS pour l’accès distant à Lync Server 2013 sont assez simples comparées à celles des certificats et des ports.</span><span class="sxs-lookup"><span data-stu-id="bee43-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="bee43-105">De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de la possibilité d’activer la Fédération.</span><span class="sxs-lookup"><span data-stu-id="bee43-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="bee43-106">Pour plus d’informations sur les exigences DNS de Lync 2013, voir [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bee43-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="bee43-107">Pour plus d’informations sur la configuration automatique des clients exécutant Lync 2013 si le DNS fractionné-Brain n’est pas configuré, voir « Configuration automatique sans DNS fractionné-Brain » dans [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bee43-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="bee43-108">Le tableau suivant contient un résumé des enregistrements DNS requis pour la prise en charge de la topologie de périphérie unique consolidée illustrée dans la figure unique.</span><span class="sxs-lookup"><span data-stu-id="bee43-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="bee43-109">Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique de clients 2013 et Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="bee43-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="bee43-110">Si vous envisagez d’utiliser des objets de stratégie de groupe pour configurer des clients Lync, les enregistrements de configuration automatique associés ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="bee43-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="bee43-111">IMPORTANT : configuration requise pour les cartes réseau du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="bee43-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="bee43-112">Pour éviter les problèmes de routage, assurez-vous qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur l’adaptateur réseau associé à l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="bee43-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="bee43-113">Par exemple, comme illustré dans la figure de la topologie unique de l’arête consolidée [avec des adresses IP privées et NAT dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), la passerelle par défaut pointe vers le pare-feu externe (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="bee43-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="bee43-114">Vous pouvez configurer deux cartes réseau sur votre serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="bee43-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="bee43-115">**Carte réseau 1 (interface interne)**</span><span class="sxs-lookup"><span data-stu-id="bee43-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="bee43-116">Interface interne avec 172.25.33.10 attribué.</span><span class="sxs-lookup"><span data-stu-id="bee43-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="bee43-117">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="bee43-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="bee43-118">Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne latérale vers tout réseau qui contient des serveurs exécutant Lync Server 2013 ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="bee43-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="bee43-119">**Carte réseau 2 (interface externe)**</span><span class="sxs-lookup"><span data-stu-id="bee43-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="bee43-120">Trois adresses IP privées sont affectées à cette carte réseau (par exemple 10.45.16.10 pour Access Edge, 10.45.16.20 pour les conférences Web, 10.45.16.30 pour les périphériques AV</span><span class="sxs-lookup"><span data-stu-id="bee43-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bee43-121">Il est possible, mais déconseillé, d’utiliser une seule adresse IP pour les trois interfaces de service Edge.</span><span class="sxs-lookup"><span data-stu-id="bee43-121">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="bee43-122">Même si cela enregistre les adresses IP, il est nécessaire de disposer d’un numéro de port différent pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="bee43-122">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="bee43-123">Le numéro de port par défaut est 443/TCP, ce qui permet à la plupart des pare-feu distants d’autoriser le trafic.</span><span class="sxs-lookup"><span data-stu-id="bee43-123">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="bee43-124">Le fait de changer les valeurs de port (par exemple) 5061/TCP pour le Edge d’accès, 444/TCP pour les conférences Web et 443/TCP pour le bord AV peut poser des problèmes pour les utilisateurs distants dans lesquels un pare-feu est derrière n’autorise pas le trafic de 5061/TCP et 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="bee43-124">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="bee43-125">Par ailleurs, trois adresses IP distinctes simplifient la résolution des problèmes en raison de la possibilité de filtrer sur l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="bee43-125">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="bee43-126">L’adresse IP d’Access Edge est principale avec passerelle par défaut configuré sur le routeur intégré (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="bee43-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="bee43-127">Conférences Web et adresses IP A/V secondaires.</span><span class="sxs-lookup"><span data-stu-id="bee43-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="bee43-128">La configuration du serveur Edge avec deux cartes réseau est l’une des deux options suivantes.</span><span class="sxs-lookup"><span data-stu-id="bee43-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="bee43-129">L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bee43-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="bee43-130">Le principal avantage de cette option est une carte réseau distincte par service de serveur Edge et une collection de données plus concise lorsque le dépannage est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="bee43-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="bee43-131">Enregistrements DNS requis pour une seule périphérie consolidée avec des adresses IP privées utilisant la traduction d’adresses réseau (exemple)</span><span class="sxs-lookup"><span data-stu-id="bee43-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bee43-132">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="bee43-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bee43-133">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="bee43-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="bee43-134">IP address/FQDN</span><span class="sxs-lookup"><span data-stu-id="bee43-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="bee43-135">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="bee43-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee43-136">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="bee43-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bee43-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="bee43-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="bee43-139">Accès à l’interface externe d’Access Edge (contoso) si nécessaire pour tous les domaines SIP pour lesquels Lync a activé les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="bee43-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee43-140">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="bee43-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bee43-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="bee43-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="bee43-143">Interface externe de conférence Web</span><span class="sxs-lookup"><span data-stu-id="bee43-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee43-144">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="bee43-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bee43-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="bee43-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="bee43-147">Interface externe A/V Edge</span><span class="sxs-lookup"><span data-stu-id="bee43-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee43-148">DNS/SRV/443 externes</span><span class="sxs-lookup"><span data-stu-id="bee43-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="bee43-149">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-151">Interface externe d’Access Edge.</span><span class="sxs-lookup"><span data-stu-id="bee43-151">Access Edge external interface.</span></span> <span data-ttu-id="bee43-152">Requis pour la configuration automatique de clients 2013 et Lync 2010 pour une utilisation externe.</span><span class="sxs-lookup"><span data-stu-id="bee43-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="bee43-153">Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bee43-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee43-154">DNS/SRV/5061 externes</span><span class="sxs-lookup"><span data-stu-id="bee43-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="bee43-155">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-157">Interface externe de l’accès SIP SIP requise pour la détection automatique de DNS des partenaires fédérés connus sous le nom de « domaine SIP autorisé » (appelé Fédération avancée dans les versions précédentes). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bee43-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee43-158">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="bee43-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bee43-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bee43-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bee43-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="bee43-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="bee43-161">Interface interne consolidée Edge</span><span class="sxs-lookup"><span data-stu-id="bee43-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="bee43-162">Les enregistrements répertoriés dans le tableau précédent sont affichés avec une extension <EM>.net</EM> ou une extension <EM>. com</EM> afin de mettre en évidence la zone dans laquelle ils doivent résider si vous n’utilisez pas le DNS fractionné-Brain.</span><span class="sxs-lookup"><span data-stu-id="bee43-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="bee43-163">Si vous utilisez le système DNS à Split-Brain, tous les enregistrements se trouvent dans la même zone <EM>. com</EM> , à la seule distinction qu’il s’agit de la version de zone DNS interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="bee43-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="bee43-164">Pour plus d’informations, consultez la section « DNS split-brain » dans <A href="lync-server-2013-determine-dns-requirements.md">déterminer les exigences DNS pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bee43-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="bee43-165">Enregistrements requis pour la Fédération</span><span class="sxs-lookup"><span data-stu-id="bee43-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bee43-166">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="bee43-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bee43-167">FQDN</span><span class="sxs-lookup"><span data-stu-id="bee43-167">FQDN</span></span></th>
<th><span data-ttu-id="bee43-168">Enregistrement d’adresse IP/nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="bee43-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="bee43-169">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="bee43-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee43-170">DNS/SRV/5061 externes</span><span class="sxs-lookup"><span data-stu-id="bee43-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="bee43-171">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-173">L’interface externe d’accès SIP SIP doit être requise pour la découverte automatique du DNS de votre Fédération par le biais d’autres partenaires de Fédération potentiels, et est désignée sous le nom de « domaines SIP autorisés » (appelé Fédération avancée dans les versions antérieures). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bee43-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="bee43-174">Cet enregistrement SRV est requis pour la mobilité et le centre de suppression des notifications de transmission</span><span class="sxs-lookup"><span data-stu-id="bee43-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="bee43-175">DNS Summary pour le protocole de messagerie et de présence extensible</span><span class="sxs-lookup"><span data-stu-id="bee43-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bee43-176">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="bee43-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bee43-177">FQDN</span><span class="sxs-lookup"><span data-stu-id="bee43-177">FQDN</span></span></th>
<th><span data-ttu-id="bee43-178">Enregistrement d’adresse IP/nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="bee43-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="bee43-179">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="bee43-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee43-180">DNS externe/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="bee43-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="bee43-181">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bee43-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bee43-183">Interface externe du proxy XMPP du service Edge d’accès ou du pool Edge. Répétez cette opération pour tous les domaines SIP internes avec Lync pour les utilisateurs pour lesquels le contact avec les contacts XMPP est autorisé via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, d’une stratégie de site à l’emplacement de l’utilisateur ou d’une stratégie utilisateur appliquée au Utilisateur compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="bee43-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="bee43-184">Un domaine XMPP autorisé doit également être configuré dans la stratégie partenaires fédérés de XMPP.</span><span class="sxs-lookup"><span data-stu-id="bee43-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="bee43-185">Pour plus d’informations, voir rubriques supplémentaires dans la <strong>section Voir aussi</strong> .</span><span class="sxs-lookup"><span data-stu-id="bee43-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee43-186">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="bee43-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bee43-187">xmpp.contoso.com (par exemple)</span><span class="sxs-lookup"><span data-stu-id="bee43-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="bee43-188">Adresse IP du service Edge d’accès sur votre serveur Edge ou pool d’hébergement de proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="bee43-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="bee43-189">Pointe vers le service Edge d’accès ou le pool Edge qui héberge le service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="bee43-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="bee43-190">En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).</span><span class="sxs-lookup"><span data-stu-id="bee43-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

