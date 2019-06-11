---
title: 'Lync Server 2013 : Configuration de la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465a949ca1581933f96f18cfe2977d400fa7a152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="58fa6-102">Configuration de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58fa6-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58fa6-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="58fa6-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="58fa6-104">Cette section part du principe que vous avez déjà publié et configuré au moins un ou plusieurs serveurs de médiation (comme décrit dans [définir un serveur de médiation dans le générateur de topologie de Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) et [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md)ou dans [Définissez et configurez un pool frontal ou un serveur Standard Edition dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) et [publiez la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivement, dans la documentation de déploiement).</span><span class="sxs-lookup"><span data-stu-id="58fa6-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="58fa6-105">Dans cette section, vous devez également définir au moins un homologue de passerelle pour fournir une connectivité PSTN, comme décrit dans [la section définir une passerelle dans le générateur de topologie de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="58fa6-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="58fa6-106">Si l’homologue auquel vous vous connectez est le contrôleur SBC (Session Border Controller) d’un fournisseur de jonctions SIP (Session Initiation Protocol), assurez-vous qu’il s’agit d’un fournisseur qualifié et qu’il prend en charge la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="58fa6-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="58fa6-107">Par exemple, de nombreux fournisseurs de jonctions SIP autoriseront uniquement leurs contrôleurs SBC à recevoir du trafic du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="58fa6-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="58fa6-108">Dans ce cas, la déviation du trafic doit être activée pour la jonction en question.</span><span class="sxs-lookup"><span data-stu-id="58fa6-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="58fa6-109">De même, vous ne pouvez pas activer la déviation du trafic multimédia sauf si l’organisation communique les adresses IP de son réseau interne au fournisseur de jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="58fa6-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58fa6-110">La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="58fa6-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="58fa6-111">Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="58fa6-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="58fa6-112">La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="58fa6-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="58fa6-113">Cette section décrit comment activer la dérivation multimédia pour réduire le traitement requis par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="58fa6-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="58fa6-114">Avant d’activer la dérivation multimédia, assurez-vous que votre environnement répond aux conditions nécessaires à la prise en charge du contournement multimédia, comme décrit dans la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="58fa6-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="58fa6-115">Assurez-vous également d’avoir utilisé les informations fournies dans la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) pour décider si vous voulez activer les paramètres globaux de contournement du contenu multimédia pour ignorer toujours le serveur de médiation ou utiliser les informations sur le site et la région lorsque vous déterminez s’il doit contournement du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="58fa6-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="58fa6-p104">Si vous avez déjà configuré le contrôle d’admission des appels, une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel la déviation du trafic multimédia est employée. La vérification de l’emploi de la déviation du trafic multimédia est effectuée en premier, et si elle est employée, le contrôle d’admission des appels n’est pas utilisé pour l’appel. Ce n’est qu’en cas d’échec de la déviation du trafic multimédia que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont, par conséquent, mutuellement exclusives pour tout appel particulier acheminé sur le RTC. Il s’agit du comportement logique, car la déviation du trafic multimédia suppose qu’il n’y a pas de restrictions de bande passante entre les points de terminaison multimédia sur un appel. La déviation du trafic multimédia est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel RTC : a) le trafic multimédia contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le trafic multimédia est traité par le serveur de médiation impliqué dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="58fa6-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="58fa6-121">Étapes suivantes: activer la dérivation multimédia sur la connexion Trunk</span><span class="sxs-lookup"><span data-stu-id="58fa6-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="58fa6-122">Après avoir configuré les paramètres initiaux pour la connectivité PSTN (plans de numérotation, stratégies vocales, enregistrements d’utilisation RTC, itinéraires d’appels sortants et règles de traduction), commencez le processus d’activation de la contournement de média en suivant les étapes décrites dans la rubrique [configurer un Trunk avec le contournement multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="58fa6-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58fa6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58fa6-123">See Also</span></span>


[<span data-ttu-id="58fa6-124">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58fa6-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="58fa6-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span><span class="sxs-lookup"><span data-stu-id="58fa6-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="58fa6-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="58fa6-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="58fa6-127">Options de contournement global de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58fa6-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="58fa6-128">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58fa6-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

