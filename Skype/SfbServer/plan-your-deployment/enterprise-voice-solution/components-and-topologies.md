---
title: Composants et topologies pour le contrôle d’admission des appels dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planification du contrôle d’admission des appels (CAC) si vous avez un réseau MPLS, une ligne SIP ou une passerelle PSTN ou un PBX tiers. S’applique à Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825844"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="927ce-104">Composants et topologies pour le contrôle d’admission des appels dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="927ce-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="927ce-105">Planification du contrôle d’admission des appels (CAC) si vous avez un réseau MPLS, une ligne SIP ou une passerelle PSTN ou un PBX tiers.</span><span class="sxs-lookup"><span data-stu-id="927ce-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="927ce-106">S’applique à Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="927ce-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="927ce-107">Les rubriques de cette section donnent des informations sur les considérations spécifiques de déploiement du contrôle d’admission des appels (CAC) avec différents types de topologies réseau.</span><span class="sxs-lookup"><span data-stu-id="927ce-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="927ce-108">Contrôle d’admission des appels sur un réseau MPLS</span><span class="sxs-lookup"><span data-stu-id="927ce-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="927ce-p103">Dans un réseau MPLS (Multiprotocol Label Switching), tous les sites sont connectés par un maillage. C’est-à-dire que tous les sites sont connectés directement au segment principal MPLS du fournisseur de services Internet, chaque site recevant la bande passante à utiliser sur une liaison WAN au cloud MPLS. Il n’y a aucun concentrateur réseau ou site central pour contrôler le routage IP. La figure suivante montre un réseau simple basé sur la technologie MPLS.</span><span class="sxs-lookup"><span data-stu-id="927ce-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="927ce-113">**Exemple de réseau MPLS**</span><span class="sxs-lookup"><span data-stu-id="927ce-113">**Example MPLS network**</span></span>

