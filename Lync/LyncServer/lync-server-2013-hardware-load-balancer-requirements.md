---
title: Configuration requise pour l’équilibreur de charge matérielle Lync Server 2013
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
ms.openlocfilehash: c89c600c822bc4e830bf60ed8131f747172018e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="35558-102">Configuration requise pour le programme d’équilibrage de la charge matérielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35558-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35558-103">_**Dernière modification de la rubrique :** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="35558-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="35558-104">La topologie Edge consolidée Lync Server 2013 est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements qui se fédéreront principalement avec d’autres organisations utilisant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35558-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="35558-105">Si, dans l’un des scénarios suivants, la haute disponibilité est requise, vous devez utiliser un programme d’équilibrage de la charge matérielle sur les pools de serveurs Edge pour prendre en charge ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="35558-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="35558-106">Fédération avec les organisations qui utilisent Office Communications Server 2007 R2 ou Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="35558-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="35558-107">Messagerie unifiée Exchange pour les utilisateurs distants utilisant la messagerie unifiée Exchange avant Exchange 2010 avec SP1</span><span class="sxs-lookup"><span data-stu-id="35558-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="35558-108">connectivité avec les utilisateurs de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="35558-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35558-p102">L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="35558-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="35558-p103">Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne.</span><span class="sxs-lookup"><span data-stu-id="35558-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="35558-113">Le protocole NAT DSR (direct Server Return) n’est pas pris en charge avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35558-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="35558-114">Pour déterminer si votre programme d’équilibrage de la charge matérielle prend en charge les fonctionnalités requises par Lync Server 2013, voir « partenaires d’équilibrage de charge [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)lync Server 2010 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="35558-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="35558-115">Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V</span><span class="sxs-lookup"><span data-stu-id="35558-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="35558-116">Voici la configuration requise pour l’équilibreur de charge matérielle pour les serveurs Edge exécutant le service Edge A/V :</span><span class="sxs-lookup"><span data-stu-id="35558-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="35558-p104">Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux, afin de rendre la transmission plus efficace.</span><span class="sxs-lookup"><span data-stu-id="35558-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="35558-119">Désactivez le nagling TCP pour la plage de ports externes 50 000 – 59 999.</span><span class="sxs-lookup"><span data-stu-id="35558-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="35558-120">N’utilisez pas NAT sur le pare-feu interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="35558-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="35558-121">L’interface interne Edge doit se trouver sur un autre réseau que l’interface externe Edge Server, et le routage entre elles doit être désactivé.</span><span class="sxs-lookup"><span data-stu-id="35558-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="35558-122">L’interface externe du serveur Edge exécutant le service Edge A/V doit utiliser des adresses IP publiquement routables et aucune traduction d’adresses réseau ou NAT sur les adresses IP externes du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="35558-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="35558-123">Exigences relatives au programme d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="35558-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="35558-124">Les exigences en matière d’affinité basée sur les cookies sont considérablement réduites dans Lync Server 2013 pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="35558-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="35558-125">Si vous déployez Lync Server 2013 et que vous ne conservez pas de serveurs frontaux ou de pools frontaux Lync Server 2010, vous n’avez pas besoin de la persistance basée sur les cookies.</span><span class="sxs-lookup"><span data-stu-id="35558-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="35558-126">Toutefois, si vous souhaitez conserver temporairement ou définitivement les serveurs frontaux ou les pools frontaux Lync Server 2010, vous devez toujours utiliser la persistance basée sur les cookies, car elle est déployée et configurée pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="35558-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35558-127"><STRONG>Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin</STRONG>, aucun impact négatif n’en résultera.</span><span class="sxs-lookup"><span data-stu-id="35558-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="35558-128">Pour les déploiements qui **n’utiliseront pas** l’affinité basée sur les cookies :</span><span class="sxs-lookup"><span data-stu-id="35558-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="35558-129">Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True.</span><span class="sxs-lookup"><span data-stu-id="35558-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="35558-130">Cela garantit que l’URL d’origine sera transférée.</span><span class="sxs-lookup"><span data-stu-id="35558-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="35558-131">Pour les déploiements qui **utiliseront** l’affinité basée sur les cookies :</span><span class="sxs-lookup"><span data-stu-id="35558-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="35558-p107">Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.</span><span class="sxs-lookup"><span data-stu-id="35558-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="35558-134">Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly</span><span class="sxs-lookup"><span data-stu-id="35558-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="35558-135">Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration</span><span class="sxs-lookup"><span data-stu-id="35558-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="35558-136">Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)</span><span class="sxs-lookup"><span data-stu-id="35558-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="35558-p108">Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée</span><span class="sxs-lookup"><span data-stu-id="35558-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35558-139">Les configurations classiques de l’équilibreur de charge matérielle utilisent l’affinité d’adresse source et une durée de vie de session de 20 min. TCP, ce qui convient pour les clients Lync Server et Lync 2013, car l’état de session est conservé via l’utilisation du client et/ou l’interaction entre les applications.</span><span class="sxs-lookup"><span data-stu-id="35558-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="35558-140">Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).</span><span class="sxs-lookup"><span data-stu-id="35558-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="35558-p109">Les programmes d’équilibrage de la charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de la charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 fournit les paramètres spécifiques pour cela.</span><span class="sxs-lookup"><span data-stu-id="35558-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="35558-145">Pour plus d’informations sur les programmes d’équilibrage de la charge matérielle de tiers, voir<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="35558-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="35558-146">La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :</span><span class="sxs-lookup"><span data-stu-id="35558-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="35558-147">Pour les VIP des services Web internes,\_définissez la persistance de l’adresse source (port interne 80, 443) sur l’équilibreur de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="35558-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="35558-148">Pour Lync Server 2013, la\_persistance de l’adresse source signifie que plusieurs connexions provenant d’une seule adresse IP sont toujours envoyées à un seul serveur pour maintenir l’état de la session.</span><span class="sxs-lookup"><span data-stu-id="35558-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="35558-149">Utilisez un délai d’inactivité TCP de 1 800 secondes.</span><span class="sxs-lookup"><span data-stu-id="35558-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="35558-p111">Sur le pare-feu situé entre le proxy inverse et le programme d’équilibrage de la charge matérielle du pool du tronçon suivant, créez une règle autorisant le trafic https: sur le port 4443, entre le proxy inverse et le programme d’équilibrage de la charge matérielle. Le programme d’équilibrage de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.</span><span class="sxs-lookup"><span data-stu-id="35558-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35558-152">Pour en savoir plus sur la configuration de l’équilibreur de la charge matérielle, veuillez consulter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="35558-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="35558-153">Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="35558-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35558-154">Emplacement du client/de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="35558-154">Client/user location</span></span></th>
<th><span data-ttu-id="35558-155">Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes</span><span class="sxs-lookup"><span data-stu-id="35558-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="35558-156">Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes</span><span class="sxs-lookup"><span data-stu-id="35558-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35558-157">Lync Web App (utilisateurs internes et externes)</span><span class="sxs-lookup"><span data-stu-id="35558-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="35558-158">Appareil mobile (utilisateurs internes et externes)</span><span class="sxs-lookup"><span data-stu-id="35558-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="35558-159">Aucune affinité</span><span class="sxs-lookup"><span data-stu-id="35558-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="35558-160">Affinité des adresses sources</span><span class="sxs-lookup"><span data-stu-id="35558-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35558-161">Lync Web App (utilisateurs externes uniquement)</span><span class="sxs-lookup"><span data-stu-id="35558-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="35558-162">Appareil mobile (utilisateurs internes et externes)</span><span class="sxs-lookup"><span data-stu-id="35558-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="35558-163">Aucune affinité</span><span class="sxs-lookup"><span data-stu-id="35558-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="35558-164">Affinité des adresses sources</span><span class="sxs-lookup"><span data-stu-id="35558-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35558-165">Lync Web App (utilisateurs internes uniquement)</span><span class="sxs-lookup"><span data-stu-id="35558-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="35558-166">Appareil mobile (non déployé)</span><span class="sxs-lookup"><span data-stu-id="35558-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="35558-167">Aucune affinité</span><span class="sxs-lookup"><span data-stu-id="35558-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="35558-168">Affinité des adresses sources</span><span class="sxs-lookup"><span data-stu-id="35558-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="35558-169">Surveillance des ports pour les programmes d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="35558-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="35558-170">Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication.</span><span class="sxs-lookup"><span data-stu-id="35558-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="35558-171">Par exemple, si le service de serveur frontal (RTCSRV) s’arrête en raison de l’échec du serveur frontal ou du pool frontal, la surveillance charge matérielle doit également cesser de recevoir du trafic sur les services Web.</span><span class="sxs-lookup"><span data-stu-id="35558-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="35558-172">Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="35558-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="35558-173">Pool d’utilisateurs du serveur frontal – interface interne charge matérielle</span><span class="sxs-lookup"><span data-stu-id="35558-173">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="35558-174">IP/Port virtuel</span><span class="sxs-lookup"><span data-stu-id="35558-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="35558-175">Port de nœud</span><span class="sxs-lookup"><span data-stu-id="35558-175">Node Port</span></span></th>
<th><span data-ttu-id="35558-176">Nœud Ordinateur/Écran</span><span class="sxs-lookup"><span data-stu-id="35558-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="35558-177">Profil de persistance</span><span class="sxs-lookup"><span data-stu-id="35558-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="35558-178">Notes</span><span class="sxs-lookup"><span data-stu-id="35558-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35558-179">&lt;int_mco_443_vs&gt;Web de pool</span><span class="sxs-lookup"><span data-stu-id="35558-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="35558-180">443</span><span class="sxs-lookup"><span data-stu-id="35558-180">443</span></span></p></td>
<td><p><span data-ttu-id="35558-181">443</span><span class="sxs-lookup"><span data-stu-id="35558-181">443</span></span></p></td>
<td><p><span data-ttu-id="35558-182">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="35558-182">Front End</span></span></p>
<p><span data-ttu-id="35558-183">5061</span><span class="sxs-lookup"><span data-stu-id="35558-183">5061</span></span></p></td>
<td><p><span data-ttu-id="35558-184">Source</span><span class="sxs-lookup"><span data-stu-id="35558-184">Source</span></span></p></td>
<td><p><span data-ttu-id="35558-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="35558-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35558-186">&lt;int_mco_80_vs&gt;Web de pool</span><span class="sxs-lookup"><span data-stu-id="35558-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="35558-187">80</span><span class="sxs-lookup"><span data-stu-id="35558-187">80</span></span></p></td>
<td><p><span data-ttu-id="35558-188">80</span><span class="sxs-lookup"><span data-stu-id="35558-188">80</span></span></p></td>
<td><p><span data-ttu-id="35558-189">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="35558-189">Front End</span></span></p>
<p><span data-ttu-id="35558-190">5061</span><span class="sxs-lookup"><span data-stu-id="35558-190">5061</span></span></p></td>
<td><p><span data-ttu-id="35558-191">Source</span><span class="sxs-lookup"><span data-stu-id="35558-191">Source</span></span></p></td>
<td><p><span data-ttu-id="35558-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="35558-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="35558-193">Pool d’utilisateurs du serveur frontal – interface externe charge matérielle</span><span class="sxs-lookup"><span data-stu-id="35558-193">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="35558-194">IP/Port virtuel</span><span class="sxs-lookup"><span data-stu-id="35558-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="35558-195">Port de nœud</span><span class="sxs-lookup"><span data-stu-id="35558-195">Node Port</span></span></th>
<th><span data-ttu-id="35558-196">Nœud Ordinateur/Écran</span><span class="sxs-lookup"><span data-stu-id="35558-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="35558-197">Profil de persistance</span><span class="sxs-lookup"><span data-stu-id="35558-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="35558-198">Notes</span><span class="sxs-lookup"><span data-stu-id="35558-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35558-199">&lt;web_mco_443_vs&gt;de pool</span><span class="sxs-lookup"><span data-stu-id="35558-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="35558-200">443</span><span class="sxs-lookup"><span data-stu-id="35558-200">443</span></span></p></td>
<td><p><span data-ttu-id="35558-201">4443</span><span class="sxs-lookup"><span data-stu-id="35558-201">4443</span></span></p></td>
<td><p><span data-ttu-id="35558-202">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="35558-202">Front End</span></span></p>
<p><span data-ttu-id="35558-203">5061</span><span class="sxs-lookup"><span data-stu-id="35558-203">5061</span></span></p></td>
<td><p><span data-ttu-id="35558-204">Aucun</span><span class="sxs-lookup"><span data-stu-id="35558-204">None</span></span></p></td>
<td><p><span data-ttu-id="35558-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="35558-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35558-206">&lt;web_mco_80_vs&gt;de pool</span><span class="sxs-lookup"><span data-stu-id="35558-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="35558-207">80</span><span class="sxs-lookup"><span data-stu-id="35558-207">80</span></span></p></td>
<td><p><span data-ttu-id="35558-208">8080</span><span class="sxs-lookup"><span data-stu-id="35558-208">8080</span></span></p></td>
<td><p><span data-ttu-id="35558-209">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="35558-209">Front End</span></span></p>
<p><span data-ttu-id="35558-210">5061</span><span class="sxs-lookup"><span data-stu-id="35558-210">5061</span></span></p></td>
<td><p><span data-ttu-id="35558-211">Aucun</span><span class="sxs-lookup"><span data-stu-id="35558-211">None</span></span></p></td>
<td><p><span data-ttu-id="35558-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="35558-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

