---
title: 'Lync Server 2013 : récupération d’urgence de serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="41948-102">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41948-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41948-103">_**Dernière modification de la rubrique :** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="41948-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="41948-p101">Comme avec les autres rôles serveur, le meilleur moyen d’offrir une haute disponibilité pour vos serveurs Edge consiste à déployer plusieurs serveurs Edge dans des pools pour chaque site. Si un serveur Edge tombe en panne, les autres serveurs dans le pool continueront à assurer les services Edge.</span><span class="sxs-lookup"><span data-stu-id="41948-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="41948-p102">Pour activer les procédures de récupération d’urgence, vous devez avoir déployé des pools de serveurs Edge distincts sur chaque site. Vous n’avez pas besoin d’associer par deux des pools Edge de façon explicite comme vous le feriez avec des pools frontaux, mais le fait de disposer de plusieurs pools Edge permet de maintenir l’activité si un pool Edge entier tombe en panne. Les sections suivantes décrivent la récupération d’urgence pour les différentes fonctions des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="41948-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="41948-109">Accès à distance</span><span class="sxs-lookup"><span data-stu-id="41948-109">Remote Access</span></span>

<span data-ttu-id="41948-110">Si vous avez plusieurs sites, chacun d’eux disposant d’un pool de serveurs Edge et que l’un des pools de serveurs Edge échoue, les services d’accès à distance continuent de fonctionner sans avoir besoin de l’intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="41948-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="41948-111">Lors de la création de pools de serveurs Edge dans des sites différents, vous ne pouvez pas utiliser le même nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="41948-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="41948-112">Chaque pool Edge doit avoir des noms de domaine complets uniques (internes et externes).</span><span class="sxs-lookup"><span data-stu-id="41948-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="41948-113">Les pools de serveurs Edge n’utilisent pas de règles de publication de proxy inverse pour communiquer avec les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="41948-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="41948-114">Le basculement automatique se produit lorsque le client interroge à nouveau les enregistrements du service DNS d’accès à distance et que les utilisateurs distants sont routés vers les serveurs Edge dans un autre site.</span><span class="sxs-lookup"><span data-stu-id="41948-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="41948-115">Le client tente de faire chaque nom de domaine complet Edge externe en fonction de la priorité des enregistrements SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="41948-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41948-116">Pour que le basculement fonctionne correctement, assurez-vous que le pare-feu autorise les serveurs frontaux de chaque pool à communiquer avec tous les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="41948-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="41948-117">Fédération</span><span class="sxs-lookup"><span data-stu-id="41948-117">Federation</span></span>

<span data-ttu-id="41948-118">Pour les relations de Fédération avec d’autres organisations exécutant Lync Server, les demandes de Fédération entrantes continueront de fonctionner aussi longtemps que vous avez des solutions comme géo-DNS GTM.</span><span class="sxs-lookup"><span data-stu-id="41948-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="41948-119">Il est important de comprendre que le basculement de Fédération ne fournit pas de basculement avec la priorité dans les enregistrements SRV.</span><span class="sxs-lookup"><span data-stu-id="41948-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="41948-120">Une solution fournie précédemment peut vous aider à fournir des fonctionnalités de récupération d’urgence pour la Fédération entrante.</span><span class="sxs-lookup"><span data-stu-id="41948-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="41948-121">La fédération sortante est toujours configurée par le biais d’un pool ou d’un serveur Edge publié dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="41948-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="41948-122">Si ce pool Edge est tombé en panne, vous devez utiliser le Générateur de topologie pour changer l’itinéraire de la fédération sortante afin d’utiliser un pool Edge en état de fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="41948-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="41948-123">Pour plus d’informations, reportez-vous à [basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="41948-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="41948-124">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="41948-124">XMPP Federation</span></span>

<span data-ttu-id="41948-125">Concernant la fédération XMPP, le trafic entrant et sortant s’arrêtera si le pool Edge qui est désigné comme passerelle de fédération XMPP tombe en panne.</span><span class="sxs-lookup"><span data-stu-id="41948-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="41948-126">Pour que la fédération XMPP fonctionne de nouveau, vous devez configurer la fédération XMPP de sorte qu’elle utilise un autre pool Edge.</span><span class="sxs-lookup"><span data-stu-id="41948-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="41948-127">Pour plus d’informations, reportez-vous à [basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="41948-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="41948-128">Le pool Edge tombe en panne mais le pool frontal fonctionne toujours</span><span class="sxs-lookup"><span data-stu-id="41948-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="41948-129">Si un pool Edge tombe en panne sur un site, alors que le pool frontal de ce site fonctionne toujours, vous devez configurer le pool frontal pour qu’il utilise un autre pool Edge d’un autre site pendant que le premier pool Edge est en panne.</span><span class="sxs-lookup"><span data-stu-id="41948-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="41948-130">Pour plus d’informations, consultez [la rubrique Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="41948-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

