---
title: 'Lync Server 2013 : déterminer les exigences DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79f1c27f48beddd0c1fd3260193a71bb79b034bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="0822d-102">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0822d-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0822d-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0822d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0822d-104">Utilisez l’organigramme suivant pour déterminer les enregistrements DNS requis.</span><span class="sxs-lookup"><span data-stu-id="0822d-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="0822d-105">Les modifications apportées aux mises à jour cumulatives pour Lync Server 2013 : février 2013 sont indiquées à l’endroit où elles s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="0822d-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0822d-106">Microsoft Lync Server 2013 prend en charge l’utilisation de l’adressage IPv6.</span><span class="sxs-lookup"><span data-stu-id="0822d-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="0822d-107">Pour utiliser les adresses IPv6, vous devez également fournir la prise en charge du DNS IPv6 et configurer les enregistrements d’hôte DNS AAAA (appelés « Quad-A »).</span><span class="sxs-lookup"><span data-stu-id="0822d-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="0822d-108">Dans les déploiements où les protocoles IPv4 et IPv6 sont utilisés, il est préférable de configurer et de gérer à la fois les enregistrements d’hôte A pour IPv4 et l’hôte AAAA pour IPv6.</span><span class="sxs-lookup"><span data-stu-id="0822d-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="0822d-109">Même si votre déploiement a été intégralement transféré vers IPv6, les enregistrements d’hôte DNS IPv4 peuvent toujours être requis lorsque des utilisateurs externes continuent à utiliser IPv4.</span><span class="sxs-lookup"><span data-stu-id="0822d-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="0822d-110">**Détermination de l’organigramme des enregistrements DNS requis**</span><span class="sxs-lookup"><span data-stu-id="0822d-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="0822d-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="0822d-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0822d-112">Par défaut, le nom d’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="0822d-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="0822d-113">Le générateur de topologie utilise des noms de domaine complets, pas des noms d’hôte.</span><span class="sxs-lookup"><span data-stu-id="0822d-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="0822d-114">Par conséquent, vous devez configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non membre d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="0822d-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="0822d-115"><STRONG>Utilisez uniquement des caractères standard</STRONG> (A–Z, a–z, 0–9 et tirets) lorsque vous assignez des noms de domaines complets à vos serveurs Lync, serveurs Edge et pools.</span><span class="sxs-lookup"><span data-stu-id="0822d-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="0822d-116">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="0822d-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="0822d-117">Les caractères non standard dans les noms de domaines complets ne sont généralement pas pris en charge par les DNS externes et les autorités publiques de certification (c’est-à-dire lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat).</span><span class="sxs-lookup"><span data-stu-id="0822d-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="0822d-118">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-dns-host-records.md">configurer des enregistrements d’hôte DNS pour Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="0822d-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="0822d-119">Comment les clients Lync localisent les services</span><span class="sxs-lookup"><span data-stu-id="0822d-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="0822d-120">Microsoft Lync 2010, Lync 2013 et Lync mobile sont similaires dans la façon dont le client trouve et accède aux services dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0822d-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="0822d-121">L’exception notable est l’application Lync Windows Store qui utilise un processus d’emplacement de service différent.</span><span class="sxs-lookup"><span data-stu-id="0822d-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="0822d-122">Cette section décrit deux scénarios de localisation des services par les clients, la méthode traditionnelle qui utilise une série d’enregistrements d’hôte SRV et A, ainsi que les enregistrements du service de découverte automatique uniquement.</span><span class="sxs-lookup"><span data-stu-id="0822d-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="0822d-123">Les mises à jour cumulatives des clients de bureau modifient le processus d’emplacement DNS à partir de Lync Server 2010 pour tous les clients, le processus de requête DNS continue jusqu’à ce qu’une requête réussie soit renvoyée, ou la liste des enregistrements DNS possibles soit épuisée, et la dernière erreur est renvoyée à le client.</span><span class="sxs-lookup"><span data-stu-id="0822d-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="0822d-124">Pour tous les clients **à l’exception** de l’application Lync Windows Store pendant la recherche DNS, les enregistrements SRV sont interrogés et renvoyés au client dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="0822d-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="0822d-125">lyncdiscoverinternal. \<enregistrement\> de domaine A (hôte) pour le service de découverte automatique sur les services Web internes</span><span class="sxs-lookup"><span data-stu-id="0822d-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="0822d-126">lyncdiscover. \<enregistrement\> de domaine A (hôte) pour le service de découverte automatique sur les services Web externes</span><span class="sxs-lookup"><span data-stu-id="0822d-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="0822d-127">\_sipinternaltls. \_TCP. \<enregistrement\> de domaine SRV (Localisateur de service) pour les connexions TLS internes</span><span class="sxs-lookup"><span data-stu-id="0822d-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="0822d-128">\_sipinternal. \_TCP. \<enregistrement\> de domaine SRV (Localisateur de service) pour les connexions TCP internes (effectué uniquement si TCP est autorisé)</span><span class="sxs-lookup"><span data-stu-id="0822d-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="0822d-129">\_SIP. \_TLS. \<enregistrement\> de domaine SRV (Localisateur de service) pour les connexions TLS externes</span><span class="sxs-lookup"><span data-stu-id="0822d-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="0822d-130">sipinternal. \<enregistrement\> de domaine A (hôte) pour le pool frontal ou le directeur, pouvant être résolu uniquement sur le réseau interne</span><span class="sxs-lookup"><span data-stu-id="0822d-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="0822d-131">SIP. \<enregistrement\> de domaine A (hôte) pour le pool frontal ou le directeur sur le réseau interne, ou le service Edge d’accès lorsque le client est externe</span><span class="sxs-lookup"><span data-stu-id="0822d-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="0822d-132">sipexternal. \<enregistrement\> de domaine A (hôte) pour le service Edge d’accès lorsque le client est externe</span><span class="sxs-lookup"><span data-stu-id="0822d-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="0822d-133">L’application Lync Windows Store modifie complètement le processus, car il utilise deux enregistrements :</span><span class="sxs-lookup"><span data-stu-id="0822d-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="0822d-134">lyncdiscoverinternal. \<enregistrement\> de domaine A (hôte) pour le service de découverte automatique sur les services Web internes</span><span class="sxs-lookup"><span data-stu-id="0822d-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="0822d-135">lyncdiscover. \<enregistrement\> de domaine A (hôte) pour le service de découverte automatique sur les services Web externes</span><span class="sxs-lookup"><span data-stu-id="0822d-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="0822d-136">Il n’y a pas de secours pour les autres types d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="0822d-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="0822d-137">La différence entre les méthodes utilisées pour les clients plus récents et les clients plus anciens est que le service de découverte automatique devient la méthode préférée pour rechercher tous les services.</span><span class="sxs-lookup"><span data-stu-id="0822d-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="0822d-138">Lorsqu’une connexion réussit, le service de découverte automatique renvoie toutes les URL des services Web pour le pool d’accueil de l’utilisateur, y compris le service de mobilité (appelé MCX par le répertoire virtuel créé pour le service dans les services Internet (IIS), Microsoft Lync Web App et les URL du planificateur Web.</span><span class="sxs-lookup"><span data-stu-id="0822d-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="0822d-139">Toutefois, l'URL du Service Mobilité interne et l'URL du Service Mobilité externe sont associées au nom de domaine complet des services web externes.</span><span class="sxs-lookup"><span data-stu-id="0822d-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="0822d-140">Par conséquent, qu’il soit interne ou externe au réseau, un appareil mobile se connecte toujours au service de mobilité de manière externe, par le biais du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="0822d-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="0822d-141">Si les mises à jour cumulatives pour Lync Server 2013 : février 2013 ont été installées, le service de découverte automatique renvoie également des références à Internal/UCWA, External/UCWA et UCWA.</span><span class="sxs-lookup"><span data-stu-id="0822d-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="0822d-142">Ces entrées font référence au composant web de l'API web Unified Communications (UCWA).</span><span class="sxs-lookup"><span data-stu-id="0822d-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="0822d-143">Actuellement, seule l’entrée UCWA est utilisée et fournit une référence à une URL pour le composant Web.</span><span class="sxs-lookup"><span data-stu-id="0822d-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="0822d-144">UCWA est utilisé par les clients mobiles Lync 2013 au lieu du service de mobilité MCX utilisé par les clients mobiles Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0822d-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0822d-145">Lors de la création d’enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un enregistrement DNS A et AAAA (si vous utilisez l’adressage IPv6) dans le même domaine que celui dans lequel l’enregistrement DNS SRV est créé.</span><span class="sxs-lookup"><span data-stu-id="0822d-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="0822d-146">Par exemple, si l’enregistrement SRV se trouve dans contoso.com, l’enregistrement A et AAAA (si vous utilisez l’adressage IPv6) sur lequel pointe vers ne peut pas être dans fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="0822d-147">La configuration par défaut consiste à diriger tout le trafic client mobile via le site externe.</span><span class="sxs-lookup"><span data-stu-id="0822d-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="0822d-148">Vous pouvez modifier les paramètres pour qu’ils ne renvoient que l’URL interne, si cela est plus préférable pour vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0822d-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="0822d-149">Dans cette configuration, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’ils se trouvent sur le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="0822d-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="0822d-150">Pour définir cette configuration, vous utilisez la cmdlet <STRONG>Set-CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0822d-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0822d-151">Bien que les applications mobiles puissent également se connecter à d’autres services Lync Server 2013, tels que le service de carnet d’adresses, les demandes Web d’applications mobiles internes sont dirigées vers le nom de domaine complet Web externe uniquement pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="0822d-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="0822d-152">Cette configuration n’est pas nécessaire pour les autres demandes de services, telles que les demandes de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0822d-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="0822d-153">Les appareils mobiles prennent en charge la découverte manuelle des services.</span><span class="sxs-lookup"><span data-stu-id="0822d-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="0822d-154">Dans ce cas, chaque utilisateur doit configurer les paramètres de l’appareil mobile avec les URI complètes interne et externe du service de découverte automatique, y compris le protocole et le chemin d’accès, comme suit :</span><span class="sxs-lookup"><span data-stu-id="0822d-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="0822d-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root pour l’accès externe</span><span class="sxs-lookup"><span data-stu-id="0822d-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="0822d-156">https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root pour l’accès interne</span><span class="sxs-lookup"><span data-stu-id="0822d-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="0822d-157">Nous vous recommandons d’utiliser la découverte automatique au lieu de la découverte manuelle.</span><span class="sxs-lookup"><span data-stu-id="0822d-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="0822d-158">Toutefois, les paramètres manuels peuvent être utiles pour résoudre les problèmes de connectivité des appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="0822d-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="0822d-159">Configuration du DNS split-brain avec Lync Server</span><span class="sxs-lookup"><span data-stu-id="0822d-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="0822d-160">Le DNS split-brain est connu sous la dénomination d’un certain nombre de noms, par exemple, Split DNS ou Split-horizon DNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="0822d-161">En fait, il décrit une configuration DNS dans laquelle il existe deux zones DNS avec le même espace de noms, mais une seule requête de services de zone DNS en interne uniquement et les autres requêtes externes aux services de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="0822d-162">Toutefois, de nombreux enregistrements DNS (SRV et A) contenus dans le DNS interne ne seront pas contenus dans le DNS externe, et inversement.</span><span class="sxs-lookup"><span data-stu-id="0822d-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="0822d-163">Dans les cas où le même enregistrement DNS existe à la fois dans le DNS interne et dans le DNS externe (par exemple, www.contoso.com), l’adresse IP renvoyée sera différente selon l’emplacement (interne ou externe) de la requête.</span><span class="sxs-lookup"><span data-stu-id="0822d-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0822d-164">Actuellement, le DNS split-brain n’est pas pris en charge pour la mobilité, ou plus spécifiquement, les enregistrements DNS LyncDiscover et LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="0822d-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="0822d-165">LyncDiscover doit être défini sur un serveur DNS externe et LyncDiscoverInternal doit être défini sur un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="0822d-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="0822d-166">Pour les besoins de ces rubriques, le terme DNS split-brain est utilisé.</span><span class="sxs-lookup"><span data-stu-id="0822d-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="0822d-167">Si vous configurez DNS split-brain, les zones interne et externe suivantes contiennent un résumé des types d’enregistrements DNS requis dans chaque zone.</span><span class="sxs-lookup"><span data-stu-id="0822d-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="0822d-168">Pour plus d’informations, reportez-vous à [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0822d-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="0822d-169">**DNS interne :**</span><span class="sxs-lookup"><span data-stu-id="0822d-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="0822d-170">contient une zone DNS appelée contoso.com pour laquelle il fait autorité</span><span class="sxs-lookup"><span data-stu-id="0822d-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="0822d-171">La zone interne contoso.com contient :</span><span class="sxs-lookup"><span data-stu-id="0822d-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="0822d-172">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour la configuration automatique du client Lync Server 2013 interne (facultatif)</span><span class="sxs-lookup"><span data-stu-id="0822d-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="0822d-173">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAMe pour la découverte automatique des services Web Lync Server 2013 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="0822d-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="0822d-174">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour le nom du pool frontal, le nom du pool directeur ou du pool Directeur, ainsi que tous les serveurs internes exécutant Lync Server 2013 dans le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="0822d-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="0822d-175">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne du serveur Edge de chaque Lync Server 2013, serveur Edge dans le réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="0822d-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="0822d-176">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse dans le réseau de périmètre (facultatif pour la gestion des proxys inverses)</span><span class="sxs-lookup"><span data-stu-id="0822d-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="0822d-177">Toutes les interfaces Edge internes du serveur Edge Lync Server 2013 dans le réseau de périmètre utilisent la zone DNS interne pour résoudre les requêtes vers contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="0822d-178">Tous les serveurs exécutant Lync Server 2013 et les clients exécutant Lync 2013 dans le réseau d’entreprise pointent vers les serveurs DNS internes pour résoudre les requêtes vers contoso.com ou utiliser le fichier HOSTs sur chaque serveur Edge et les enregistrements de liste A et AAAA (si vous utilisez l’adressage IPv6) pour serveur du tronçon suivant, en particulier le VIP directeur ou directeur, le VIP de pool frontal ou le serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0822d-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="0822d-179">**DNS externe :**</span><span class="sxs-lookup"><span data-stu-id="0822d-179">**External DNS:**</span></span>

  - <span data-ttu-id="0822d-180">contient une zone DNS appelée contoso.com pour laquelle il fait autorité</span><span class="sxs-lookup"><span data-stu-id="0822d-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="0822d-181">La zone externe contoso.com contient :</span><span class="sxs-lookup"><span data-stu-id="0822d-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="0822d-182">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour la configuration automatique du client Lync Server 2013 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="0822d-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="0822d-183">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) ou CNAMe pour la découverte automatique des services Web Lync Server 2013 pour une utilisation avec la mobilité</span><span class="sxs-lookup"><span data-stu-id="0822d-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="0822d-184">Les enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) et SRV pour l’interface externe de serveur Edge de chaque Lync Server 2013, serveur Edge ou adresse IP virtuelle du programme d’équilibrage de la charge matérielle dans le réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="0822d-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="0822d-185">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface externe du serveur proxy inverse ou de l’adresse IP virtuelle pour un pool de serveurs proxy inverses dans le réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="0822d-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="0822d-186">Configuration automatique sans DNS split-brain</span><span class="sxs-lookup"><span data-stu-id="0822d-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="0822d-187">À l’aide du DNS split-brain, un utilisateur de Lync Server 2013 qui se connecte en interne peut tirer parti de la configuration automatique si \_la zone DNS interne contient un sipinternaltls. \_enregistrement TCP SRV pour chaque domaine SIP utilisé.</span><span class="sxs-lookup"><span data-stu-id="0822d-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="0822d-188">Toutefois, si vous n’utilisez pas le DNS split-brain, la configuration interne automatique des clients exécutant Lync ne fonctionnera pas, sauf si l’une des solutions de contournement décrites plus loin dans cette section est implémentée.</span><span class="sxs-lookup"><span data-stu-id="0822d-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="0822d-189">En effet, Lync Server 2013 nécessite l’URI SIP de l’utilisateur pour correspondre au domaine du pool frontal désigné pour la configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="0822d-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="0822d-190">Cela était également le cas avec les versions antérieures de Communicator.</span><span class="sxs-lookup"><span data-stu-id="0822d-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="0822d-191">Si par exemple vous avez deux domaines SIP utilisés, les enregistrements DNS SRV suivants seront nécessaires :</span><span class="sxs-lookup"><span data-stu-id="0822d-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="0822d-192">Si un utilisateur se connecte en tant que bob@contoso.com l’enregistrement SRV suivant fonctionnera pour la configuration automatique, car le domaine SIP de l’utilisateur (contoso.com) correspond au domaine du pool frontal de configuration automatique) :</span><span class="sxs-lookup"><span data-stu-id="0822d-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="0822d-193">\_sipinternaltls. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="0822d-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="0822d-195">Si un utilisateur se connecte en tant que alice@fabrikam.com, l’enregistrement DNS SRV suivant fonctionnera pour la configuration automatique du deuxième domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="0822d-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="0822d-196">\_sipinternaltls. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="0822d-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0822d-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="0822d-198">À titre de comparaison, si un utilisateur se connecte en tant que tim@litwareinc.com, l’enregistrement DNS SRV suivant ne fonctionne pas pour la configuration automatique, car le domaine SIP du client (litwareinc.com) ne correspond pas au domaine dans lequel se trouve le pool (fabrikam.com) :</span><span class="sxs-lookup"><span data-stu-id="0822d-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="0822d-199">\_sipinternaltls. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="0822d-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0822d-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="0822d-201">Si la configuration automatique est requise pour les clients exécutant Lync, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0822d-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="0822d-202">**Les objets**   de stratégie de groupe utilisent des objets de stratégie de groupe pour renseigner les valeurs de serveur correctes.</span><span class="sxs-lookup"><span data-stu-id="0822d-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0822d-203">Cette option n’active pas la configuration automatique, mais automatise le processus de configuration manuelle. Par conséquent, en suivant cette approche, les enregistrements SRV associés à la configuration automatique ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="0822d-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="0822d-204">**La zone**   interne correspondante permet de créer une zone dans le DNS interne correspondant à la zone DNS externe (par exemple, contoso.com) et de créer des enregistrements DNS a et aaaa (si vous utilisez l’adressage IPv6) correspondant au pool Lync Server 2013 utilisé pour la configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="0822d-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="0822d-205">Par exemple, si un utilisateur est hébergé sur pool01.contoso.net, mais qu’il se connecte à Lync en tant que bob@contoso.com, créez une zone DNS interne appelée contoso.com et à l’intérieur de celle-ci, créez un enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="0822d-206">**Zone de code interne**   si vous créez une zone entière dans le DNS interne n’est pas une option, vous pouvez créer des zones de code confidentiel (dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique et remplir ces zones à l’aide de dnscmd. exe.</span><span class="sxs-lookup"><span data-stu-id="0822d-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="0822d-207">Dnscmd.exe est obligatoire car l’interface utilisateur DNS ne prend pas en charge la création de zones repère.</span><span class="sxs-lookup"><span data-stu-id="0822d-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="0822d-208">Par exemple, si le domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 contenant deux serveurs frontaux, vous avez besoin des zones repère en enregistrements A suivants dans votre DNS interne :</span><span class="sxs-lookup"><span data-stu-id="0822d-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="0822d-209">Si votre environnement contient un deuxième domaine SIP (par exemple, fabrikam.com), vous avez besoin des zones repère et des enregistrements A suivants dans votre DNS interne :</span><span class="sxs-lookup"><span data-stu-id="0822d-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="0822d-p121">Le nom de domaine complet du pool frontal apparaît deux fois, mais avec deux adresses IP différentes. Cela est dû à l’utilisation de l’équilibrage de la charge DNS, mais si l’équilibrage de la charge matérielle était utilisé, il n’y aurait qu’une seule entrée de pool frontal. De même, les valeurs du nom de domaine complet du pool frontal entre l’exemple contoso.com et l’exemple fabrikam.com changent, mais les adresses IP sont conservées. La raison est que les utilisateurs qui se connectent à partir de l’un de ces domaines IP utilisent le même pool frontal pour la configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="0822d-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="0822d-214">Pour plus d’informations, reportez-vous à l’article du blog DMTF, « Communicator Automatic Configuration and [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)split-brain DNS », à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0822d-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0822d-215">Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.</span><span class="sxs-lookup"><span data-stu-id="0822d-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="0822d-216">Configuration du DNS (Domain Name System) pour la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="0822d-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="0822d-217">Pour configurer le DNS de façon à rediriger le trafic Web Lync Server 2013 vers vos sites de récupération d’urgence et de basculement, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="0822d-218">Vous pouvez configurer vos enregistrements DNS pour que le Web prenne en charge la récupération d’urgence, de sorte que les fonctionnalités qui utilisent les services Web se poursuivent même si un pool frontal complet tombe en panne.</span><span class="sxs-lookup"><span data-stu-id="0822d-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="0822d-219">Cette fonctionnalité de récupération d’urgence prend en charge la découverte automatique (URL Lyncdiscover), la réunion et les URL simples de numérotation.</span><span class="sxs-lookup"><span data-stu-id="0822d-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="0822d-220">Vous définissez et configurez des enregistrements hôtes DNS (A et AAAA en cas d’utilisation d’IPv6) supplémentaires pour la résolution interne et externe des services Web au niveau de votre fournisseur GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="0822d-221">Les détails suivants supposent que les pools couplés, géographiquement dispersés et GeoDNS pris en charge par votre fournisseur avec un DNS à tour de rôle ou configurés pour utiliser Pool1 comme principaux, basculent vers Pool2 en cas de perte de communication ou de défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="0822d-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0822d-222">Enregistrement GeoDNS (exemple)</span><span class="sxs-lookup"><span data-stu-id="0822d-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="0822d-223">Enregistrements de pool (exemple)</span><span class="sxs-lookup"><span data-stu-id="0822d-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="0822d-224">Enregistrements CNAMe (exemple)</span><span class="sxs-lookup"><span data-stu-id="0822d-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="0822d-225">Paramètres DNS (sélectionnez une option)</span><span class="sxs-lookup"><span data-stu-id="0822d-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0822d-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-229">Alias Meet.contoso.com vers Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-230">Alias Meet.contoso.com vers Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-231">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-232">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0822d-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-236">Alias Meet.contoso.com vers Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-237">Alias Meet.contoso.com vers Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-238">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-239">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0822d-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-243">Alias Dialin.contoso.com vers Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-244">Alias Dialin.contoso.com vers Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-245">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-246">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0822d-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-250">Alias Dialin.contoso.com vers Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-251">Alias Dialin.contoso.com vers Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-252">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-253">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0822d-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-257">Alias Lyncdiscoverinternal.contoso.com vers Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-258">Alias Lyncdiscoverinternal.contoso.com vers Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-259">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-260">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0822d-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-264">Alias Lyncdiscover.contoso.com vers Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-265">Alias Lyncdiscover.contoso.com vers Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-266">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-267">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0822d-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-271">Alias Scheduler.contoso.com vers Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-272">Alias Scheduler.contoso.com vers Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-273">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-274">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0822d-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-278">Alias Scheduler.contoso.com vers Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="0822d-279">Alias Scheduler.contoso.com vers Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0822d-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0822d-280">Tourniquet entre les pools</span><span class="sxs-lookup"><span data-stu-id="0822d-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="0822d-281">Utiliser le principal, se connecter au secondaire en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="0822d-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="0822d-282">Équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="0822d-282">DNS Load Balancing</span></span>

<span data-ttu-id="0822d-283">L’équilibrage de la charge DNS est généralement implémenté au niveau de l’application.</span><span class="sxs-lookup"><span data-stu-id="0822d-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="0822d-284">L’application (par exemple, un client exécutant Lync) tente de se connecter à un serveur dans un pool en se connectant à l’une des adresses IP renvoyées par la requête d’enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour le nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="0822d-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="0822d-285">Si par exemple il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, voilà ce qui se produit :</span><span class="sxs-lookup"><span data-stu-id="0822d-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="0822d-286">Clients exécutant une requête DNS Lync pour pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="0822d-287">La requête renvoie trois adresses IP et les met en cache comme suit (pas nécessairement dans cet ordre) :</span><span class="sxs-lookup"><span data-stu-id="0822d-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="0822d-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="0822d-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="0822d-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="0822d-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="0822d-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="0822d-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="0822d-291">Le client tente d’établir une connexion TCP (Transmission Control Protocol) à l’une des adresses IP.</span><span class="sxs-lookup"><span data-stu-id="0822d-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="0822d-292">En cas d’échec, le client essaie l’adresse IP suivante dans le cache.</span><span class="sxs-lookup"><span data-stu-id="0822d-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="0822d-293">Si la connexion TCP réussit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0822d-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="0822d-294">Si le client essaie toutes les entrées mises en cache sans connexion, l’utilisateur est informé qu’aucun serveur exécutant Lync Server 2013 n’est disponible pour le moment.</span><span class="sxs-lookup"><span data-stu-id="0822d-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0822d-295">L’équilibrage de la charge DNS est différent du tourniquet (round robin) DNS (DNS RR) qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour fournir un ordre d’adresses IP différent correspondant aux serveurs d’un pool.</span><span class="sxs-lookup"><span data-stu-id="0822d-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="0822d-296">DNS RR active en général uniquement la distribution de la charge, mais n’active pas le basculement.</span><span class="sxs-lookup"><span data-stu-id="0822d-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="0822d-297">Par exemple, si la connexion à l’adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue.</span><span class="sxs-lookup"><span data-stu-id="0822d-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="0822d-298">Par conséquent, le tourniquet DNS (round robin) seul est moins fiable que l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="0822d-299">Vous pouvez utiliser le tourniquet DNS (round robin) conjointement avec l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="0822d-300">L’équilibrage de la charge DNS est utilisé dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="0822d-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="0822d-301">Équilibrage de la charge du SIP de serveur à serveur vers les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="0822d-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="0822d-302">Équilibrage de la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="0822d-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="0822d-303">Empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage »)</span><span class="sxs-lookup"><span data-stu-id="0822d-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="0822d-304">Équilibrage de la charge de l’ensemble du trafic client-serveur entre les clients et les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="0822d-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="0822d-305">L’équilibrage de la charge DNS ne peut pas être utilisé dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="0822d-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="0822d-306">Trafic Web client à serveur vers le directeur ou les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="0822d-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="0822d-307">Équilibrage de la charge DNS et trafic fédéré :</span><span class="sxs-lookup"><span data-stu-id="0822d-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="0822d-308">Si plusieurs enregistrements DNS sont renvoyés par une requête SRV DNS, le service Edge d’accès sélectionne toujours l’enregistrement DNS SRV avec la priorité numérique la plus basse et la pondération numérique la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="0822d-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="0822d-309">Le document IETF (Internet Engineering Task Force) « un RR DNS pour la spécification de l’emplacement des services <http://www.ietf.org/rfc/rfc2782.txt> (DNS SRV) » indique que s’il existe plusieurs enregistrements SRV DNS définis, Priority est utilisé pour la première fois, puis Weight.</span><span class="sxs-lookup"><span data-stu-id="0822d-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="0822d-310">Par exemple, l’enregistrement DNS SRV a a un poids de 20 et une priorité de 40 et un enregistrement DNS SRV B dont le poids est de 10 et la priorité 50.</span><span class="sxs-lookup"><span data-stu-id="0822d-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="0822d-311">L’enregistrement DNS SRV A avec la priorité 40 est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0822d-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="0822d-312">Les règles suivantes s’appliquent à la sélection des enregistrements SRV DNS :</span><span class="sxs-lookup"><span data-stu-id="0822d-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="0822d-313">La priorité est prise en compte en premier.</span><span class="sxs-lookup"><span data-stu-id="0822d-313">Priority is considered first.</span></span> <span data-ttu-id="0822d-314">Un client doit essayer de contacter l’hôte cible défini par l’enregistrement DNS SRV avec la priorité la plus faible qu’il peut atteindre.</span><span class="sxs-lookup"><span data-stu-id="0822d-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="0822d-315">Les cibles ayant la même priorité doivent être testées dans un ordre défini par le champ Weight.</span><span class="sxs-lookup"><span data-stu-id="0822d-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="0822d-316">Le champ poids spécifie un poids relatif pour les entrées présentant la même priorité.</span><span class="sxs-lookup"><span data-stu-id="0822d-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="0822d-317">Les poids plus élevés doivent se voir attribuer une probabilité proportionnellement plus élevée de sélection.</span><span class="sxs-lookup"><span data-stu-id="0822d-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="0822d-318">Les administrateurs DNS doivent utiliser le poids 0 lorsqu’il n’y a aucune sélection de serveur à effectuer.</span><span class="sxs-lookup"><span data-stu-id="0822d-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="0822d-319">En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements dont le poids est supérieur à 0 doivent avoir une chance très faible d’être sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="0822d-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="0822d-320">Si plusieurs enregistrements SRV DNS avec une priorité et un poids égaux sont renvoyés, le service Edge d’accès sélectionne l’enregistrement SRV qui a été reçu en premier à partir du serveur DNS.</span><span class="sxs-lookup"><span data-stu-id="0822d-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

