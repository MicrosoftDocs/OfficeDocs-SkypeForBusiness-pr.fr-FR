---
title: Créer des stratégies intersite réseau dans Skype Entreprise Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Créez des stratégies intersessants réseau, qui sont utilisées par Voix Entreprise d’admission des appels dans Skype Entreprise Server.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822474"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="f30b6-103">Créer des stratégies intersite réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f30b6-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f30b6-104">Créez des stratégies intersessants réseau, qui sont utilisées par Voix Entreprise d’admission des appels dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f30b6-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="f30b6-105">Une stratégie intersessant réseau définit des limites de bande passante entre les sites qui ont des liaisons wan directes entre eux.</span><span class="sxs-lookup"><span data-stu-id="f30b6-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f30b6-106">Une stratégie intersessant réseau n’est requise que s’il existe un lien croisé direct entre deux sites réseau. </span><span class="sxs-lookup"><span data-stu-id="f30b6-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="f30b6-107">Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="f30b6-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="f30b6-108">Ces deux sites nécessitent une stratégie intersessant qui applique un profil de stratégie de bande passante approprié.</span><span class="sxs-lookup"><span data-stu-id="f30b6-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="f30b6-109">L’exemple suivant applique le profil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="f30b6-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="f30b6-110">Pour créer une stratégie intersessant réseau</span><span class="sxs-lookup"><span data-stu-id="f30b6-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="f30b6-111">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="f30b6-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f30b6-112">Exécutez la cmdlet New-CsNetworkInterSitePolicy pour créer des stratégies intersessants réseau et appliquer un profil de stratégie de bande passante approprié pour deux sites qui ont un lien direct entre les sites.</span><span class="sxs-lookup"><span data-stu-id="f30b6-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="f30b6-113">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f30b6-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="f30b6-114">Répétez l’étape 2 si nécessaire pour créer des stratégies réseau intersessants pour toutes les paires de sites réseau qui ont un lien direct.</span><span class="sxs-lookup"><span data-stu-id="f30b6-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f30b6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f30b6-115">See also</span></span>

[<span data-ttu-id="f30b6-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f30b6-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="f30b6-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f30b6-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="f30b6-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f30b6-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="f30b6-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f30b6-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
