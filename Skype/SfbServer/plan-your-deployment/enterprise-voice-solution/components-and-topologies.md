---
title: Composants et topologies pour appeler le contrôle d’admission dans Skype pour les entreprises
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planification du contrôle d’admission des appels si vous disposez d’un réseau MPLS, d’une jonction SIP (Session Initiation Protocol) ou d’une passerelle RTC ou d’un système PBX tiers. S’applique à Skype Business Server Enterprise Voice.
ms.openlocfilehash: 7022ade98dbd614023a4faaea283b939fa658e73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207951"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="c5325-104">Composants et topologies pour appeler le contrôle d’admission dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="c5325-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="c5325-105">Planification du contrôle d’admission des appels si vous disposez d’un réseau MPLS, d’une jonction SIP (Session Initiation Protocol) ou d’une passerelle RTC ou d’un système PBX tiers.</span><span class="sxs-lookup"><span data-stu-id="c5325-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="c5325-106">S’applique à Skype Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c5325-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="c5325-107">Les rubriques de cette section donnent des informations sur les considérations spécifiques de déploiement du contrôle d’admission des appels (CAC) avec différents types de topologies réseau.</span><span class="sxs-lookup"><span data-stu-id="c5325-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="c5325-108">Contrôle d’admission des appels sur un réseau MPLS</span><span class="sxs-lookup"><span data-stu-id="c5325-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="c5325-p103">Dans un réseau MPLS (Multiprotocol Label Switching), tous les sites sont connectés par un maillage. C’est-à-dire que tous les sites sont connectés directement au segment principal MPLS du fournisseur de services Internet, chaque site recevant la bande passante à utiliser sur une liaison de réseau étendu au cloud MPLS. Il n’y a aucun concentrateur réseau ou site central pour contrôler le routage IP. La figure suivante montre un réseau simple basé sur la technologie MPLS.</span><span class="sxs-lookup"><span data-stu-id="c5325-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="c5325-113">**Exemple de réseau MPLS**</span><span class="sxs-lookup"><span data-stu-id="c5325-113">**Example MPLS network**</span></span>

