---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement E9-1-1 aux sites du réseau dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 7a6930fddcadc9b9eb772d20c21ff1e13be6bef0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890345"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="3f40c-103">Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="3f40c-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="3f40c-104">Affecter des stratégies d’emplacement E9-1-1 aux sites du réseau dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3f40c-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="3f40c-105">Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans les [stratégies d’emplacement créer Skype pour Business Server](create-location-policies.md) à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="3f40c-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="3f40c-106">Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f40c-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="3f40c-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3f40c-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="3f40c-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3f40c-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="3f40c-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3f40c-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="3f40c-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="3f40c-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="3f40c-111">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="3f40c-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="3f40c-112">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3f40c-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3f40c-113">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="3f40c-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="3f40c-114">Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="3f40c-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="3f40c-115">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="3f40c-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="3f40c-116">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3f40c-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3f40c-117">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="3f40c-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="3f40c-118">Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="3f40c-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


