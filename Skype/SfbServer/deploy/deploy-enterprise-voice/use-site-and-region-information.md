---
title: Configurer les paramètres globaux de déviation du média dans Skype Entreprise Server pour utiliser les informations de site et de région
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurez le contournement de média pour qu’il soit utilisé uniquement pour certains sites et régions dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830584"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="33f04-103">Configurer les paramètres globaux de déviation du média dans Skype Entreprise Server pour utiliser les informations de site et de région</span><span class="sxs-lookup"><span data-stu-id="33f04-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="33f04-104">Configurez le contournement de média pour qu’il soit utilisé uniquement pour certains sites et régions dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="33f04-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="33f04-105">Si vous utilisez les étapes de cette rubrique pour configurer les paramètres globaux du contournement de média, nous partons du principe que vous n’avez pas une bonne connectivité entre tous les points de terminaison Skype Entreprise et tout homologue pour lequel vous avez configuré le contournement de média sur la connexion de liaison.</span><span class="sxs-lookup"><span data-stu-id="33f04-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33f04-p101">Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de contournement de média lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure suivante pour modifier les informations relatives aux sites et aux régions destinées au contournement de média. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="33f04-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="33f04-109">Pour que le contournement de média fonctionne correctement, il doit y avoir une cohérence entre un site tel que défini dans le Générateur de topologie et tel qu’il est défini lorsque vous configurez des régions réseau et des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="33f04-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="33f04-110">Par exemple, si vous avez un site de succursale que vous avez défini dans le Générateur de topologie comme n’ayant qu’une passerelle PSTN déployée, ce site de succursale doit être configuré avec une stratégie Voix Entreprise qui permet aux utilisateurs de sites de succursale de faire router leurs appels PSTN via la passerelle PSTN sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="33f04-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="33f04-111">Pour configurer les informations relatives aux sites et aux régions pour le contournement de média</span><span class="sxs-lookup"><span data-stu-id="33f04-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="33f04-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33f04-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="33f04-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="33f04-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="33f04-114">Double-cliquez sur la configuration **Globale** dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="33f04-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="33f04-115">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.</span><span class="sxs-lookup"><span data-stu-id="33f04-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="33f04-116">Cliquez sur **Utiliser la configuration des sites et des régions**.</span><span class="sxs-lookup"><span data-stu-id="33f04-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="33f04-117">Si nécessaire, activez la case à cocher **Activer le contournement pour les sites non mappés**.</span><span class="sxs-lookup"><span data-stu-id="33f04-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33f04-p103">Activez uniquement cette case à cocher si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée. Vous devez uniquement spécifier les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="33f04-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="33f04-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="33f04-121">Click **Commit**.</span></span>
    
<span data-ttu-id="33f04-122">Ensuite, ajoutez des sous-réseaux au site réseau, comme décrit dans Associer un [sous-réseau à un site réseau.](deploy-network.md#BKMK_AssociateSubnets)</span><span class="sxs-lookup"><span data-stu-id="33f04-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="33f04-123">Une fois que vous avez associé tous les sous-réseaux aux sites réseau, le déploiement du contournement de média est terminé.</span><span class="sxs-lookup"><span data-stu-id="33f04-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="33f04-124">Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour pouvoir poursuivre le déploiement du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="33f04-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="33f04-125">Pour plus d’informations, voir Déployer des régions réseau, des sites et [des sous-réseaux dans Skype Entreprise.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="33f04-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="33f04-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33f04-126">See also</span></span>

[<span data-ttu-id="33f04-127">Associer un sous-réseau à un site réseau</span><span class="sxs-lookup"><span data-stu-id="33f04-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

