---
title: Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 1a9e719e6c008fcd8bf8c12612f8eea15447648e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009707"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="b97f3-103">Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="b97f3-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="b97f3-104">Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b97f3-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="b97f3-105">Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b97f3-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b97f3-106">Pour activer le contrôle d’admission des appels à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b97f3-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b97f3-107">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b97f3-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b97f3-p101">Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="b97f3-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="b97f3-110">Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b97f3-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b97f3-111">Pour activer le contrôle d’admission des appels à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="b97f3-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b97f3-112">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="b97f3-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b97f3-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="b97f3-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b97f3-114">Cliquez sur le bouton de navigation **Global**.</span><span class="sxs-lookup"><span data-stu-id="b97f3-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="b97f3-115">Cliquez sur **Global** dans la liste, puis sélectionnez **Afficher les détails** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="b97f3-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="b97f3-116">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.</span><span class="sxs-lookup"><span data-stu-id="b97f3-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b97f3-117">Si vous souhaitez désactiver le contrôle d’admission des appels dans tout votre déploiement, désactivez cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="b97f3-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="b97f3-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b97f3-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b97f3-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b97f3-119">See also</span></span>

[<span data-ttu-id="b97f3-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b97f3-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="b97f3-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b97f3-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="b97f3-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b97f3-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)