---
title: Créer des stratégies inter-sites réseau dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Créer des stratégies inter-sites, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server réseau.
ms.openlocfilehash: 455caaf624c463bdb1c32ca8fbce70c88626c774
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892964"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="1a42d-103">Créer des stratégies inter-sites réseau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1a42d-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="1a42d-104">Créer des stratégies inter-sites, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server réseau.</span><span class="sxs-lookup"><span data-stu-id="1a42d-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="1a42d-105">Une stratégie réseau intersite définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.</span><span class="sxs-lookup"><span data-stu-id="1a42d-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1a42d-106">Une stratégie réseau intersite est requis *uniquement* s’il existe un lien d’accès direct entre deux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="1a42d-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="1a42d-p101">Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="1a42d-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="1a42d-110">Pour créer une stratégie réseau intersite</span><span class="sxs-lookup"><span data-stu-id="1a42d-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="1a42d-111">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1a42d-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1a42d-p102">Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies réseau intersite et appliquer un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="1a42d-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="1a42d-114">Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies réseau intersite pour toutes les paires de sites réseau qui présentent un lien d’accès direct.</span><span class="sxs-lookup"><span data-stu-id="1a42d-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a42d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a42d-115">See also</span></span>

[<span data-ttu-id="1a42d-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1a42d-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="1a42d-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1a42d-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="1a42d-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1a42d-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="1a42d-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1a42d-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
