---
title: 'Lync Server 2013 : Récupération d’urgence de serveur Edge'
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
ms.openlocfilehash: 431b4853407b65bca2b029626cc5659490a493d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="92417-102">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92417-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92417-103">_**Dernière modification de la rubrique :** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="92417-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="92417-104">Comme pour les autres rôles de serveur, la meilleure façon de garantir la disponibilité de votre serveur Edge consiste à déployer plusieurs serveurs Edge dans les pools de chaque site.</span><span class="sxs-lookup"><span data-stu-id="92417-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="92417-105">Si un serveur Edge est hors service, les autres serveurs du pool continuent de fournir les services Edge.</span><span class="sxs-lookup"><span data-stu-id="92417-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="92417-106">Pour activer les procédures de récupération d’urgence, vous devez déployer des pools de serveurs de bord séparés sur des sites distincts.</span><span class="sxs-lookup"><span data-stu-id="92417-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="92417-107">Vous n’avez pas besoin de jumeler explicitement les pools d’arête comme pour les pools frontaux, mais le fait de disposer de plusieurs pools de bords vous permet d’assurer la mise en place de l’intégralité d’un pool de périphérie.</span><span class="sxs-lookup"><span data-stu-id="92417-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="92417-108">Les sections suivantes fournissent des détails sur la récupération après sinistre pour les diverses fonctions des serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="92417-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="92417-109">Accès à distance</span><span class="sxs-lookup"><span data-stu-id="92417-109">Remote Access</span></span>

<span data-ttu-id="92417-110">Si vous disposez de plusieurs sites, chacun avec un pool de serveurs Edge et l’ensemble d’un pool de périphérie tombe en panne, les services d’accès à distance continuent de fonctionner sans intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="92417-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="92417-111">Vous ne pouvez pas utiliser le même nom de domaine complet lors de la création de pools Edge dans différents sites.</span><span class="sxs-lookup"><span data-stu-id="92417-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="92417-112">Chaque pool Edge doit être doté d’un FQDN unique (interne et externe).</span><span class="sxs-lookup"><span data-stu-id="92417-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="92417-113">Les pools de bords n’utilisent pas les règles de publication de proxy inverse pour parler aux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="92417-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="92417-114">Le basculement automatique se produit lorsque le client réactive les enregistrements du service DNS d’accès à distance et que les utilisateurs distants sont routés vers les serveurs de périphérie d’un autre site.</span><span class="sxs-lookup"><span data-stu-id="92417-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="92417-115">Le client tente de chaque nom de domaine complet de bord externe en fonction de la priorité des enregistrements SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="92417-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92417-116">Pour que le basculement fonctionne sans problèmes, assurez-vous que le pare-feu permet aux serveurs frontaux de chaque pool de communiquer avec tous les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="92417-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="92417-117">Fédération</span><span class="sxs-lookup"><span data-stu-id="92417-117">Federation</span></span>

<span data-ttu-id="92417-118">Pour les relations de Fédération avec d’autres organisations exécutant Lync Server, les demandes de Fédération entrante continuent de fonctionner aussi longtemps que vous disposez de solutions comme géo-DNS GTM.</span><span class="sxs-lookup"><span data-stu-id="92417-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="92417-119">Il est important de comprendre que le basculement de la Fédération ne fournit pas de basculement avec la priorité dans les enregistrements SRV.</span><span class="sxs-lookup"><span data-stu-id="92417-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="92417-120">Une solution fournie précédemment peut vous aider à fournir des fonctionnalités de reprise après sinistre pour la Fédération entrante.</span><span class="sxs-lookup"><span data-stu-id="92417-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="92417-121">La Fédération sortante est toujours configurée par le biais d’un pool d’organisations ou d’un serveur de périphérie publié au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="92417-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="92417-122">Dans le cas contraire, vous devez utiliser le générateur de topologie pour modifier l’itinéraire de Fédération sortant et utiliser un pool de bords qui est toujours en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="92417-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="92417-123">Pour plus d’informations, reportez-vous à [échec du pool Edge utilisé pour la Fédération Lync Server dans Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="92417-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="92417-124">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="92417-124">XMPP Federation</span></span>

<span data-ttu-id="92417-125">Pour la Fédération XMPP, le trafic entrant et sortant échouera si le pool de périphériques de périmètre désigné comme passerelle de Fédération XMPP s’arrête.</span><span class="sxs-lookup"><span data-stu-id="92417-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="92417-126">Pour faire en sorte que la Fédération XMPP fonctionne à nouveau, vous devez modifier la Fédération de XMPP pour utiliser un pool de périphérie différent.</span><span class="sxs-lookup"><span data-stu-id="92417-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="92417-127">Pour plus d’informations, reportez-vous à [échec du pool Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="92417-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="92417-128">Le pool Edge ne fonctionne pas, mais le pool frontal s’exécute toujours</span><span class="sxs-lookup"><span data-stu-id="92417-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="92417-129">Si un pool de périphériques ne fonctionne pas sur un site, mais que le pool frontal sur ce site est toujours en cours d’exécution, vous devez modifier le pool frontal pour utiliser un pool de périphérie différent sur un autre site lorsque ce dernier est en bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="92417-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="92417-130">Pour plus d’informations, reportez-vous à [la section changement du pool de bords associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="92417-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

