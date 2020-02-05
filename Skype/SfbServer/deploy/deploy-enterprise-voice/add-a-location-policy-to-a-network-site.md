---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Attribuez des stratégies d’emplacement E9-1-1 aux sites réseau dans Skype entreprise Server Voice.
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768277"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="bd1f0-103">Ajouter une stratégie d’emplacement à un site réseau dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bd1f0-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="bd1f0-104">Attribuez des stratégies d’emplacement E9-1-1 aux sites réseau dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="bd1f0-105">Les exemples suivants montrent comment ajouter la stratégie d’emplacement de **Redmond** définie dans [créer des stratégies d’emplacement dans Skype entreprise Server](create-location-policies.md) à un site réseau existant et comment créer un site réseau qui utilise la politique de localisation de **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="bd1f0-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="bd1f0-106">Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd1f0-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="bd1f0-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="bd1f0-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="bd1f0-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="bd1f0-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="bd1f0-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="bd1f0-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="bd1f0-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="bd1f0-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="bd1f0-111">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="bd1f0-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="bd1f0-112">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="bd1f0-113">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="bd1f0-114">Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="bd1f0-115">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="bd1f0-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="bd1f0-116">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="bd1f0-117">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="bd1f0-118">Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


