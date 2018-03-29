---
title: Activation du contrôle d’admission des appels dans Skype Entreprise Server 2015
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Activer le contrôle d’admission appel dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 52425dffc788ab2d1e6822957f30b67e00cb7a9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="47e8d-103">Activation du contrôle d’admission des appels dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="47e8d-103">Enable call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="47e8d-104">Activer le contrôle d’admission appel dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="47e8d-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="47e8d-105">Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.</span><span class="sxs-lookup"><span data-stu-id="47e8d-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="47e8d-106">Pour activer l’appel de contrôle d’admission pour Business Server Management Shell à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="47e8d-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="47e8d-107">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="47e8d-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="47e8d-p101">Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="47e8d-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="47e8d-110">Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="47e8d-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="47e8d-111">Pour activer l’appel de contrôle d’admission pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="47e8d-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="47e8d-112">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="47e8d-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="47e8d-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="47e8d-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="47e8d-114">Cliquez sur le bouton de navigation **Global**.</span><span class="sxs-lookup"><span data-stu-id="47e8d-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="47e8d-115">Cliquez sur **Global** dans la liste, puis sélectionnez **Afficher les détails** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="47e8d-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="47e8d-116">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.</span><span class="sxs-lookup"><span data-stu-id="47e8d-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47e8d-117">Si vous souhaitez désactiver le contrôle d’admission des appels dans tout votre déploiement, désactivez cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="47e8d-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="47e8d-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="47e8d-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="47e8d-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47e8d-119">See also</span></span>

#### 

[<span data-ttu-id="47e8d-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="47e8d-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="47e8d-121">Ensemble-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="47e8d-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="47e8d-122">Supprimer-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="47e8d-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)

