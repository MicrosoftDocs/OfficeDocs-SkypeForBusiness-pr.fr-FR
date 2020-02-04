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
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="4502a-102">Recommandations en matière de déploiement pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4502a-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4502a-103">_**Dernière modification de la rubrique :** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="4502a-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="4502a-104">Cette rubrique décrit les recommandations en matière de planification pour le déploiement de médiation Server.</span><span class="sxs-lookup"><span data-stu-id="4502a-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="4502a-105">Après avoir examiné ces recommandations, nous vous conseillons d’utiliser l’outil de planification pour créer et afficher des topologies de remplacement possibles, qui peuvent servir de modèles pour la topologie de déploiement finale que vous décidez de déployer.</span><span class="sxs-lookup"><span data-stu-id="4502a-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="4502a-106">Serveur de médiation autonome ou colocalisé</span><span class="sxs-lookup"><span data-stu-id="4502a-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="4502a-107">Le serveur de médiation est par défaut colocalisé sur le serveur principal ou le serveur frontal standard dans un pool frontal de sites centraux.</span><span class="sxs-lookup"><span data-stu-id="4502a-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="4502a-108">Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendront des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4502a-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="4502a-109">Nombre d’homologues de passerelle que le pool de serveurs de médiation contrôle</span><span class="sxs-lookup"><span data-stu-id="4502a-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="4502a-110">des périodes de trafic aux heures de pointe via ces passerelles ;</span><span class="sxs-lookup"><span data-stu-id="4502a-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="4502a-111">Pourcentage d’appels dont le média ignore le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="4502a-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="4502a-112">Lors de la planification, veillez à prendre en compte les exigences de traitement multimédia pour les appels RTC et les conférences A/V qui ne sont pas configurées pour le recours au contenu multimédia, ainsi que le traitement requis pour gérer les interactions de signalisation en fonction du nombre d’appels vers des heures de disponibilité qui doivent être pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4502a-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="4502a-113">S’il n’y a pas assez d’UC, vous devez déployer un pool autonome de serveurs de médiation. les passerelles RTC, IP PBX et SBCs doivent être divisées en sous-ensembles contrôlés par les serveurs de médiation colocalisés dans un pool et les serveurs de médiation autonomes dans un ou plusieurs pools autonomes.</span><span class="sxs-lookup"><span data-stu-id="4502a-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="4502a-114">Si vous avez déployé des passerelles RTC, des PBX IP ou des contrôleurs de frontière de session (SBCs) qui ne prennent pas en charge les fonctionnalités appropriées pour interagir avec un pool de serveurs de médiation, y compris les suivants, ils devront être associés à un pool autonome composé de d’un serveur de médiation unique :</span><span class="sxs-lookup"><span data-stu-id="4502a-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="4502a-115">Effectuer l’équilibrage de charge DNS (Layer Domain Name System) entre les serveurs de médiation d’un pool (ou sinon, le trafic est uniformément routé vers tous les serveurs de médiation d’un pool)</span><span class="sxs-lookup"><span data-stu-id="4502a-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="4502a-116">Accepter le trafic de n’importe quel serveur de médiation dans un pool</span><span class="sxs-lookup"><span data-stu-id="4502a-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="4502a-117">Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si collocating du serveur de médiation avec votre pool frontal peut gérer le chargement.</span><span class="sxs-lookup"><span data-stu-id="4502a-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="4502a-118">Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="4502a-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="4502a-119">Aspects relatifs au site central et aux sites de succursale</span><span class="sxs-lookup"><span data-stu-id="4502a-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="4502a-120">Les serveurs de médiation sur le site central peuvent être utilisés pour acheminer les appels pour les PBX IP ou les passerelles RTC dans les sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="4502a-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="4502a-121">Toutefois, si vous déployez des Trunks SIP, vous devez déployer un serveur de médiation sur le site où chaque Trunk est arrêté.</span><span class="sxs-lookup"><span data-stu-id="4502a-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="4502a-122">Le fait de disposer d’un serveur de médiation au niveau du site central pour les appels pour un PBX IP ou une passerelle RTC sur un site de succursale ne nécessite pas l’utilisation de la fonctionnalité de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="4502a-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="4502a-123">Toutefois, si vous pouvez activer la dérivation multimédia, cela réduit la latence du chemin multimédia et, par conséquent, entraîne une meilleure qualité multimédia, car le chemin multimédia n’est plus nécessaire pour suivre le chemin d’accès de signalisation.</span><span class="sxs-lookup"><span data-stu-id="4502a-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="4502a-124">La déviation du trafic multimédia réduira également la charge de traitement sur le pool.</span><span class="sxs-lookup"><span data-stu-id="4502a-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4502a-125">La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC.</span><span class="sxs-lookup"><span data-stu-id="4502a-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="4502a-126">Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="4502a-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="4502a-127">La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span><span class="sxs-lookup"><span data-stu-id="4502a-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="4502a-128">Si la résilience du site de succursale est requise, il est nécessaire d’avoir une branche ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle dans le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="4502a-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="4502a-129">(L’hypothèse de la résilience du site de succursale est que la présence et les conférences ne sont pas résilientes sur le site.) Pour obtenir des instructions sur la planification du site de succursale pour les appels vocaux, voir [planification de la résilience vocale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="4502a-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="4502a-130">S’il s’agit d’interactions avec un PBX IP, si ce n’est 3960 pas le cas, vous pouvez découper les premiers mots du message d’accueil pour les appels entrants du PBX IP vers les points de terminaison de Lync.</span><span class="sxs-lookup"><span data-stu-id="4502a-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="4502a-131">Ce comportement peut être plus sérieux si un serveur de médiation sur un site central effectue le routage des appels pour un PBX IP à l’endroit où l’itinéraire se termine sur un site de succursale, car une plus grande période est nécessaire pour que le signalement s’exécute.</span><span class="sxs-lookup"><span data-stu-id="4502a-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="4502a-132">Si vous subissez ce comportement, le déploiement d’un serveur de médiation sur le site de la succursale est le seul moyen de réduire l’écrêtage des premiers mots.</span><span class="sxs-lookup"><span data-stu-id="4502a-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="4502a-133">Enfin, si votre site central possède un PBX TDM ou si votre PBX IP n’élimine pas la nécessité d’une passerelle RTC, vous devez déployer une passerelle sur l’itinéraire d’appel connexion du serveur de médiation et du PBX.</span><span class="sxs-lookup"><span data-stu-id="4502a-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4502a-134">Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="4502a-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="4502a-135">RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4502a-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="4502a-136">Pour plus d’informations, consultez la section « améliorations apportées à l’échelle de <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>réception dans Windows Server ».</span><span class="sxs-lookup"><span data-stu-id="4502a-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="4502a-137">Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.</span><span class="sxs-lookup"><span data-stu-id="4502a-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