![CAC avec MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="c5325-p104">Pour déployer le contrôle d’admission des appels dans un réseau MPLS, vous devez créer une région sur le réseau pour représenter le cloud MPLS et créer un site réseau pour représenter chaque site satellite MPLS. La figure suivante montre comment la région et les sites du réseau doivent être configurés pour représenter le réseau MPLS exemple dans la figure précédente. Les limites globales de bande passante et de session de bande passante sont ensuite basées sur la capacité de la liaison de réseau étendu de chaque site vers la région qui représente le cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="c5325-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="c5325-118">**Région et sites d’un réseau MPLS**</span><span class="sxs-lookup"><span data-stu-id="c5325-118">**Network region and network sites for an MPLS network**</span></span>

![Diagramme de contrôle d’admission des appels (CAC) avec MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="c5325-120">Contrôle d’admission des appels sur une jonction SIP</span><span class="sxs-lookup"><span data-stu-id="c5325-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="c5325-p105">Pour déployer le contrôle d’admission des appels sur une jonction SIP, vous créez un site réseau pour représenter le fournisseur de services de téléphonie Internet (ITSP). Pour appliquer la stratégie de bande passante sur la jonction SIP, vous créez une stratégie intersite entre le site réseau dans votre entreprise et le site réseau créé pour représenter le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="c5325-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="c5325-123">La figure suivante montre un exemple de déploiement du contrôle d’admission des appels sur une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="c5325-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="c5325-124">**Configuration du contrôle d’admission des appels sur une jonction SIP (Session Initiation Protocol)**</span><span class="sxs-lookup"><span data-stu-id="c5325-124">**CAC configuration on a SIP trunk**</span></span>

![Diagramme de jonction SIP de Contrôle d’admission des appels](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="c5325-126">Pour configurer le contrôle d’admission des appels sur une jonction SIP, vous devrez exécuter les tâches suivantes pendant le déploiement du contrôle d’admission des appels :</span><span class="sxs-lookup"><span data-stu-id="c5325-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="c5325-p106">Créez un site réseau pour représenter le fournisseur de services de téléphonie Internet. Associez le site réseau à une région réseau appropriée, et allouez une bande passante nulle pour l’audio et la vidéo pour ce site réseau. Pour plus d’informations, reportez-vous à [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c5325-p106">Create a network site to represent the ITSP. Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site. For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5325-p107">Pour le fournisseur de services de téléphonie Internet, cette configuration de site réseau n’est pas fonctionnelle. Les valeurs de stratégie de bande passante sont en fait appliquées à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="c5325-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="c5325-132">Créez un lien intersite pour la jonction SIP à l’aide des valeurs de paramètre pertinentes pour le site créé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="c5325-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="c5325-133">Par exemple, utilisez le nom du site réseau dans votre entreprise comme valeur du paramètre NetworkSiteID1 et le site réseau du fournisseur de services de téléphonie Internet comme valeur du paramètre NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="c5325-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="c5325-134">Pour plus d’informations, voir [créer des stratégies inter-sites réseau dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) dans la documentation de déploiement et [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c5325-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="c5325-135">Obtenir l’adresse IP de la Session Border Controller (SCB) le Point de terminaison multimédia à partir de votre fournisseur ITSP.</span><span class="sxs-lookup"><span data-stu-id="c5325-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="c5325-136">Ajoutez cette adresse IP avec un masque de sous-réseau de 32 au site réseau qui représente le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="c5325-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="c5325-137">Pour plus d’informations, reportez-vous à [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5325-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="c5325-138">Contrôle d’admisson des appels avec une passerelle RTC ou un système PBX tiers</span><span class="sxs-lookup"><span data-stu-id="c5325-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="c5325-139">Cette rubrique décrit les exemples de la façon dont le contrôle d’admission des appels (CAC) peut être déployé sur le lien entre l’interface de passerelle du serveur de médiation et une passerelle de réseau téléphonique commuté tiers ou un autocommutateur privé (PBX).</span><span class="sxs-lookup"><span data-stu-id="c5325-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="c5325-140">Exemple 1 : Contrôle d’admission des appels entre le serveur de médiation et une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="c5325-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="c5325-141">CAC peut être déployé sur le réseau étendu lien à partir de l’interface de passerelle du serveur de médiation vers une passerelle PBX ou PSTN de tiers.</span><span class="sxs-lookup"><span data-stu-id="c5325-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="c5325-142">**Exemple 1 : Contrôle d’admission des appels entre le serveur de médiation et une passerelle RTC**</span><span class="sxs-lookup"><span data-stu-id="c5325-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Cas 1 : CAC entre passerelle PSTN de serveur de médiation](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="c5325-144">Dans cet exemple, CAC est appliquée entre le serveur de médiation et une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="c5325-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="c5325-145">Si un Skype pour l’utilisateur de l’entreprise cliente au Site réseau 1 passe un appel RTC par le biais de la passerelle PSTN dans Site réseau 2, le les données multimédias transitent par le biais de la liaison réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="c5325-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="c5325-146">Par conséquent, deux vérifications de contrôle d’admission des appels sont effectuées pour chaque session RTC :</span><span class="sxs-lookup"><span data-stu-id="c5325-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="c5325-147">Entre le Skype pour une application client d’entreprise et le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c5325-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="c5325-148">Entre le serveur de médiation et la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="c5325-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="c5325-149">Cet exemple s’applique aux appels RTC entrants vers un client dans Site réseau 1, ainsi qu’aux appels RTC sortants issus d’une application cliente dans Site réseau n1.</span><span class="sxs-lookup"><span data-stu-id="c5325-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-150">Assurez-vous que le sous-réseau IP auquel appartient la passerelle RTC est configuré et associé au Site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="c5325-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-151">Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au Site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="c5325-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-152">Pour plus d’informations, reportez-vous à la rubrique [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5325-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="c5325-153">Cas 2 : CAC entre le serveur de médiation et un système PBX tiers avec Point de terminaison multimédia</span><span class="sxs-lookup"><span data-stu-id="c5325-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="c5325-154">Cette configuration est semblable à l’exemple 1.</span><span class="sxs-lookup"><span data-stu-id="c5325-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="c5325-155">Dans les deux cas, le serveur de médiation sait quel périphérique termine multimédia à l’opposé de la liaison WAN et l’adresse IP de la passerelle PSTN ou PBX avec une terminaison Point MTP (Media) est configuré sur le serveur de médiation comme tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="c5325-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="c5325-156">**Exemple 2 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers avec point de terminaison multimédia (MTP)**</span><span class="sxs-lookup"><span data-stu-id="c5325-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Cas 2 : CAC entre PBX de serveur de médiation avec MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="c5325-158">Dans cet exemple, CAC est appliquée entre le serveur de médiation et le système PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="c5325-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="c5325-159">Si un Skype pour l’utilisateur de l’entreprise cliente sur le Site réseau 1 passe un appel PSTN via le système PBX/MTP situé dans un Site réseau 2, le les données multimédias transitent par le biais de la liaison réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="c5325-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="c5325-160">Par conséquent, pour chaque session RTC, deux vérifications de contrôle d’admission des appels sont effectuées :</span><span class="sxs-lookup"><span data-stu-id="c5325-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="c5325-161">Entre le Skype pour une application client d’entreprise et le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c5325-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="c5325-162">Entre le serveur de médiation et le système PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="c5325-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="c5325-163">Cet exemple s’applique aux appels RTC entrants vers un client dans Site réseau n° 1, ainsi qu’aux appels RTC sortants issus d’un client dans Site réseau n° 1.</span><span class="sxs-lookup"><span data-stu-id="c5325-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-164">Assurez-vous que le sous-réseau IP auquel appartient le MTP est configuré et associé au Site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="c5325-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-165">Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au Site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="c5325-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-166">Pour plus d’informations, reportez-vous à la rubrique [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5325-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="c5325-167">Cas 3 : CAC entre le serveur de médiation et un système PBX tiers sans Point de terminaison multimédia</span><span class="sxs-lookup"><span data-stu-id="c5325-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="c5325-168">L’exemple 3 est légèrement différent des deux premiers.</span><span class="sxs-lookup"><span data-stu-id="c5325-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="c5325-169">S’il n’existe aucune MTP sur le système PBX tiers, d’une session sortante demande au système PBX tiers le serveur de médiation ne sait pas où multimédia se termine dans la limite du système PBX.</span><span class="sxs-lookup"><span data-stu-id="c5325-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="c5325-170">Dans ce cas, le les données multimédias transitent directement entre le serveur de médiation et le périphérique de point de terminaison tiers.</span><span class="sxs-lookup"><span data-stu-id="c5325-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="c5325-171">**Exemple 3 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers sans point de terminaison multimédia (MTP)**</span><span class="sxs-lookup"><span data-stu-id="c5325-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Cas 3 : CAC entre PBX de serveur de médiation sans MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="c5325-173">Dans cet exemple, si un Skype pour l’utilisateur de l’entreprise cliente au Site réseau 1 passe un appel à un utilisateur par le système PBX, le serveur de médiation est capable d’effectuer des vérifications CAC uniquement sur le segment de proxy entre (le Skype pour l’application cliente de Business) et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c5325-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="c5325-174">Car le serveur de médiation ne dispose pas d’informations sur l’appareil de point de terminaison pendant la session est demandée, CAC vérifications ne peut pas être effectuées sur le réseau étendu lien (entre le serveur de médiation et le point de terminaison tiers) avant l’établissement d’un appel.</span><span class="sxs-lookup"><span data-stu-id="c5325-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="c5325-175">Une fois la session établie, le serveur de médiation facilite toutefois, dans Gestion de la bande passante utilisée sur la jonction.</span><span class="sxs-lookup"><span data-stu-id="c5325-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="c5325-176">Pour les appels provenant du point de terminaison tiers, les informations sur ce périphérique de point de terminaison sont disponibles au moment de la demande de session et à cocher CAC peut être effectuée sur les deux côtés du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c5325-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-177">Assurez-vous que le sous-réseau IP auquel appartiennent les périphériques de point de terminaison est configuré et associé au Site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="c5325-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-178">Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au Site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="c5325-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="c5325-179">Pour plus d’informations, reportez-vous à la rubrique [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5325-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


