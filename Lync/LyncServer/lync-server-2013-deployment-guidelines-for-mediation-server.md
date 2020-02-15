---
title: 'Lync Server 2013 : instructions de déploiement pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0404590ab5b3208de989093df7ede55a3aee2f54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="bc60d-102">Instructions de déploiement pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc60d-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc60d-103">_**Dernière modification de la rubrique :** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="bc60d-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="bc60d-104">Cette rubrique décrit les instructions de planification pour le déploiement d’un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="bc60d-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="bc60d-105">Après avoir examiné ces instructions, nous vous recommandons d’utiliser l’outil de planification pour créer et afficher d’autres topologies possibles, qui peuvent servir de modèles pour ce que la topologie personnalisée finale que vous décidez de déployer ressemblerait.</span><span class="sxs-lookup"><span data-stu-id="bc60d-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="bc60d-106">Serveur de médiation colocalisé ou autonome ?</span><span class="sxs-lookup"><span data-stu-id="bc60d-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="bc60d-107">Le serveur de médiation est colocalisé par défaut sur le serveur Standard Edition Server ou frontal dans un pool frontal sur les sites centraux.</span><span class="sxs-lookup"><span data-stu-id="bc60d-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="bc60d-108">Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendent des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bc60d-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="bc60d-109">Le nombre d’homologues de passerelle contrôlés par le pool de serveurs de médiation ;</span><span class="sxs-lookup"><span data-stu-id="bc60d-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="bc60d-110">Les périodes de trafic à haut volume via ces passerelles ;</span><span class="sxs-lookup"><span data-stu-id="bc60d-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="bc60d-111">Le pourcentage d’appels qui sont des appels dont le média contournent le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="bc60d-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="bc60d-112">Lors de la planification, veillez à prendre en compte les exigences en matière de traitement des médias pour les appels PSTN et les conférences A/V qui ne sont pas configurées pour la déviation du trafic multimédia, ainsi que le traitement nécessaire pour gérer les interactions de signalisation pour le nombre d’appels d’heure de pointe qui doivent être pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bc60d-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="bc60d-113">S’il n’y a pas assez d’UC, vous devez déployer un pool autonome de serveurs de médiation ; les passerelles PSTN, IP-PBX et SBCs doivent être divisées en sous-ensembles contrôlés par les serveurs de médiation colocalisés dans un pool et les serveurs de médiation autonomes dans un ou plusieurs pools autonomes.</span><span class="sxs-lookup"><span data-stu-id="bc60d-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="bc60d-114">Si vous avez déployé des passerelles PSTN, des systèmes IP-PBX ou des contrôleurs de frontière de session (SBC) qui ne prennent pas en charge les fonctionnalités correctes pour interagir avec un pool de serveurs de médiation, y compris les éléments suivants, ils devront être associés à un pool autonome composé d’un serveur de médiation unique :</span><span class="sxs-lookup"><span data-stu-id="bc60d-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="bc60d-115">Effectuer l’équilibrage de charge DNS (Domain Name System) de couche réseau entre les serveurs de médiation d’un pool (ou acheminer uniformément le trafic de manière uniforme vers tous les serveurs de médiation d’un pool)</span><span class="sxs-lookup"><span data-stu-id="bc60d-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="bc60d-116">Accepter le trafic d’un serveur de médiation dans un pool</span><span class="sxs-lookup"><span data-stu-id="bc60d-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="bc60d-117">Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si colocaliser le serveur de médiation avec votre pool frontal peut gérer la charge.</span><span class="sxs-lookup"><span data-stu-id="bc60d-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="bc60d-118">Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="bc60d-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="bc60d-119">Considérations relatives au site central et aux sites de succursale</span><span class="sxs-lookup"><span data-stu-id="bc60d-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="bc60d-p105">Les serveurs de médiation sur le site central peuvent être utilisés pour router les appels sur les sites de succursale pour les passerelles PSTN ou les IP-PBX. Si vous déployez des jonctions SIP, cependant, vous devez déployer un serveur de médiation sur le site où s’arrête chaque jonction. Le fait de disposer d’un serveur de médiation sur le site central qui route les appels sur un site de succursale pour un IP/PBX ou une passerelle PSTN ne requiert pas l’utilisation du contournement de média. Toutefois, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès des médias et par conséquent, obtenir une qualité des médias améliorée du fait que le chemin d’accès des médias n’est plus nécessaire pour suivre le chemin de signalisation. Le contournement de média réduira également la charge de traitement sur le pool.</span><span class="sxs-lookup"><span data-stu-id="bc60d-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc60d-125">Le contournement de média ne fonctionnera pas avec chaque passerelle PSTN, système IP-PBX et SBC.</span><span class="sxs-lookup"><span data-stu-id="bc60d-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="bc60d-126">Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="bc60d-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="bc60d-127">La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à.</span><span class="sxs-lookup"><span data-stu-id="bc60d-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="bc60d-128">Si la résistance de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle doit être déployé sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="bc60d-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="bc60d-129">(L’hypothèse de résistance de site de succursale est que la présence et la Conférence ne sont pas résilientes sur le site.) Pour obtenir des conseils sur la planification de site de succursale pour la voix, voir [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="bc60d-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="bc60d-130">Pour les interactions avec un système IP-PBX, si le système IP-PBX ne prend pas correctement en charge les interactions de médias précoces avec plusieurs boîtes de dialogue précoces et RFC 3960, il peut y avoir un découpage des premiers mots du message d’accueil pour les appels entrants depuis le PBX IP vers des points de terminaison Lync.</span><span class="sxs-lookup"><span data-stu-id="bc60d-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="bc60d-131">Ce comportement peut s’aggraver si un serveur de médiation sur le site central achemine les appels pour un IP-PBX là où s’arrête l’itinéraire sur un site de succursale, car la signalisation a besoin de plus de temps pour se terminer.</span><span class="sxs-lookup"><span data-stu-id="bc60d-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="bc60d-132">Si vous êtes confronté à ce problème, le déploiement d’un serveur de médiation sur le site de succursale constitue le seul moyen de réduire le découpage des premiers mots.</span><span class="sxs-lookup"><span data-stu-id="bc60d-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="bc60d-133">Pour finir, si votre site central comporte un TDM PBX ou que votre IP-PBX ne supprime pas le besoin d’une passerelle PSTN, vous devez alors déployer une passerelle sur l’itinéraire d’appel qui se connecte au serveur de médiation et au PBX.</span><span class="sxs-lookup"><span data-stu-id="bc60d-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc60d-134">Pour améliorer les performances multimédias d’un serveur de médiation autonome, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="bc60d-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="bc60d-135">RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="bc60d-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="bc60d-136">Pour plus d’informations, reportez-vous à la section « améliorations de l' <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>évolutivité côté réception dans Windows Server » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="bc60d-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="bc60d-137">Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="bc60d-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

