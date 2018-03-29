---
title: Création de stratégies intersites réseau dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Permet de créer des stratégies entre les sites, qui sont utilisés par le contrôle d’admission appel Voix Entreprise dans Skype pour Business Server de réseau.
ms.openlocfilehash: 73eee49022f039bf1bd36d1a06176fa94f3ef3f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-intersite-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="7f2f8-103">Création de stratégies intersites réseau dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7f2f8-103">Create network intersite policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7f2f8-104">Permet de créer des stratégies entre les sites, qui sont utilisés par le contrôle d’admission appel Voix Entreprise dans Skype pour Business Server de réseau.</span><span class="sxs-lookup"><span data-stu-id="7f2f8-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="7f2f8-105">Une stratégie entre les sites de réseau définit les limites de la bande passante entre les sites qui ont des liaisons WAN directes entre eux.</span><span class="sxs-lookup"><span data-stu-id="7f2f8-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f2f8-106">Une stratégie entre les sites de réseau est requis *uniquement* s’il existe une liaison croisée directe entre deux sites du réseau.</span><span class="sxs-lookup"><span data-stu-id="7f2f8-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="7f2f8-p101">Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="7f2f8-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="7f2f8-110">Pour créer une stratégie réseau intersite</span><span class="sxs-lookup"><span data-stu-id="7f2f8-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="7f2f8-111">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7f2f8-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7f2f8-p102">Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies réseau intersite et appliquer un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="7f2f8-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="7f2f8-114">Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies réseau intersite pour toutes les paires de sites réseau qui présentent un lien d’accès direct.</span><span class="sxs-lookup"><span data-stu-id="7f2f8-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7f2f8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f2f8-115">See also</span></span>

#### 

[<span data-ttu-id="7f2f8-116">Nouvelle-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7f2f8-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="7f2f8-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7f2f8-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="7f2f8-118">Ensemble-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7f2f8-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="7f2f8-119">Supprimer-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7f2f8-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

