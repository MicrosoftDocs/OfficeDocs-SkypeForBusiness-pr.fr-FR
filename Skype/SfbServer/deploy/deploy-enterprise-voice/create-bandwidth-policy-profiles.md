---
title: Création de profils de stratégie de bande passante dans Skype Entreprise Server 2015
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Créer ou modifier des stratégies de bande passante, qui sont utilisés par le contrôle d’admission appel Voix Entreprise dans Skype pour Business Server.
ms.openlocfilehash: 8d8fb4ff11f3f43b2a50054cc42297dda2d9a652
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server-2015"></a><span data-ttu-id="ae0c5-103">Création de profils de stratégie de bande passante dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="ae0c5-103">Create bandwidth policy profiles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ae0c5-104">Créer ou modifier des stratégies de bande passante, qui sont utilisés par le contrôle d’admission appel Voix Entreprise dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ae0c5-105">Stratégies de bande passante définissent les limitations de l’utilisation de la bande passante en temps réel audio et vidéo modalités.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="ae0c5-106">Stratégies de bande passante sont des profils de stratégie tobandwidth appliqué, qui peuvent être appliquées à plusieurs sites de réseau appel de contrôle d’admission.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="ae0c5-107">Pour connaître la limite que la bande passante doit définir dans votre déploiement de CAC, afficher un [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="ae0c5-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="ae0c5-p102">Les stratégies d’exemple créées lors de la procédure suivante définissent des limites pour l’ensemble du trafic audio, les sessions audio individuelles, l’ensemble du trafic vidéo et les sessions vidéo individuelles. Le profil de stratégie de bande passante « 5Mb_Link » définit par exemple les limites suivantes :</span><span class="sxs-lookup"><span data-stu-id="ae0c5-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="ae0c5-110">Limite audio : 2 000 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="ae0c5-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="ae0c5-111">Limite de session audio : 200 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="ae0c5-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="ae0c5-112">Limite vidéo : 1 400 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="ae0c5-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="ae0c5-113">Limite de session vidéo : 700 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="ae0c5-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="ae0c5-p103">La valeur minimum de limite de session audio est 40 Kbits/s. La valeur minimum de limite de session vidéo est 100 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ae0c5-116">Pour créer des profils de stratégie de bande passante pour Business Server Management Shell à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="ae0c5-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ae0c5-117">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ae0c5-p104">Pour chaque profil de stratégie de bande passante que vous voulez créer, exécutez l’applet de commande New-CsNetworkBandwidthPolicyProfile. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ae0c5-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ae0c5-120">Pour créer des profils de stratégie de bande passante pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="ae0c5-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ae0c5-121">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ae0c5-122">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ae0c5-123">Cliquez sur le bouton de navigation **Profil de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="ae0c5-124">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-124">Click **New**.</span></span>
    
5. <span data-ttu-id="ae0c5-125">Dans la page **Nouveau profil de stratégie**, cliquez sur **Nom**, puis tapez un nom pour le profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="ae0c5-126">Cliquez sur **Limite audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions audio combinées.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="ae0c5-127">Cliquez sur **Limite de session audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session audio individuelle.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="ae0c5-128">Cliquez sur **Limite vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions vidéo combinées.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="ae0c5-129">Cliquez sur **Limite de session vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session vidéo individuelle.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="ae0c5-130">En option, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="ae0c5-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="ae0c5-132">Pour finir de créer des profils de stratégie de bande passante pour votre topologie, répétez les étapes 4 à 11 avec des paramètres pour d’autres profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ae0c5-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ae0c5-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae0c5-133">See also</span></span>

#### 

[<span data-ttu-id="ae0c5-134">Nouvelle-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ae0c5-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ae0c5-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ae0c5-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ae0c5-136">Ensemble-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ae0c5-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ae0c5-137">Supprimer-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ae0c5-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)

