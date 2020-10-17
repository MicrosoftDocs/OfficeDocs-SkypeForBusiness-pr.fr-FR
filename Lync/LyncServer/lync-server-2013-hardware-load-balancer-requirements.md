---
title: Configuration requise pour l’équilibreur de charge matérielle Lync Server 2013
description: Configuration requise pour le programme d’équilibrage de la charge matérielle de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552920"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="c3532-103">Configuration requise pour le programme d’équilibrage de la charge matérielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3532-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3532-104">_**Dernière modification de la rubrique :** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="c3532-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="c3532-105">La topologie Edge consolidée Lync Server 2013 est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements qui se fédéreront principalement avec d’autres organisations utilisant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3532-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="c3532-106">Si, dans l’un des scénarios suivants, la haute disponibilité est requise, vous devez utiliser un programme d’équilibrage de la charge matérielle sur les pools de serveurs Edge pour prendre en charge ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c3532-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="c3532-107">Fédération avec les organisations qui utilisent Office Communications Server 2007 R2 ou Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c3532-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="c3532-108">Messagerie unifiée Exchange pour les utilisateurs distants utilisant la messagerie unifiée Exchange avant Exchange 2010 avec SP1</span><span class="sxs-lookup"><span data-stu-id="c3532-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="c3532-109">connectivité avec les utilisateurs de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="c3532-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3532-p102">L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="c3532-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c3532-p103">Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne.</span><span class="sxs-lookup"><span data-stu-id="c3532-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c3532-114">Le protocole NAT DSR (direct Server Return) n’est pas pris en charge avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3532-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="c3532-115">Pour déterminer si votre programme d’équilibrage de la charge matérielle prend en charge les fonctionnalités requises par Lync Server 2013, voir « partenaires d’équilibrage de charge Lync Server 2010 » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="c3532-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="c3532-116">Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="c3532-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="c3532-117">Voici la configuration requise pour l’équilibreur de charge matérielle pour les serveurs Edge exécutant le service Edge A/V :</span><span class="sxs-lookup"><span data-stu-id="c3532-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="c3532-p104">Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux, afin de rendre la transmission plus efficace.</span><span class="sxs-lookup"><span data-stu-id="c3532-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="c3532-120">Désactivez le nagling TCP pour la plage de ports externes 50 000 – 59 999.</span><span class="sxs-lookup"><span data-stu-id="c3532-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="c3532-121">N’utilisez pas NAT sur le pare-feu interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="c3532-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="c3532-122">L’interface interne Edge doit se trouver sur un autre réseau que l’interface externe Edge Server, et le routage entre elles doit être désactivé.</span><span class="sxs-lookup"><span data-stu-id="c3532-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="c3532-123">L’interface externe du serveur Edge exécutant le service Edge A/V doit utiliser des adresses IP publiquement routables et aucune traduction d’adresses réseau ou NAT sur les adresses IP externes du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="c3532-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="c3532-124">Exigences relatives au programme d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="c3532-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="c3532-125">Les exigences en matière d’affinité basée sur les cookies sont considérablement réduites dans Lync Server 2013 pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="c3532-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="c3532-126">Si vous déployez Lync Server 2013 et que vous ne conservez pas de serveurs frontaux ou de pools frontaux Lync Server 2010, vous n’avez pas besoin de la persistance basée sur les cookies.</span><span class="sxs-lookup"><span data-stu-id="c3532-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="c3532-127">Toutefois, si vous souhaitez conserver temporairement ou définitivement les serveurs frontaux ou les pools frontaux Lync Server 2010, vous devez toujours utiliser la persistance basée sur les cookies, car elle est déployée et configurée pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c3532-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3532-128"><STRONG>Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin</STRONG>, aucun impact négatif n’en résultera.</span><span class="sxs-lookup"><span data-stu-id="c3532-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="c3532-129">Pour les déploiements qui **n’utiliseront pas** l’affinité basée sur les cookies :</span><span class="sxs-lookup"><span data-stu-id="c3532-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="c3532-p106">Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.</span><span class="sxs-lookup"><span data-stu-id="c3532-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="c3532-132">Pour les déploiements qui **utiliseront** l’affinité basée sur les cookies :</span><span class="sxs-lookup"><span data-stu-id="c3532-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="c3532-p107">Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.</span><span class="sxs-lookup"><span data-stu-id="c3532-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="c3532-135">Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly</span><span class="sxs-lookup"><span data-stu-id="c3532-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="c3532-136">Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration</span><span class="sxs-lookup"><span data-stu-id="c3532-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="c3532-137">Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)</span><span class="sxs-lookup"><span data-stu-id="c3532-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="c3532-p108">Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée</span><span class="sxs-lookup"><span data-stu-id="c3532-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3532-140">Les configurations classiques de l’équilibreur de charge matérielle utilisent l’affinité d’adresse source et une durée de vie de session de 20 min. TCP, ce qui convient pour les clients Lync Server et Lync 2013, car l’état de session est conservé via l’utilisation du client et/ou l’interaction entre les applications.</span><span class="sxs-lookup"><span data-stu-id="c3532-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="c3532-141">Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).</span><span class="sxs-lookup"><span data-stu-id="c3532-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c3532-p109">Les programmes d’équilibrage de la charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de la charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 fournit les paramètres spécifiques pour cela.</span><span class="sxs-lookup"><span data-stu-id="c3532-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="c3532-146">Pour plus d’informations sur les programmes d’équilibrage de la charge matérielle de tiers, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="c3532-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="c3532-147">La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :</span><span class="sxs-lookup"><span data-stu-id="c3532-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="c3532-148">Pour les VIP des services Web internes, définissez \_ la persistance de l’adresse source (port interne 80, 443) sur l’équilibreur de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="c3532-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="c3532-149">Pour Lync Server 2013, \_ la persistance de l’adresse source signifie que plusieurs connexions provenant d’une seule adresse IP sont toujours envoyées à un seul serveur pour maintenir l’état de la session.</span><span class="sxs-lookup"><span data-stu-id="c3532-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="c3532-150">Utilisez un délai d’inactivité TCP de 1 800 secondes.</span><span class="sxs-lookup"><span data-stu-id="c3532-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="c3532-p111">Sur le pare-feu situé entre le proxy inverse et le programme d’équilibrage de la charge matérielle du pool du tronçon suivant, créez une règle autorisant le trafic https: sur le port 4443, entre le proxy inverse et le programme d’équilibrage de la charge matérielle. Le programme d’équilibrage de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.</span><span class="sxs-lookup"><span data-stu-id="c3532-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3532-153">Pour en savoir plus sur la configuration de l’équilibreur de la charge matérielle, veuillez consulter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c3532-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="c3532-154">Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="c3532-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3532-155">Emplacement du client/de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c3532-155">Client/user location</span></span></th>
<th><span data-ttu-id="c3532-156">Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes</span><span class="sxs-lookup"><span data-stu-id="c3532-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="c3532-157">Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes</span><span class="sxs-lookup"><span data-stu-id="c3532-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3532-158">Lync Web App (utilisateurs internes et externes)</span><span class="sxs-lookup"><span data-stu-id="c3532-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="c3532-159">Appareil mobile (utilisateurs internes et externes)</span><span class="sxs-lookup"><span data-stu-id="c3532-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="c3532-160">Aucune affinité</span><span class="sxs-lookup"><span data-stu-id="c3532-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="c3532-161">Affinité des adresses sources</span><span class="sxs-lookup"><span data-stu-id="c3532-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3532-162">Lync Web App (utilisateurs externes uniquement)</span><span class="sxs-lookup"><span data-stu-id="c3532-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="c3532-163">Appareil mobile (utilisateurs internes et externes)</span><span class="sxs-lookup"><span data-stu-id="c3532-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="c3532-164">Aucune affinité</span><span class="sxs-lookup"><span data-stu-id="c3532-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="c3532-165">Affinité des adresses sources</span><span class="sxs-lookup"><span data-stu-id="c3532-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3532-166">Lync Web App (utilisateurs internes uniquement)</span><span class="sxs-lookup"><span data-stu-id="c3532-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="c3532-167">Appareil mobile (non déployé)</span><span class="sxs-lookup"><span data-stu-id="c3532-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="c3532-168">Aucune affinité</span><span class="sxs-lookup"><span data-stu-id="c3532-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="c3532-169">Affinité des adresses sources</span><span class="sxs-lookup"><span data-stu-id="c3532-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="c3532-170">Surveillance des ports pour les programmes d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="c3532-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="c3532-171">Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication.</span><span class="sxs-lookup"><span data-stu-id="c3532-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="c3532-172">Par exemple, si le service de serveur frontal (RTCSRV) s’arrête en raison de l’échec du serveur frontal ou du pool frontal, la surveillance charge matérielle doit également cesser de recevoir du trafic sur les services Web.</span><span class="sxs-lookup"><span data-stu-id="c3532-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="c3532-173">Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c3532-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="c3532-174">Pool d’utilisateurs du serveur frontal – interface interne charge matérielle</span><span class="sxs-lookup"><span data-stu-id="c3532-174">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3532-175">IP/Port virtuel</span><span class="sxs-lookup"><span data-stu-id="c3532-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="c3532-176">Port de nœud</span><span class="sxs-lookup"><span data-stu-id="c3532-176">Node Port</span></span></th>
<th><span data-ttu-id="c3532-177">Nœud Ordinateur/Écran</span><span class="sxs-lookup"><span data-stu-id="c3532-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="c3532-178">Profil de persistance</span><span class="sxs-lookup"><span data-stu-id="c3532-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="c3532-179">Notes</span><span class="sxs-lookup"><span data-stu-id="c3532-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3532-180">&lt;&gt;int_mco_443_vs Web de pool</span><span class="sxs-lookup"><span data-stu-id="c3532-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="c3532-181">443</span><span class="sxs-lookup"><span data-stu-id="c3532-181">443</span></span></p></td>
<td><p><span data-ttu-id="c3532-182">443</span><span class="sxs-lookup"><span data-stu-id="c3532-182">443</span></span></p></td>
<td><p><span data-ttu-id="c3532-183">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c3532-183">Front End</span></span></p>
<p><span data-ttu-id="c3532-184">5061</span><span class="sxs-lookup"><span data-stu-id="c3532-184">5061</span></span></p></td>
<td><p><span data-ttu-id="c3532-185">Source</span><span class="sxs-lookup"><span data-stu-id="c3532-185">Source</span></span></p></td>
<td><p><span data-ttu-id="c3532-186">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c3532-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3532-187">&lt;&gt;int_mco_80_vs Web de pool</span><span class="sxs-lookup"><span data-stu-id="c3532-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="c3532-188">80</span><span class="sxs-lookup"><span data-stu-id="c3532-188">80</span></span></p></td>
<td><p><span data-ttu-id="c3532-189">80</span><span class="sxs-lookup"><span data-stu-id="c3532-189">80</span></span></p></td>
<td><p><span data-ttu-id="c3532-190">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c3532-190">Front End</span></span></p>
<p><span data-ttu-id="c3532-191">5061</span><span class="sxs-lookup"><span data-stu-id="c3532-191">5061</span></span></p></td>
<td><p><span data-ttu-id="c3532-192">Source</span><span class="sxs-lookup"><span data-stu-id="c3532-192">Source</span></span></p></td>
<td><p><span data-ttu-id="c3532-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="c3532-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="c3532-194">Pool d’utilisateurs du serveur frontal – interface externe charge matérielle</span><span class="sxs-lookup"><span data-stu-id="c3532-194">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3532-195">IP/Port virtuel</span><span class="sxs-lookup"><span data-stu-id="c3532-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="c3532-196">Port de nœud</span><span class="sxs-lookup"><span data-stu-id="c3532-196">Node Port</span></span></th>
<th><span data-ttu-id="c3532-197">Nœud Ordinateur/Écran</span><span class="sxs-lookup"><span data-stu-id="c3532-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="c3532-198">Profil de persistance</span><span class="sxs-lookup"><span data-stu-id="c3532-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="c3532-199">Notes</span><span class="sxs-lookup"><span data-stu-id="c3532-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3532-200">&lt;web_mco_443_vs de pool &gt;</span><span class="sxs-lookup"><span data-stu-id="c3532-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="c3532-201">443</span><span class="sxs-lookup"><span data-stu-id="c3532-201">443</span></span></p></td>
<td><p><span data-ttu-id="c3532-202">4443</span><span class="sxs-lookup"><span data-stu-id="c3532-202">4443</span></span></p></td>
<td><p><span data-ttu-id="c3532-203">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c3532-203">Front End</span></span></p>
<p><span data-ttu-id="c3532-204">5061</span><span class="sxs-lookup"><span data-stu-id="c3532-204">5061</span></span></p></td>
<td><p><span data-ttu-id="c3532-205">Aucune</span><span class="sxs-lookup"><span data-stu-id="c3532-205">None</span></span></p></td>
<td><p><span data-ttu-id="c3532-206">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c3532-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3532-207">&lt;web_mco_80_vs de pool &gt;</span><span class="sxs-lookup"><span data-stu-id="c3532-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="c3532-208">80</span><span class="sxs-lookup"><span data-stu-id="c3532-208">80</span></span></p></td>
<td><p><span data-ttu-id="c3532-209">8080</span><span class="sxs-lookup"><span data-stu-id="c3532-209">8080</span></span></p></td>
<td><p><span data-ttu-id="c3532-210">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c3532-210">Front End</span></span></p>
<p><span data-ttu-id="c3532-211">5061</span><span class="sxs-lookup"><span data-stu-id="c3532-211">5061</span></span></p></td>
<td><p><span data-ttu-id="c3532-212">Aucune</span><span class="sxs-lookup"><span data-stu-id="c3532-212">None</span></span></p></td>
<td><p><span data-ttu-id="c3532-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="c3532-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

