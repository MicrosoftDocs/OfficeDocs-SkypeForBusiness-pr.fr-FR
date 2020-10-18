---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-découverte automatique'
description: 'Lync Server 2013 : Résumé des enregistrements DNS-découverte automatique.'
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
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574280"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="a204a-103">Résumé des enregistrements DNS-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a204a-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a204a-104">_**Dernière modification de la rubrique :** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="a204a-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="a204a-105">La découverte automatique est un service flexible en ce qu’elle accepte la communication via HTTP ou HTTPs.</span><span class="sxs-lookup"><span data-stu-id="a204a-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="a204a-106">Pour ce faire, le système DNS (Domain Name System) et les certificats utilisés par les serveurs qui hébergent le service de découverte automatique doivent être configurés correctement.</span><span class="sxs-lookup"><span data-stu-id="a204a-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="a204a-107">Les exigences de certificat sont traitées dans [Résumé des certificats-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="a204a-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a204a-108">La logique de recherche DNS pour les clients Lync Server utilise un ordre de résolution spécifique.</span><span class="sxs-lookup"><span data-stu-id="a204a-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="a204a-109">Vous devez toujours inclure le lyncdiscoverinternal. &lt; domaine &gt; et lyncdiscover. &lt; domaine &gt; dans votre DNS.</span><span class="sxs-lookup"><span data-stu-id="a204a-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="a204a-110">À l’exclusion du lyncdiscoverinternal. &lt; l' &gt; enregistrement de domaine entraîne l’échec de la connexion des clients internes aux services prévus ou la réception d’une réponse de découverte automatique incorrecte.</span><span class="sxs-lookup"><span data-stu-id="a204a-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="a204a-111">Enregistrements DNS internes</span><span class="sxs-lookup"><span data-stu-id="a204a-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a204a-112">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="a204a-112">Record type</span></span></th>
<th><span data-ttu-id="a204a-113">Nom d’hôte</span><span class="sxs-lookup"><span data-stu-id="a204a-113">Host name</span></span></th>
<th><span data-ttu-id="a204a-114">Résolu en</span><span class="sxs-lookup"><span data-stu-id="a204a-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a204a-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="a204a-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="a204a-116">Lyncdiscoverinternal. &lt; nom de domaine interne&gt;</span><span class="sxs-lookup"><span data-stu-id="a204a-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="a204a-117">Nom de domaine complet (FQDN) des services Web internes pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur.</span><span class="sxs-lookup"><span data-stu-id="a204a-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a204a-118">A (hôte, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="a204a-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="a204a-119">lyncdiscoverinternal. &lt; nom de domaine interne&gt;</span><span class="sxs-lookup"><span data-stu-id="a204a-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="a204a-120">Adresse IP interne des services Web (adresse IP virtuelle (VIP) si vous utilisez un programme d’équilibrage de la charge) de votre pool Directeur, si vous en avez un, ou de votre pool frontal si vous ne disposez pas d’un directeur.</span><span class="sxs-lookup"><span data-stu-id="a204a-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a204a-121">Vous devez créer l’un des enregistrements DNS externes suivants :</span><span class="sxs-lookup"><span data-stu-id="a204a-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="a204a-122">Enregistrements DNS externes</span><span class="sxs-lookup"><span data-stu-id="a204a-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a204a-123">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="a204a-123">Record type</span></span></th>
<th><span data-ttu-id="a204a-124">Nom d’hôte</span><span class="sxs-lookup"><span data-stu-id="a204a-124">Host name</span></span></th>
<th><span data-ttu-id="a204a-125">Résolu en</span><span class="sxs-lookup"><span data-stu-id="a204a-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a204a-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="a204a-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="a204a-127">lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a204a-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="a204a-128">Nom de domaine complet externe des services Web pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur.</span><span class="sxs-lookup"><span data-stu-id="a204a-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a204a-129">A (hôte, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="a204a-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="a204a-130">lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a204a-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="a204a-131">Adresse IP externe ou publique du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a204a-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a204a-132">Le trafic externe passe par le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a204a-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a204a-133">Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) de différents domaines.</span><span class="sxs-lookup"><span data-stu-id="a204a-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="a204a-134">Par conséquent, la redirection CNAME vers différents domaines n’est pas prise en charge sur le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a204a-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="a204a-135">Par exemple, un enregistrement DNS CNAME pour lyncdiscover.contoso.com qui redirige vers une adresse director.contoso.net n’est pas pris en charge sur HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a204a-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="a204a-136">Dans une telle topologie, un client d’appareil mobile doit utiliser le protocole HTTP pour la première demande, de sorte que la redirection CNAME soit résolue sur HTTP.</span><span class="sxs-lookup"><span data-stu-id="a204a-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="a204a-137">Les demandes ultérieures utilisent ensuite le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a204a-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="a204a-138">Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication web pour le port 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="a204a-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="a204a-139">Pour plus d’informations, reportez-vous à la section « pour créer une règle de publication Web pour le port 80 » dans <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configuration du proxy inverse pour la mobilité dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a204a-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="a204a-140">La redirection CNAME vers le même domaine est prise en charge sur HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a204a-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="a204a-141">Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.</span><span class="sxs-lookup"><span data-stu-id="a204a-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a204a-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a204a-142">See Also</span></span>


[<span data-ttu-id="a204a-143">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a204a-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="a204a-144">Résumé des certificats-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a204a-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

