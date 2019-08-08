---
title: Créer des stratégies d’intersite réseau dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Créer des stratégies réseau intersites, qui sont utilisées par le système de contrôle d’admission des appels voix entreprise dans Skype entreprise Server.
ms.openlocfilehash: ac03057de5b6e25e2b9de812f0d53ae02811d456
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233481"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="9c886-103">Créer des stratégies d’intersite réseau dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9c886-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="9c886-104">Créer des stratégies réseau intersites, qui sont utilisées par le système de contrôle d’admission des appels voix entreprise dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9c886-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="9c886-105">Une stratégie réseau intersite définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.</span><span class="sxs-lookup"><span data-stu-id="9c886-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9c886-106">Une stratégie inter-site réseau est requise *uniquement* s’il existe un lien croisé direct entre deux sites du réseau.</span><span class="sxs-lookup"><span data-stu-id="9c886-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="9c886-p101">Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="9c886-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="9c886-110">Pour créer une stratégie réseau intersite</span><span class="sxs-lookup"><span data-stu-id="9c886-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="9c886-111">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9c886-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9c886-p102">Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies réseau intersite et appliquer un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="9c886-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="9c886-114">Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies réseau intersite pour toutes les paires de sites réseau qui présentent un lien d’accès direct.</span><span class="sxs-lookup"><span data-stu-id="9c886-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9c886-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c886-115">See also</span></span>

[<span data-ttu-id="9c886-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9c886-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="9c886-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9c886-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="9c886-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9c886-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="9c886-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="9c886-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
