---
title: 'Lync Server 2013 : configuration de la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bf2fb06f25ccf1871393cf4d80ffa3c33a42fc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="5fe33-102">Configurer la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe33-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fe33-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="5fe33-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="5fe33-104">Cette section suppose que vous ayez déjà publié et configuré au moins un ou plusieurs serveurs de médiation (comme décrit dans [define a Mediation Server in Topology Builder in Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) et [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), ou dans [définir et configurer un pool frontal ou un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) et [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivement, tout dans la documentation de déploiement).</span><span class="sxs-lookup"><span data-stu-id="5fe33-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="5fe33-105">Cette section suppose également que vous ayez défini au moins un homologue de passerelle pour fournir la connectivité PSTN, comme décrit dans [define a Gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5fe33-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="5fe33-106">Si l’homologue auquel vous vous connectez est l’SBC d’un fournisseur de jonction SIP, assurez-vous que le fournisseur est un fournisseur qualifié et que le fournisseur prend en charge la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="5fe33-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="5fe33-107">Par exemple, de nombreux fournisseurs de jonction SIP autoriseront uniquement leurs SBC à recevoir du trafic du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5fe33-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="5fe33-108">Dans ce cas, le contournement doit être activé pour la jonction en question.</span><span class="sxs-lookup"><span data-stu-id="5fe33-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="5fe33-109">De même, vous ne pouvez pas activer le contournement de média, à moins que l’organisation ne révèle les adresses IP de son réseau interne au fournisseur de jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="5fe33-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fe33-110">Le contournement de média ne fonctionnera pas avec chaque passerelle PSTN, système IP-PBX et SBC.</span><span class="sxs-lookup"><span data-stu-id="5fe33-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="5fe33-111">Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="5fe33-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="5fe33-112">La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à.</span><span class="sxs-lookup"><span data-stu-id="5fe33-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="5fe33-113">Cette rubrique explique comment activer le contournement de média en vue de réduire le traitement nécessaire du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5fe33-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="5fe33-114">Avant d’activer la déviation du trafic multimédia, assurez-vous que votre environnement répond aux conditions requises pour prendre en charge la déviation du trafic multimédia, comme décrit dans la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5fe33-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="5fe33-115">Assurez-vous également que vous avez utilisé les informations de planification de la déviation du trafic [multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) pour décider s’il faut activer les paramètres globaux de déviation du trafic multimédia pour toujours contourner le serveur de médiation ou utiliser les informations de site et de région lorsque vous déterminez s’il faut contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="5fe33-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="5fe33-p104">Si vous avez déjà configuré le contrôle d’admission des appels (CAC), une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel le contournement de média est employé. La vérification de l’emploi du contournement de media est effectuée en premier, et s’il est employé, le contrôle d’admission des appels n’est pas utilisé pour l’appel ; ce n’est qu’en cas d’échec du contournement de média que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont par conséquent mutuellement exclusives pour tout appel particulier qui est acheminé sur le PSTN. Il s’agit du comportement logique car le contournement de média suppose que les restrictions de bande passante n’existent pas entre systèmes d’extrémité de média sur un appel ; le contournement de média est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel PSTN : a) le média contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le media est traité par le serveur de médiation impliqué dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="5fe33-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="5fe33-121">Étapes suivantes : Activer le contournement de média sur la connexion des jonctions</span><span class="sxs-lookup"><span data-stu-id="5fe33-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="5fe33-122">Après avoir configuré les paramètres initiaux pour la connectivité PSTN (plans de numérotation, stratégies de voix, enregistrements d’utilisation RTC, itinéraires d’appels sortants et règles de traduction), commencez le processus d’activation de la déviation du trafic multimédia en suivant les étapes décrites dans [Configure a trunk with Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="5fe33-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fe33-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fe33-123">See Also</span></span>


[<span data-ttu-id="5fe33-124">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe33-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="5fe33-125">Configuration de la déviation du trafic multimédia dans Lync Server 2013 pour toujours contourner le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="5fe33-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="5fe33-126">Configurer les paramètres globaux de déviation du trafic multimédia dans Lync Server 2013 pour utiliser les informations de site et de région</span><span class="sxs-lookup"><span data-stu-id="5fe33-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="5fe33-127">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe33-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="5fe33-128">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe33-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