![CAC avec MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="927ce-p104">Pour déployer le contrôle d’admission des appels dans un réseau MPLS, vous devez créer une région sur le réseau pour représenter le cloud MPLS et créer un site réseau pour représenter chaque site satellite MPLS. La figure suivante montre comment la région et les sites du réseau doivent être configurés pour représenter le réseau MPLS exemple dans la figure précédente. Les limites globales de bande passante et de session de bande passante sont ensuite basées sur la capacité de la liaison WAN de chaque site vers la région qui représente le cloud MPLS.</span><span class="sxs-lookup"><span data-stu-id="927ce-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="927ce-118">**Région et sites d’un réseau MPLS**</span><span class="sxs-lookup"><span data-stu-id="927ce-118">**Network region and network sites for an MPLS network**</span></span>

![Contrôle d’admission des appels (CAC) avec diagramme MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="927ce-120">Contrôle d’admission des appels sur une trunk SIP</span><span class="sxs-lookup"><span data-stu-id="927ce-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="927ce-p105">Pour déployer le contrôle d’admission des appels sur une jonction SIP, vous créez un site réseau pour représenter le fournisseur de services de téléphonie Internet (ITSP). Pour appliquer la stratégie de bande passante sur la jonction SIP, vous créez une stratégie intersite entre le site réseau dans votre entreprise et le site réseau créé pour représenter le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="927ce-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="927ce-123">La figure suivante montre un exemple de déploiement du contrôle d’admission des appels sur une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="927ce-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="927ce-124">**Configuration du contrôle d’admission des appels sur une jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="927ce-124">**CAC configuration on a SIP trunk**</span></span>

![Diagramme de la trunking SIP du contrôle d’admission des appels](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="927ce-126">Pour configurer le contrôle d’admission des appels sur une jonction SIP, vous devrez exécuter les tâches suivantes pendant le déploiement du contrôle d’admission des appels :</span><span class="sxs-lookup"><span data-stu-id="927ce-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="927ce-127">Créez un site réseau pour représenter le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="927ce-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="927ce-128">Associez le site réseau à une région réseau appropriée, et allouez une bande passante nulle pour l’audio et la vidéo pour ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="927ce-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="927ce-129">Pour plus d’informations, voir [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="927ce-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="927ce-130">Pour le fournisseur de services de téléphonie Internet, cette configuration de site réseau n’est pas fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="927ce-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="927ce-131">Les valeurs de stratégie de bande passante sont en fait appliquées à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="927ce-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="927ce-132">Créez un lien intersite pour la jonction SIP à l’aide des valeurs de paramètre pertinentes pour le site créé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="927ce-133">Par exemple, utilisez le nom du site réseau dans votre entreprise comme valeur du paramètre NetworkSiteID1 et le site réseau du fournisseur de services de téléphonie Internet comme valeur du paramètre NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="927ce-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="927ce-134">Pour plus d’informations, voir [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="927ce-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="927ce-135">Obtenez l’adresse IP du point de terminaison multimédia du contrôleur de frontière de session (SCB) auprès de votre itsp.</span><span class="sxs-lookup"><span data-stu-id="927ce-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="927ce-136">Ajoutez cette adresse IP avec un masque de sous-réseau de 32 au site réseau qui représente le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="927ce-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="927ce-137">Pour plus d’informations, voir [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="927ce-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="927ce-138">Contrôle d’admission des appels avec une passerelle PSTN ou un PBX tiers</span><span class="sxs-lookup"><span data-stu-id="927ce-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="927ce-139">Cette rubrique décrit des exemples de déploiement du contrôle d’admission des appels (CAC) sur la liaison entre l’interface de passerelle du serveur de médiation et une passerelle PSTN (réseau téléphonique commuté) tierce ou pbX (private branch exchange).</span><span class="sxs-lookup"><span data-stu-id="927ce-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="927ce-140">Cas 1 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et une passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="927ce-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="927ce-141">Le service Cac peut être déployé sur la liaison de réseau wan à partir de l’interface de passerelle du serveur de médiation vers une passerelle PBX ou PSTN tierce.</span><span class="sxs-lookup"><span data-stu-id="927ce-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="927ce-142">**Cas 1 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et une passerelle PSTN**</span><span class="sxs-lookup"><span data-stu-id="927ce-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Cas 1 : Contrôle d’accès au contrôle d’accès entre passerelle PSTN du serveur de médiation](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="927ce-144">Dans cet exemple, le service Cac est appliqué entre le serveur de médiation et une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="927ce-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="927ce-145">Si un utilisateur client Skype Entreprise sur le site réseau 1 passe un appel PSTN via la passerelle PSTN dans le site réseau 2, le média passe par la liaison wan.</span><span class="sxs-lookup"><span data-stu-id="927ce-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="927ce-146">Par conséquent, deux vérifications cac sont effectuées pour chaque session PSTN :</span><span class="sxs-lookup"><span data-stu-id="927ce-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="927ce-147">Entre l’application cliente Skype Entreprise et le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="927ce-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="927ce-148">Entre le serveur de médiation et la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="927ce-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="927ce-149">Cela fonctionne à la fois pour les appels PSTN entrants vers un client dans le site réseau 1 et pour les appels PSTN sortants provenant d’une application cliente dans Le site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-150">Assurez-vous que le sous-réseau IP à qui appartient la passerelle PSTN est configuré et associé au site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="927ce-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-151">Assurez-vous que le sous-réseau IP à qui appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-152">Pour plus d’informations, voir [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="927ce-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="927ce-153">Cas 2 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers avec point de terminaison multimédia</span><span class="sxs-lookup"><span data-stu-id="927ce-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="927ce-154">Cette configuration est similaire au cas 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="927ce-155">Dans les deux cas, le serveur de médiation connaît le périphérique qui arrête le média à l’extrémité opposée de la liaison wan et l’adresse IP de la passerelle PSTN ou du PBX avec point de terminaison multimédia (MTP) est configurée sur le serveur de médiation comme saut suivant.</span><span class="sxs-lookup"><span data-stu-id="927ce-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="927ce-156">**Cas 2 : CONTRÔLE D’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers avec MTP**</span><span class="sxs-lookup"><span data-stu-id="927ce-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Cas 2 : CONTRÔLE D’accès au contrôle d’accès entre pbX du serveur de médiation avec MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="927ce-158">Dans cet exemple, le service Cac est appliqué entre le serveur de médiation et le PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="927ce-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="927ce-159">Si un utilisateur client Skype Entreprise sur le site réseau 1 passe un appel PSTN via le PBX/MTP situé dans le site réseau 2, le média passe par la liaison wan.</span><span class="sxs-lookup"><span data-stu-id="927ce-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="927ce-160">Par conséquent, pour chaque session PSTN, deux contrôles d’intégrité du contrôle d’intégrité sont effectués :</span><span class="sxs-lookup"><span data-stu-id="927ce-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="927ce-161">Entre l’application cliente Skype Entreprise et le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="927ce-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="927ce-162">Entre le serveur de médiation et le PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="927ce-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="927ce-163">Cela fonctionne pour les appels PSTN entrants vers un client du site réseau 1 et les appels PSTN sortants provenant d’un client du Site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-164">Assurez-vous que le sous-réseau IP à qui appartient le MTP est configuré et associé au site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="927ce-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-165">Assurez-vous que le sous-réseau IP à qui appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-166">Pour plus d’informations, voir [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="927ce-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="927ce-167">Cas 3 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers sans point de terminaison multimédia</span><span class="sxs-lookup"><span data-stu-id="927ce-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="927ce-168">Le cas 3 est légèrement différent des deux premiers cas.</span><span class="sxs-lookup"><span data-stu-id="927ce-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="927ce-169">S’il n’existe aucun MTP sur le PBX tiers, pour une demande de session sortante au PBX tiers, le serveur de médiation ne sait pas où le média s’interrompra dans la limite du PBX.</span><span class="sxs-lookup"><span data-stu-id="927ce-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="927ce-170">Dans ce cas, le média circule directement entre le serveur de médiation et le périphérique de point de terminaison tiers.</span><span class="sxs-lookup"><span data-stu-id="927ce-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="927ce-171">**Cas 3 : CONTRÔLE D’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers sans MTP**</span><span class="sxs-lookup"><span data-stu-id="927ce-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Cas 3 : CONTRÔLE D’accès au contrôle d’accès entre le PBX du serveur de médiation sans MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="927ce-173">Dans cet exemple, si un utilisateur client Skype Entreprise sur le site réseau 1 appelle un utilisateur via le PBX, le serveur de médiation peut effectuer des vérifications cac uniquement sur la partie proxy (entre l’application cliente Skype Entreprise et le serveur de médiation).</span><span class="sxs-lookup"><span data-stu-id="927ce-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="927ce-174">Étant donné que le serveur de médiation ne comprend pas d’informations sur le périphérique de point de terminaison pendant la demande de session, les vérifications du contrôle d’accès au contrôle d’accès ne peuvent pas être effectuées sur la liaison wan (entre le serveur de médiation et le point de terminaison tiers) avant l’établissement de l’appel.</span><span class="sxs-lookup"><span data-stu-id="927ce-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="927ce-175">Cependant, une fois la session établie, le serveur de médiation facilite la gestion de la bande passante utilisée sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="927ce-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="927ce-176">Pour les appels qui proviennent du point de terminaison tiers, les informations sur ce périphérique de point de terminaison sont disponibles au moment de la demande de session et la vérification cac peut être effectuée sur les deux côtés du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="927ce-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-177">Assurez-vous que le sous-réseau IP à qui appartiennent les appareils de point de terminaison est configuré et associé au site réseau 2.</span><span class="sxs-lookup"><span data-stu-id="927ce-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-178">Assurez-vous que le sous-réseau IP à qui appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.</span><span class="sxs-lookup"><span data-stu-id="927ce-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="927ce-179">Pour plus d’informations, voir [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="927ce-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


