---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement E9-1-1 aux sites du réseau dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: d30f9295b633ccfa7439e697931b13bd92b1cc0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893174"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="cfb12-103">Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="cfb12-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="cfb12-104">Affecter des stratégies d’emplacement E9-1-1 aux sites du réseau dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cfb12-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="cfb12-105">Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans les [stratégies d’emplacement créer Skype pour Business Server](create-location-policies.md) à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="cfb12-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="cfb12-106">Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="cfb12-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="cfb12-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="cfb12-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="cfb12-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="cfb12-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="cfb12-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="cfb12-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="cfb12-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="cfb12-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="cfb12-111">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="cfb12-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="cfb12-112">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cfb12-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cfb12-113">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="cfb12-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="cfb12-114">Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="cfb12-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="cfb12-115">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="cfb12-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="cfb12-116">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cfb12-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cfb12-117">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="cfb12-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="cfb12-118">Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="cfb12-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


