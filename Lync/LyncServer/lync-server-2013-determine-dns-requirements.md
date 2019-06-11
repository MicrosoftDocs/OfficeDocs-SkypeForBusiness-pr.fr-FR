---
title: 'Lync Server 2013 : Détermination de la configuration requise pour DNS pour Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="853e6-102">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="853e6-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="853e6-103">_**Dernière modification de la rubrique:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="853e6-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="853e6-104">Utilisez le diagramme de flux suivant pour déterminer la configuration requise DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="853e6-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="853e6-105">Les modifications apportées aux mises à jour cumulatives pour Lync Server 2013:2013 février sont indiquées dans l’emplacement où ils s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="853e6-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="853e6-106">Microsoft Lync Server 2013 prend en charge l’utilisation de l’adressage IPv6.</span><span class="sxs-lookup"><span data-stu-id="853e6-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="853e6-107">Pour utiliser les adresses IPv6, vous devez également fournir une prise en charge pour le DNS IPv6 et configurer les enregistrements d’hôte DNS AAAA (connus sous le nom de «Quad-A»).</span><span class="sxs-lookup"><span data-stu-id="853e6-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="853e6-108">Dans les déploiements où IPv4 et IPv6 sont utilisés, il est préférable de configurer et de gérer les enregistrements d’hôte A pour IPv4 et l’hôte AAAA pour IPv6.</span><span class="sxs-lookup"><span data-stu-id="853e6-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="853e6-109">Même si votre déploiement a été entièrement basculé vers IPv6, des enregistrements d’hôte DNS IPv4 peuvent toujours être requis lorsque des utilisateurs externes utilisent toujours IPv4.</span><span class="sxs-lookup"><span data-stu-id="853e6-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="853e6-110">**Déterminer le graphique de processus requis pour DNS**</span><span class="sxs-lookup"><span data-stu-id="853e6-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="853e6-111">![175782ac-363e-408a-912F-8991bf152970] (images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912F-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="853e6-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="853e6-112">Par défaut, le nom de l’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="853e6-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="853e6-113">Le générateur de topologie utilise les noms de domaine complets et non les noms d’hôte.</span><span class="sxs-lookup"><span data-stu-id="853e6-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="853e6-114">Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine.</span><span class="sxs-lookup"><span data-stu-id="853e6-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="853e6-115"><STRONG>Utilisez uniquement les caractères standard</STRONG> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools.</span><span class="sxs-lookup"><span data-stu-id="853e6-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="853e6-116">N’utilisez pas les caractères ou traits de soulignement Unicode.</span><span class="sxs-lookup"><span data-stu-id="853e6-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="853e6-117">Souvent, les caractères non standard dans un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand le FQDN doit être assigné au SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="853e6-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="853e6-118">Pour plus d’informations, voir <A href="lync-server-2013-configure-dns-host-records.md">configurer les enregistrements d’hôte DNS pour Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="853e6-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="853e6-119">Comment les clients Lync trouvent les services</span><span class="sxs-lookup"><span data-stu-id="853e6-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="853e6-120">Microsoft Lync 2010, Lync 2013 et Lync mobile sont similaires dans la façon dont le client recherche et accède aux services dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="853e6-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="853e6-121">L’exception notable est l’application Lync du Windows Store qui utilise un processus d’emplacement de service différent.</span><span class="sxs-lookup"><span data-stu-id="853e6-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="853e6-122">Cette section décrit en détail deux scénarios illustrant la façon dont les clients trouvent les services, d’abord la méthode classique à l’aide d’une série d’enregistrements SRV et en second lieu en utilisant uniquement les enregistrements du service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="853e6-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="853e6-123">Les mises à jour cumulatives apportées aux clients de bureau changent le processus d’emplacement DNS de Lync Server 2010 pour tous les clients, le processus de requête DNS se poursuit jusqu’à ce qu’une requête réussie soit renvoyée ou que la liste des enregistrements DNS possibles soit épuisée et que la dernière erreur soit retournée à le client.</span><span class="sxs-lookup"><span data-stu-id="853e6-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="853e6-124">Pour tous les clients, **à l’exception** de l’application Lync du Windows Store lors de la recherche DNS, les enregistrements SRV sont interrogés et renvoyés au client dans l’ordre suivant:</span><span class="sxs-lookup"><span data-stu-id="853e6-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="853e6-125">lyncdiscoverinternal. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web internes</span><span class="sxs-lookup"><span data-stu-id="853e6-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="853e6-126">lyncdiscover. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web externes</span><span class="sxs-lookup"><span data-stu-id="853e6-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="853e6-127">\_sipinternaltls. \_TCP. \<enregistrement\> Domain SRV (service Locator) pour les connexions TLS internes</span><span class="sxs-lookup"><span data-stu-id="853e6-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="853e6-128">\_sipinternal. \_TCP. \<enregistrement\> Domain SRV (Localisateur de service) pour les connexions TCP internes (exécuté uniquement si le protocole TCP est autorisé)</span><span class="sxs-lookup"><span data-stu-id="853e6-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="853e6-129">\_SIP. \_TLS. \<enregistrement\> Domain SRV (service Locator) pour les connexions TLS externes</span><span class="sxs-lookup"><span data-stu-id="853e6-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="853e6-130">sipinternal. \<l'\> enregistrement Domain A (Host) pour le pool frontal ou le directeur, résolu uniquement sur le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="853e6-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="853e6-131">SIP. \<enregistrement\> de domaine A (hôte) pour le pool frontal ou le directeur sur le réseau interne, ou le service Edge d’accès lorsque le client est externe</span><span class="sxs-lookup"><span data-stu-id="853e6-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="853e6-132">sipexternal. \<enregistrement\> de domaine A (hôte) pour le service Edge d’accès lorsque le client est externe</span><span class="sxs-lookup"><span data-stu-id="853e6-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="853e6-133">L’application Lync du Windows Store modifie entièrement le processus, car elle utilise deux enregistrements:</span><span class="sxs-lookup"><span data-stu-id="853e6-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="853e6-134">lyncdiscoverinternal. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web internes</span><span class="sxs-lookup"><span data-stu-id="853e6-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="853e6-135">lyncdiscover. \<enregistrement\> Domain A (Host) pour le service de découverte automatique sur les services Web externes</span><span class="sxs-lookup"><span data-stu-id="853e6-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="853e6-136">Il n’y a aucun retour vers les autres types d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="853e6-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="853e6-137">La différence entre les méthodes utilisées pour les nouveaux clients par rapport aux clients plus anciens est que le service de découverte automatique devient la méthode préférée pour rechercher tous les services.</span><span class="sxs-lookup"><span data-stu-id="853e6-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="853e6-138">Quand une connexion est établie, le service de découverte automatique renvoie toutes les URL des services Web pour le pool de domicile de l’utilisateur, y compris le service de mobilité (connu sous le nom de MCX par le répertoire virtuel créé pour le service dans IIS), Microsoft Lync Web App et URL Web Scheduler.</span><span class="sxs-lookup"><span data-stu-id="853e6-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="853e6-139">Toutefois, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont associées au nom de domaine complet des services Web externes.</span><span class="sxs-lookup"><span data-stu-id="853e6-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="853e6-140">Par conséquent, qu’il s’agisse d’un appareil mobile ou d’une connexion externe, l’appareil se connecte toujours au service de mobilité par le biais du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="853e6-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="853e6-141">Si les mises à jour cumulatives pour Lync Server 2013: février 2013 ont été installées, le service de découverte automatique renvoie également des références à des éléments internes/UCWA, externes/UCWA et UCWA.</span><span class="sxs-lookup"><span data-stu-id="853e6-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="853e6-142">Ces entrées font référence au composant WebPart Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="853e6-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="853e6-143">Pour l’instant, seul l’entrée UCWA est utilisée et fournit une référence à une URL pour le composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="853e6-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="853e6-144">UCWA est utilisé par les clients mobiles Lync 2013 au lieu du service de mobilité MCX utilisé par les clients mobiles Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="853e6-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="853e6-145">Lors de la création d’enregistrements SRV, il est important de ne pas oublier qu’ils doivent pointer vers un enregistrement DNS A et AAAA (si vous utilisez l’adressage IPv6) dans le même domaine dans lequel l’enregistrement SRV DNS est créé.</span><span class="sxs-lookup"><span data-stu-id="853e6-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="853e6-146">Par exemple, si l’enregistrement SRV est dans contoso.com, l’enregistrement A et le signe AAAA (si vous utilisez l’adressage IPv6) ne peuvent pas être dans fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="853e6-147">La configuration par défaut consiste à diriger tout le trafic du client mobile par le biais du site externe.</span><span class="sxs-lookup"><span data-stu-id="853e6-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="853e6-148">Vous pouvez modifier les paramètres pour renvoyer uniquement l’URL interne, si cela est préférable pour vos exigences.</span><span class="sxs-lookup"><span data-stu-id="853e6-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="853e6-149">Avec cette configuration, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’elles se trouvent à l’intérieur du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="853e6-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="853e6-150">Pour ce faire, vous devez utiliser l’applet <STRONG>de passe Set-CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="853e6-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="853e6-151">Même si les applications mobiles peuvent également se connecter à d’autres services Lync Server 2013, tels que le service de carnet d’adresses, les demandes Web de l’application mobile interne sont dirigées vers le FQDN Web externe uniquement pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="853e6-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="853e6-152">D’autres demandes de service, telles que des demandes de carnet d’adresses, ne nécessitent pas cette configuration.</span><span class="sxs-lookup"><span data-stu-id="853e6-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="853e6-153">Les appareils mobiles prennent en charge la découverte manuelle des services.</span><span class="sxs-lookup"><span data-stu-id="853e6-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="853e6-154">Dans le cas présent, chaque utilisateur doit configurer les paramètres de l’appareil mobile avec les URI de service de découverte automatique internes et externes complets, y compris le protocole et le chemin d’accès comme suit:</span><span class="sxs-lookup"><span data-stu-id="853e6-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="853e6-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root pour l’accès externe</span><span class="sxs-lookup"><span data-stu-id="853e6-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="853e6-156">https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root pour l’accès interne</span><span class="sxs-lookup"><span data-stu-id="853e6-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="853e6-157">Nous vous recommandons d’utiliser la découverte automatique plutôt que la découverte manuelle.</span><span class="sxs-lookup"><span data-stu-id="853e6-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="853e6-158">Toutefois, il peut s’avérer utile de résoudre les problèmes de connectivité des appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="853e6-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="853e6-159">Configuration du système DNS split-brain avec Lync Server</span><span class="sxs-lookup"><span data-stu-id="853e6-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="853e6-160">Le système DNS split-brain est connu par un certain nombre de noms (par exemple, Split DNS ou Split-horizon).</span><span class="sxs-lookup"><span data-stu-id="853e6-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="853e6-161">Il s’agit simplement d’une configuration DNS qui comporte deux zones DNS ayant le même espace de noms, mais une requête en interne uniquement pour les services de zone DNS, et les autres demandes externes aux services de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="853e6-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="853e6-162">Toutefois, la plupart des enregistrements DNS SRV et A contenus dans le DNS interne ne seront pas inclus dans le DNS externe et l’inverse est également vrai.</span><span class="sxs-lookup"><span data-stu-id="853e6-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="853e6-163">Dans les cas où il existe le même enregistrement DNS dans le DNS interne et externe (par exemple, www.contoso.com), l’adresse IP renvoyée sera différente en fonction de la date à laquelle la requête a été lancée (interne ou externe).</span><span class="sxs-lookup"><span data-stu-id="853e6-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="853e6-164">Pour le moment, le DNS fractionné-Brain n’est pas pris en charge pour la mobilité, ou plus précisément, les enregistrements DNS LyncDiscover et LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="853e6-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="853e6-165">LyncDiscover doit être défini sur un serveur DNS externe et LyncDiscoverInternal doit être défini sur un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="853e6-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="853e6-166">Dans le cadre de ces rubriques, le terme «DNS split-brain» sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="853e6-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="853e6-167">Si vous configurez le système DNS fractionné-Brain, la zone interne et externe suivante contiennent un résumé des types d’enregistrements DNS requis dans chaque zone.</span><span class="sxs-lookup"><span data-stu-id="853e6-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="853e6-168">Pour plus d’informations, reportez-vous à la rubrique [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="853e6-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="853e6-169">**DNS interne:**</span><span class="sxs-lookup"><span data-stu-id="853e6-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="853e6-170">Contient une zone DNS appelée contoso.com pour laquelle il fait autorité</span><span class="sxs-lookup"><span data-stu-id="853e6-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="853e6-171">La zone contoso.com interne contient les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="853e6-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="853e6-172">DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour la configuration automatique du client Lync Server 2013 interne (facultatif)</span><span class="sxs-lookup"><span data-stu-id="853e6-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="853e6-173">DNS A et AAAA (si vous utilisez l’adressage IPv6) ou les enregistrements CNAMe pour la découverte automatique des services Web Lync Server 2013 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="853e6-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="853e6-174">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour le nom du pool frontal, le directeur ou le nom du pool de réalisateurs, ainsi que tous les serveurs internes exécutant Lync Server 2013 sur le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="853e6-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="853e6-175">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne latérale de chaque Lync Server 2013, serveur Edge du réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="853e6-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="853e6-176">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface interne de chaque serveur proxy inverse dans le réseau de périmètre (facultatif pour la gestion du proxy inverse)</span><span class="sxs-lookup"><span data-stu-id="853e6-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="853e6-177">Toutes les interfaces Edge internes de Lync Server 2013 Edge Server dans le réseau de périmètre utilisent la zone DNS interne pour la résolution des requêtes vers contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="853e6-178">Tous les serveurs exécutant Lync Server 2013 et les clients exécutant Lync 2013 dans le réseau d’entreprise pointent vers les serveurs DNS internes pour la résolution des requêtes vers contoso.com ou l’utilisation du fichier HOSTs sur chaque serveur Edge et de la liste A et des enregistrements AAAA (si vous utilisez l’adressage IPv6) pour serveur du tronçon suivant, en particulier le directeur ou le VIP du réalisateur, le protocole VIP de pool frontal ou le serveur Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="853e6-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="853e6-179">**DNS externe:**</span><span class="sxs-lookup"><span data-stu-id="853e6-179">**External DNS:**</span></span>

  - <span data-ttu-id="853e6-180">Contient une zone DNS appelée contoso.com pour laquelle il fait autorité</span><span class="sxs-lookup"><span data-stu-id="853e6-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="853e6-181">La zone contoso.com externe contient les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="853e6-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="853e6-182">DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour la configuration automatique du client Lync Server 2013 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="853e6-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="853e6-183">DNS A et AAAA (si vous utilisez l’adressage IPv6) ou les enregistrements CNAMe pour la découverte automatique des services Web de Lync Server 2013 pour une utilisation avec la mobilité</span><span class="sxs-lookup"><span data-stu-id="853e6-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="853e6-184">DNS A et AAAA (si vous utilisez l’adressage IPv6) et enregistrements SRV pour l’interface externe Edge de chaque adresse IP virtuelle Lync Server 2013, Edge Server ou du réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="853e6-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="853e6-185">Enregistrements DNS A et AAAA (si vous utilisez l’adressage IPv6) pour l’interface externe du serveur proxy inverse ou d’une adresse IP virtuelle pour une réserve de serveurs proxy inverse dans le réseau de périmètre</span><span class="sxs-lookup"><span data-stu-id="853e6-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="853e6-186">Configuration automatique sans DNS fractionné-Brain</span><span class="sxs-lookup"><span data-stu-id="853e6-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="853e6-187">À l’aide du système DNS fractionné-Brain, un utilisateur de Lync Server 2013 qui se connecte en interne peut tirer parti de la configuration automatique \_si la zone DNS interne contient une sipinternaltls. \_enregistrement SRV TCP pour chaque domaine SIP utilisé.</span><span class="sxs-lookup"><span data-stu-id="853e6-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="853e6-188">Toutefois, si vous n’utilisez pas le DNS fractionné-Brain, la configuration automatique interne des clients exécutant Lync ne fonctionne pas, sauf si l’une des solutions de contournement décrites dans la section ci-après est implémentée.</span><span class="sxs-lookup"><span data-stu-id="853e6-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="853e6-189">Le problème est dû au fait que Lync Server 2013 nécessite que l’URI SIP de l’utilisateur correspond au domaine du pool frontal destiné à la configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="853e6-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="853e6-190">C’est également le cas dans les versions antérieures de Communicator.</span><span class="sxs-lookup"><span data-stu-id="853e6-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="853e6-191">Par exemple, si deux domaines SIP sont utilisés, les enregistrements de service DNS (SRV) suivants sont nécessaires:</span><span class="sxs-lookup"><span data-stu-id="853e6-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="853e6-192">Si un utilisateur se connecte en tant que bob@contoso.com, l’enregistrement SRV suivant fonctionne pour la configuration automatique, car le domaine SIP de l’utilisateur (contoso.com) correspond au domaine du pool frontal de configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="853e6-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="853e6-193">\_sipinternaltls. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="853e6-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="853e6-195">Si un utilisateur se connecte en tant que alice@fabrikam.com, l’enregistrement SRV DNS suivant fonctionne pour la configuration automatique du deuxième domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="853e6-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="853e6-196">\_sipinternaltls. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="853e6-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="853e6-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="853e6-198">Pour comparaison, si un utilisateur se connecte en tant que tim@litwareinc.com, l’enregistrement SRV DNS suivant ne fonctionne pas pour la configuration automatique, car le domaine SIP du client (litwareinc.com) ne correspond pas au domaine dans lequel se trouve le pool (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="853e6-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="853e6-199">\_sipinternaltls. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="853e6-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="853e6-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="853e6-201">Si la configuration automatique est requise pour les clients exécutant Lync, sélectionnez l’une des options suivantes:</span><span class="sxs-lookup"><span data-stu-id="853e6-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="853e6-202">**Les objets**   de stratégie de groupe utilisent des objets de stratégie de groupe pour renseigner les valeurs de serveur correctes.</span><span class="sxs-lookup"><span data-stu-id="853e6-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="853e6-203">Si cette option n’est pas activée dans le processus de configuration manuelle, vous n’avez pas besoin de configurer automatiquement les enregistrements SRV associés à la configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="853e6-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="853e6-204">\*\*\*\*   Mise en correspondance de la zone interne créez une zone dans le DNS interne qui correspond à la zone DNS externe (par exemple, contoso.com) et créez les enregistrements DNS a et aaaa (si vous utilisez l’adressage IPv6) correspondant au pool Lync Server 2013 utilisé pour la gestion automatique. configurations.</span><span class="sxs-lookup"><span data-stu-id="853e6-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="853e6-205">Par exemple, si un utilisateur est hébergé sur pool01.contoso.net mais qu’il se connecte à Lync en tant que bob@contoso.com, créez une zone DNS interne appelée contoso.com et à l’intérieur de cette dernière, créez un enregistrement DNS A et AAAA (si l’adressage IPv6 est utilisé) pour pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="853e6-206">**Zone interne en mode punaise**   si vous créez une zone entière dans le DNS interne n’est pas une option disponible, vous pouvez créer des zones de point d’épingle (qui sont dédiées) qui correspondent aux enregistrements SRV requis pour la configuration automatique et les renseigner les zones utilisant dnscmd. exe.</span><span class="sxs-lookup"><span data-stu-id="853e6-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="853e6-207">Dnscmd. exe est requis, car l’interface utilisateur DNS ne prend pas en charge la création de zones au lieu de punaise.</span><span class="sxs-lookup"><span data-stu-id="853e6-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="853e6-208">Par exemple, si le domaine SIP est contoso.com et que vous avez un pool frontal appelé pool01 qui contient deux serveurs frontaux, vous avez besoin des zones de points de repère et des enregistrements A suivants dans votre DNS interne:</span><span class="sxs-lookup"><span data-stu-id="853e6-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="853e6-209">Si votre environnement contient un deuxième domaine SIP (par exemple, fabrikam.com), vous avez besoin des zones de points de repère et des enregistrements A suivants dans votre DNS interne:</span><span class="sxs-lookup"><span data-stu-id="853e6-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="853e6-210">Le nom de domaine complet (FQDN) du pool frontal apparaît deux fois, mais avec deux adresses IP différentes.</span><span class="sxs-lookup"><span data-stu-id="853e6-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="853e6-211">En effet, l’équilibrage de charge DNS est utilisé, mais si l’équilibrage de charge matérielle est utilisé, il n’y a qu’une entrée de pool frontal unique.</span><span class="sxs-lookup"><span data-stu-id="853e6-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="853e6-212">Par ailleurs, les valeurs de nom de domaine complet (FQDN) du pool frontal changent entre l’exemple contoso.com et l’exemple fabrikam.com, mais les adresses IP restent identiques.</span><span class="sxs-lookup"><span data-stu-id="853e6-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="853e6-213">En effet, les utilisateurs qui se connectent à partir d’un domaine SIP utilisent le même pool frontal pour la configuration automatique.</span><span class="sxs-lookup"><span data-stu-id="853e6-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="853e6-214">Pour plus d’informations, reportez-vous à [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)l’article de blog DMTF «configuration automatique de Communicator et DNS split-brain».</span><span class="sxs-lookup"><span data-stu-id="853e6-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="853e6-215">Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.</span><span class="sxs-lookup"><span data-stu-id="853e6-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="853e6-216">Configuration du DNS (Domain Name System) pour la récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="853e6-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="853e6-217">Pour configurer le système DNS afin de rediriger le trafic Web de Lync Server 2013 vers vos sites de reprise et de basculement sur incident, vous devez utiliser un fournisseur DNS qui prend en charge GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="853e6-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="853e6-218">Vous pouvez configurer vos enregistrements DNS pour le Web de manière à ce qu’ils prennent en charge la récupération après sinistre, de sorte que les fonctionnalités qui utilisent les services Web continuent de fonctionner, même si une seule partie du frontale s’affiche.</span><span class="sxs-lookup"><span data-stu-id="853e6-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="853e6-219">Cette fonctionnalité de reprise après sinistre prend en charge la découverte automatique (URL Lyncdiscover), la réunion et les URL simples de connexion.</span><span class="sxs-lookup"><span data-stu-id="853e6-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="853e6-220">Vous pouvez définir et configurer des enregistrements DNS supplémentaires (A et AAAA si vous utilisez des enregistrements IPv6) pour la résolution interne et externe des services Web auprès de votre fournisseur de services de GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="853e6-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="853e6-221">Les détails suivants présupposent que le niveau de répartition des réserves, géographiquement et GeoDNS est pris en charge par votre fournisseur avec le DNS à répétition alternée ou configuré pour utiliser Pool1 comme principal, et basculer vers Pool2 en cas de perte de communication ou de défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="853e6-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="853e6-222">Enregistrement GeoDNS (exemple)</span><span class="sxs-lookup"><span data-stu-id="853e6-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="853e6-223">Enregistrements du pool (exemple)</span><span class="sxs-lookup"><span data-stu-id="853e6-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="853e6-224">Enregistrements CNAMe (exemple)</span><span class="sxs-lookup"><span data-stu-id="853e6-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="853e6-225">Paramètres DNS (sélectionnez une option)</span><span class="sxs-lookup"><span data-stu-id="853e6-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="853e6-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-229">Meet.contoso.com alias de Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-230">Meet.contoso.com alias de Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-231">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-232">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853e6-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-236">Meet.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-237">Meet.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-238">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-239">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853e6-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-243">Dialin.contoso.com alias de Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-244">Dialin.contoso.com alias de Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-245">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-246">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853e6-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-250">Dialin.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-251">Dialin.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-252">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-253">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853e6-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-257">Lyncdiscoverinternal.contoso.com alias de Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-258">Lyncdiscoverinternal.contoso.com alias de Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-259">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-260">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853e6-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-264">Lyncdiscover.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-265">Lyncdiscover.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-266">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-267">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853e6-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-271">Scheduler.contoso.com alias de Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-272">Scheduler.contoso.com alias de Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-273">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-274">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853e6-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-278">Scheduler.contoso.com alias de Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="853e6-279">Scheduler.contoso.com alias de Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="853e6-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="853e6-280">Round Robin entre pools</span><span class="sxs-lookup"><span data-stu-id="853e6-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="853e6-281">Utiliser le principal, se connecter à Secondary en cas d’échec</span><span class="sxs-lookup"><span data-stu-id="853e6-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="853e6-282">DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="853e6-282">DNS Load Balancing</span></span>

<span data-ttu-id="853e6-283">L’équilibrage de charge DNS est généralement implémenté au niveau de l’application.</span><span class="sxs-lookup"><span data-stu-id="853e6-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="853e6-284">Dans le cas contraire, l’application (par exemple, un client exécutant Lync) essaie de se connecter à un serveur dans un pool en se connectant à l’une des adresses IP renvoyées à partir de l’enregistrement DNS A et du nom de domaine AAAA (si l’adressage IPv6 est utilisé).</span><span class="sxs-lookup"><span data-stu-id="853e6-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="853e6-285">Par exemple, s’il existe trois serveurs front end dans un pool intitulé pool01.contoso.com, les informations suivantes se produisent:</span><span class="sxs-lookup"><span data-stu-id="853e6-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="853e6-286">Les clients exécutant une requête Lync DNS pour pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="853e6-287">La requête renvoie trois adresses IP et les met en cache comme suit (pas nécessairement dans cet ordre):</span><span class="sxs-lookup"><span data-stu-id="853e6-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="853e6-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="853e6-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="853e6-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="853e6-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="853e6-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="853e6-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="853e6-291">Le client tente d’établir une connexion TCP (Transmission Control Protocol) vers l’une des adresses IP.</span><span class="sxs-lookup"><span data-stu-id="853e6-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="853e6-292">En cas d’échec, le client tente l’adresse IP suivante dans le cache.</span><span class="sxs-lookup"><span data-stu-id="853e6-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="853e6-293">Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="853e6-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="853e6-294">Si le client tente d’accéder à toutes les entrées du cache sans connexion réussie, l’utilisateur est prévenu qu’aucun serveur exécutant Lync Server 2013 n’est disponible pour le moment.</span><span class="sxs-lookup"><span data-stu-id="853e6-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="853e6-295">Le service d’équilibrage de charge DNS est différent de l’équilibrage de charge DNS (RR) qui fait généralement référence à l’équilibrage de charge en fonction du système DNS, qui fournit un ordre différent d’adresses IP correspondant aux serveurs d’un pool.</span><span class="sxs-lookup"><span data-stu-id="853e6-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="853e6-296">En règle générale, le RR DNS active uniquement la distribution de charge, mais n’autorise pas le basculement.</span><span class="sxs-lookup"><span data-stu-id="853e6-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="853e6-297">Par exemple, si la connexion à une adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue.</span><span class="sxs-lookup"><span data-stu-id="853e6-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="853e6-298">C’est la raison pour laquelle le tourniquet DNS est plutôt moins fiable que le service d’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="853e6-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="853e6-299">Vous pouvez utiliser le tourniquet DNS conjointement avec l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="853e6-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="853e6-300">L’équilibrage de charge DNS est utilisé pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="853e6-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="853e6-301">Équilibrage de la charge de serveur à serveur SIP aux serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="853e6-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="853e6-302">Les applications UCAS (Unified Communications application Services) de répartition de charge telles que le standard automatique des conférences, le groupe de réponse et le parc d’appels</span><span class="sxs-lookup"><span data-stu-id="853e6-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="853e6-303">Interdiction de nouvelles connexions aux applications UCAS (également appelées «drainage»)</span><span class="sxs-lookup"><span data-stu-id="853e6-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="853e6-304">Équilibrage de la charge de tout le trafic client à serveur entre les clients et les serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="853e6-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="853e6-305">L’équilibrage de charge DNS ne peut pas être utilisé pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="853e6-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="853e6-306">Trafic Web de client à serveur vers le directeur ou les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="853e6-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="853e6-307">Équilibrage de charge DNS et trafic fédéré:</span><span class="sxs-lookup"><span data-stu-id="853e6-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="853e6-308">Si plusieurs enregistrements DNS sont renvoyés par une requête DNS SRV, le service Edge d’accès sélectionne toujours l’enregistrement SRV DNS avec la priorité numérique la plus basse et la pondération numérique la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="853e6-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="853e6-309">Le document «IETF (Internet Engineering Task Force» "un RR DNS pour spécifier l’emplacement des services ( <http://www.ietf.org/rfc/rfc2782.txt> DNS SRV)" spécifie que, si plusieurs enregistrements SRV DNS sont définis, la priorité est d’abord utilisée, puis pondération.</span><span class="sxs-lookup"><span data-stu-id="853e6-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="853e6-310">Par exemple, l’enregistrement SRV DNS a a une épaisseur de 20 et une priorité de 40 et de l’enregistrement SRV DNS B a une épaisseur de 10 et de Priority 50.</span><span class="sxs-lookup"><span data-stu-id="853e6-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="853e6-311">L’enregistrement SRV DNS A avec la priorité 40 est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="853e6-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="853e6-312">Les règles suivantes s’appliquent à la sélection d’enregistrements SRV DNS:</span><span class="sxs-lookup"><span data-stu-id="853e6-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="853e6-313">Priority est considéré comme premier.</span><span class="sxs-lookup"><span data-stu-id="853e6-313">Priority is considered first.</span></span> <span data-ttu-id="853e6-314">Un client doit tenter de contacter l’hôte cible défini par l’enregistrement SRV DNS dont la priorité numéro faible peut être atteinte.</span><span class="sxs-lookup"><span data-stu-id="853e6-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="853e6-315">Les cibles de même priorité doivent être essayées dans un ordre défini par le champ pondération.</span><span class="sxs-lookup"><span data-stu-id="853e6-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="853e6-316">Le champ poids spécifie une pondération relative pour les entrées ayant la même priorité.</span><span class="sxs-lookup"><span data-stu-id="853e6-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="853e6-317">Le plus grand nombre de pondérations doit être proportionnel à la sélection.</span><span class="sxs-lookup"><span data-stu-id="853e6-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="853e6-318">Les administrateurs DNS doivent utiliser le poids 0 quand il n’y a pas de sélection de serveur à effectuer.</span><span class="sxs-lookup"><span data-stu-id="853e6-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="853e6-319">En présence d’enregistrements contenant des pondérations supérieures à 0, les enregistrements de poids 0 doivent avoir une très petite chance d’être sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="853e6-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="853e6-320">Si plusieurs enregistrements SRV DNS ayant une priorité et un poids identiques sont retournés, le service Edge d’accès sélectionne l’enregistrement SRV reçu en premier du serveur DNS.</span><span class="sxs-lookup"><span data-stu-id="853e6-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

