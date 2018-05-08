---
title: Configurer les paramètres globaux de déviation du trafic multimédia dans Skype pour Business Server 2015 à utiliser les informations de site et de région
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurer le contournement de média à utiliser uniquement pour certains sites et régions dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: ce9daafdde21bc2d30a942ce6b888f2cc7c4e2ff
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a><span data-ttu-id="d10ec-103">Configurer les paramètres globaux de déviation du trafic multimédia dans Skype pour Business Server 2015 à utiliser les informations de site et de région</span><span class="sxs-lookup"><span data-stu-id="d10ec-103">Configure media bypass global settings in Skype for Business Server 2015 to use site and region information</span></span>
 
<span data-ttu-id="d10ec-104">Configurer le contournement de média à utiliser uniquement pour certains sites et régions dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d10ec-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="d10ec-105">Si vous utilisez les étapes décrites dans cette rubrique pour configurer les paramètres globaux pour le média de contournement, il est supposé que vous n’avez pas vérifié la connectivité entre tous les Skype pour les points de terminaison d’entreprise et un homologue pour lequel vous avez configuré le contournement de média sur la connexion de jonction.</span><span class="sxs-lookup"><span data-stu-id="d10ec-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d10ec-p101">Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de déviation du trafic multimédia lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure ci-dessous pour modifier les informations relatives aux sites et aux régions destinées à la déviation du trafic multimédia. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="d10ec-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="d10ec-109">Pour le contournement de média pour fonctionner correctement doit être la cohérence entre un site comme défini dans le Générateur de topologie et telle qu’elle est définie lorsque vous configurez des sites réseau et les régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="d10ec-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="d10ec-110">Par exemple, si vous disposez d’un site de succursale que vous avez défini dans le Générateur de topologie comme ayant déployé uniquement une passerelle PSTN, puis ce site de succursale doit être configuré avec une stratégie de voix entreprise qui permet aux utilisateurs de site de succursale pour que leurs appels PSTN acheminés via la passerelle PSTN Gateway, consultez le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="d10ec-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="d10ec-111">Pour configurer les informations relatives aux sites et aux régions pour la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="d10ec-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="d10ec-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="d10ec-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="d10ec-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="d10ec-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="d10ec-114">Double-cliquez sur la configuration **Globale** dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="d10ec-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="d10ec-115">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.</span><span class="sxs-lookup"><span data-stu-id="d10ec-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="d10ec-116">Cliquez sur **Utiliser la configuration des sites et des régions**.</span><span class="sxs-lookup"><span data-stu-id="d10ec-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="d10ec-117">Si nécessaire, activez la case à cocher **Activer la déviation pour les sites non mappés**.</span><span class="sxs-lookup"><span data-stu-id="d10ec-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d10ec-p103">N’activez cette case à cocher que si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez la déviation du trafic pour les sites non mappés, la configuration est rationalisée. Vous ne spécifiez que les sous-réseaux associés aux sites de succursale au lieu d’avoir à spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="d10ec-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="d10ec-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d10ec-121">Click **Commit**.</span></span>
    
<span data-ttu-id="d10ec-p104">Ensuite, ajoutez les sous-réseaux au site réseau, comme indiqué dans la rubrique [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). Une fois que vous avez associé tous les sous-réseaux aux sites réseau, le déploiement de la déviation du trafic multimédia est terminé.</span><span class="sxs-lookup"><span data-stu-id="d10ec-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="d10ec-124">Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour poursuivre le déploiement de la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="d10ec-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="d10ec-125">Pour plus d’informations, voir [déployer les régions de réseau, des sites et sous-réseaux de Skype pour Business 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="d10ec-125">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d10ec-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d10ec-126">See also</span></span>

#### 

[<span data-ttu-id="d10ec-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="d10ec-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

