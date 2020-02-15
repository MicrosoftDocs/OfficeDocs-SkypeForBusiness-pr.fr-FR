---
title: Résumé des enregistrements DNS-serveur Edge unique consolidé avec adresses IP publiques
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d78bcb5733b2630ad69ebc7686885625ce6ed13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="67f13-102">Résumé des enregistrements DNS-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67f13-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67f13-103">_**Dernière modification de la rubrique :** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="67f13-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="67f13-104">Les exigences liées aux enregistrements DNS pour l’accès à distance à Lync Server 2013 sont relativement simples par rapport à celles des certificats et des ports.</span><span class="sxs-lookup"><span data-stu-id="67f13-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="67f13-105">De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de l’activation de la Fédération.</span><span class="sxs-lookup"><span data-stu-id="67f13-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="67f13-106">Pour plus d’informations sur les exigences DNS de Lync 2013, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67f13-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="67f13-107">Pour plus d’informations sur la configuration automatique des clients exécutant Lync 2013 si le DNS split-brain n’est pas configuré, voir « Configuration automatique sans DNS split-brain » dans [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67f13-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="67f13-108">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée indiquée dans la figure Topologie Edge consolidée unique.</span><span class="sxs-lookup"><span data-stu-id="67f13-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="67f13-109">Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013 et Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="67f13-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="67f13-110">Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements de configuration automatique associés ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="67f13-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="67f13-111">IMPORTANT : configuration requise pour la carte réseau de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="67f13-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="67f13-112">Pour éviter les problèmes de routage, vérifiez qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="67f13-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="67f13-113">Par exemple, comme indiqué dans la topologie de serveur Edge consolidé unique avec des adresses IP publiques, dans serveur [Edge consolidé unique avec adresses IP publiques dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), la passerelle par défaut pointe vers le routeur externe de votre périmètre Internet ou pare-feu qui peut fournir des adresses IP publiques.</span><span class="sxs-lookup"><span data-stu-id="67f13-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="67f13-114">La relation réseau pour les interfaces de serveur Edge est une relation de routage au lieu d’une relation NAT.</span><span class="sxs-lookup"><span data-stu-id="67f13-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="67f13-115">Vous pouvez configurer deux cartes réseau dans votre serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="67f13-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="67f13-116">**Carte réseau 1 (interface interne)**</span><span class="sxs-lookup"><span data-stu-id="67f13-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="67f13-117">Interface interne avec 172.25.33.10 affecté.</span><span class="sxs-lookup"><span data-stu-id="67f13-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="67f13-118">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="67f13-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="67f13-119">Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="67f13-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="67f13-120">**Carte réseau 2 (interface externe)**</span><span class="sxs-lookup"><span data-stu-id="67f13-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="67f13-121">Trois adresses IP publiques sont assignées à cette carte réseau, par exemple 131.107.155.10 pour le serveur Edge d’accès, 131.107.155.20 pour le serveur Edge de conférence web, 131.107.155.30 pour le serveur Edge AV.</span><span class="sxs-lookup"><span data-stu-id="67f13-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="67f13-p104">Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Bien que les adresses IP soient enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. Le fait d’affecter aux ports les valeurs 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V, par exemple, peut générer des problèmes pour les utilisateurs distants se trouvant derrière un pare-feu qui n’autorise pas le trafic sur 5061/TCP et 444/TCP. Par ailleurs, l’utilisation de trois adresses IP distinctes facilite le dépannage puisqu’il est possible d’appliquer un filtre selon l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="67f13-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="67f13-127">L’adresse IP publique des serveurs Edge d’accès avec la passerelle par défaut définie sur le routeur public (131.107.155.1) est l’adresse principale.</span><span class="sxs-lookup"><span data-stu-id="67f13-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="67f13-128">Les adresses IP publiques des serveurs de conférence web et Edge A/V sont des adresses IP supplémentaires dans la section **Avancé** des propriétés **Protocole Internet version 4 (TCP/IPv4)** et **Protocole Internet version 6 (TCP/IPv6)** des **Propriétés de la connexion au réseau local** dans Windows Server.</span><span class="sxs-lookup"><span data-stu-id="67f13-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="67f13-129">La configuration du serveur Edge avec deux cartes réseau est l’une des deux options.</span><span class="sxs-lookup"><span data-stu-id="67f13-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="67f13-130">L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="67f13-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="67f13-131">Le principal avantage de cette option est une carte réseau distincte par serveur de serveur Edge et une collecte de données potentiellement plus concise lorsque la résolution des problèmes est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="67f13-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="67f13-132">Enregistrements DNS requis pour un serveur Edge consolidé unique avec des adresses IP publiques (Exemple)</span><span class="sxs-lookup"><span data-stu-id="67f13-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67f13-133">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="67f13-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="67f13-134">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="67f13-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="67f13-135">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="67f13-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="67f13-136">Mappe vers/Commentaires</span><span class="sxs-lookup"><span data-stu-id="67f13-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67f13-137">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="67f13-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="67f13-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="67f13-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="67f13-140">Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="67f13-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f13-141">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="67f13-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="67f13-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="67f13-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="67f13-144">Interface externe de serveur Edge de conférence web</span><span class="sxs-lookup"><span data-stu-id="67f13-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f13-145">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="67f13-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="67f13-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="67f13-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="67f13-148">Interface externe de serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="67f13-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f13-149">DNS externe/SRV/443</span><span class="sxs-lookup"><span data-stu-id="67f13-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="67f13-150">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="67f13-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-152">Interface externe du serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="67f13-152">Access Edge external interface.</span></span> <span data-ttu-id="67f13-153">Nécessaire pour que la configuration automatique des clients Lync 2013 et Lync 2010 fonctionne en externe.</span><span class="sxs-lookup"><span data-stu-id="67f13-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="67f13-154">Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="67f13-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f13-155">DNS externe/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="67f13-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="67f13-156">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="67f13-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-158">Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique des partenaires fédérés, connue sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="67f13-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f13-159">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="67f13-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="67f13-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="67f13-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="67f13-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="67f13-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="67f13-162">Interface interne de serveur Edge consolidé</span><span class="sxs-lookup"><span data-stu-id="67f13-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="67f13-163">Les enregistrements répertoriés dans le tableau précédent sont indiqués avec une extension <EM>.net</EM> ou une extension <EM>.com</EM> pour mettre en avant la zone dans laquelle ils doivent résider si vous n’utilisez pas une configuration DNS split-brain.</span><span class="sxs-lookup"><span data-stu-id="67f13-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="67f13-164">Si vous utilisez une configuration DNS split-brain, tous les enregistrements seraient dans la même zone, leur version, interne ou externe, permettant de les distinguer.</span><span class="sxs-lookup"><span data-stu-id="67f13-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="67f13-165">Pour plus d’informations, voir « split-brain DNS » dans <A href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="67f13-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="67f13-166">Enregistrements requis pour la fédération</span><span class="sxs-lookup"><span data-stu-id="67f13-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67f13-167">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="67f13-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="67f13-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="67f13-168">FQDN</span></span></th>
<th><span data-ttu-id="67f13-169">Adresse IP/Enregistrement d’hôte FQDN</span><span class="sxs-lookup"><span data-stu-id="67f13-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="67f13-170">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="67f13-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67f13-171">DNS externe /SRV/5061</span><span class="sxs-lookup"><span data-stu-id="67f13-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="67f13-172">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="67f13-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-174">Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique de votre fédération par d’autres partenaires de fédération potentiels, elle est aussi connue sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</span><span class="sxs-lookup"><span data-stu-id="67f13-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="67f13-175">Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push.</span><span class="sxs-lookup"><span data-stu-id="67f13-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="67f13-176">Résumé DNS pour le protocole XMPP</span><span class="sxs-lookup"><span data-stu-id="67f13-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67f13-177">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="67f13-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="67f13-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="67f13-178">FQDN</span></span></th>
<th><span data-ttu-id="67f13-179">Adresse IP/Enregistrement d’hôte FQDN</span><span class="sxs-lookup"><span data-stu-id="67f13-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="67f13-180">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="67f13-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67f13-181">DNS externe/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="67f13-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="67f13-182">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="67f13-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67f13-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="67f13-184">Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération si nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée au Utilisateur à extension Lync.</span><span class="sxs-lookup"><span data-stu-id="67f13-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="67f13-185">Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP.</span><span class="sxs-lookup"><span data-stu-id="67f13-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="67f13-186">Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</span><span class="sxs-lookup"><span data-stu-id="67f13-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f13-187">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="67f13-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="67f13-188">xmpp.contoso.com (par exemple)</span><span class="sxs-lookup"><span data-stu-id="67f13-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="67f13-189">Adresse IP du service Edge d’accès sur votre serveur Edge ou le pool de serveurs Edge qui héberge le proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="67f13-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="67f13-190">Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="67f13-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="67f13-191">En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</span><span class="sxs-lookup"><span data-stu-id="67f13-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

