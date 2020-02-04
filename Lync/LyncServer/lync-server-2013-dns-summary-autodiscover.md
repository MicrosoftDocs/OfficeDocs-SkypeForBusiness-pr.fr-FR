---
title: 'Serveur Lync Server 2013 : Résumé DNS-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="3d3de-102">DNS Summary-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3de-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d3de-103">_**Dernière modification de la rubrique :** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="3d3de-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="3d3de-104">La découverte automatique est un service flexible qui accepte les communications via HTTP ou HTTPs.</span><span class="sxs-lookup"><span data-stu-id="3d3de-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="3d3de-105">Pour ce faire, le système de noms de domaine (DNS) et les certificats utilisés par les serveurs qui hébergent le service de découverte automatique doivent être correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="3d3de-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="3d3de-106">Les exigences en matière de certificats sont décrites dans [synthèse des certificats-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="3d3de-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d3de-107">La logique de recherche DNS pour les clients du serveur Lync utilise un ordre de résolution spécifique.</span><span class="sxs-lookup"><span data-stu-id="3d3de-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="3d3de-108">Vous devez toujours inclure le lyncdiscoverinternal. &lt;Domain&gt; et lyncdiscover. &lt;Domain&gt; de votre DNS.</span><span class="sxs-lookup"><span data-stu-id="3d3de-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="3d3de-109">À l’exception du lyncdiscoverinternal. &lt;l'&gt; enregistrement du domaine entraîne l’échec de la connexion des clients internes aux services prévus ou la réception d’une réponse de découverte automatique incorrecte.</span><span class="sxs-lookup"><span data-stu-id="3d3de-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="3d3de-110">Enregistrements DNS internes</span><span class="sxs-lookup"><span data-stu-id="3d3de-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d3de-111">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="3d3de-111">Record type</span></span></th>
<th><span data-ttu-id="3d3de-112">Nom d’hôte</span><span class="sxs-lookup"><span data-stu-id="3d3de-112">Host name</span></span></th>
<th><span data-ttu-id="3d3de-113">Résolu en</span><span class="sxs-lookup"><span data-stu-id="3d3de-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d3de-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d3de-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="3d3de-115">Lyncdiscoverinternal. &lt;nom de domaine interne&gt;</span><span class="sxs-lookup"><span data-stu-id="3d3de-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="3d3de-116">Nom de domaine complet (FQDN) des services Web internes de votre pool de Director, si vous en avez un ou pour votre pool frontal si vous n’avez pas de directeur.</span><span class="sxs-lookup"><span data-stu-id="3d3de-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d3de-117">A (hôte, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="3d3de-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="3d3de-118">lyncdiscoverinternal. &lt;nom de domaine interne&gt;</span><span class="sxs-lookup"><span data-stu-id="3d3de-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="3d3de-119">Adresse IP des services Web internes (adresse IP virtuelle) si vous utilisez un équilibreur de charge, si vous en avez un, ou si vous n’avez pas de réalisateur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3d3de-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3d3de-120">Vous devez créer un des enregistrements DNS externes suivants :</span><span class="sxs-lookup"><span data-stu-id="3d3de-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="3d3de-121">Enregistrements DNS externes</span><span class="sxs-lookup"><span data-stu-id="3d3de-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d3de-122">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="3d3de-122">Record type</span></span></th>
<th><span data-ttu-id="3d3de-123">Nom d’hôte</span><span class="sxs-lookup"><span data-stu-id="3d3de-123">Host name</span></span></th>
<th><span data-ttu-id="3d3de-124">Résolu en</span><span class="sxs-lookup"><span data-stu-id="3d3de-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d3de-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="3d3de-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="3d3de-126">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="3d3de-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="3d3de-127">Nom de domaine complet des services Web externes pour votre pool de directeurs, le cas échéant, ou pour votre pool frontal si vous n’avez pas de directeur.</span><span class="sxs-lookup"><span data-stu-id="3d3de-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d3de-128">A (hôte, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="3d3de-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="3d3de-129">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="3d3de-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="3d3de-130">Adresse IP externe ou publique du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3d3de-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3d3de-131">Le trafic externe traverse le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3d3de-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3d3de-132">Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) provenant de différents domaines.</span><span class="sxs-lookup"><span data-stu-id="3d3de-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="3d3de-133">Par conséquent, la redirection CNAMe vers différents domaines n’est pas prise en charge sur HTTPs.</span><span class="sxs-lookup"><span data-stu-id="3d3de-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="3d3de-134">Par exemple, un enregistrement CNAMe DNS pour lyncdiscover.contoso.com qui redirige vers une adresse de director.contoso.net n’est pas pris en charge sur HTTPs.</span><span class="sxs-lookup"><span data-stu-id="3d3de-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="3d3de-135">Dans le cas d’une telle topologie, un client d’appareil mobile doit utiliser HTTP pour la première demande, de sorte que la redirection CNAMe soit résolue via HTTP.</span><span class="sxs-lookup"><span data-stu-id="3d3de-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="3d3de-136">Les requêtes suivantes utilisent alors HTTPs.</span><span class="sxs-lookup"><span data-stu-id="3d3de-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="3d3de-137">Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication Web pour le port 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="3d3de-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="3d3de-138">Pour plus d’informations, reportez-vous à la section « pour créer une règle de publication Web pour le port 80 » dans <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configuration du proxy inverse pour la mobilité dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d3de-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="3d3de-139">La redirection CNAMe vers le même domaine est prise en charge sur HTTPs.</span><span class="sxs-lookup"><span data-stu-id="3d3de-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="3d3de-140">Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.</span><span class="sxs-lookup"><span data-stu-id="3d3de-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d3de-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d3de-141">See Also</span></span>


[<span data-ttu-id="3d3de-142">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3de-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="3d3de-143">Résumé du certificat-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3de-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

