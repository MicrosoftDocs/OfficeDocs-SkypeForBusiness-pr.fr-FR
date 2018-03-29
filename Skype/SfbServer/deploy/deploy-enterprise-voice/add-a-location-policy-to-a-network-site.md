---
title: Ajout d’une stratégie d’emplacement à un site réseau dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement de E9-1-1 pour les sites de réseau de Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="d0f7d-103">Ajout d’une stratégie d’emplacement à un site réseau dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d0f7d-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d0f7d-104">Affecter des stratégies d’emplacement de E9-1-1 pour les sites de réseau de Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d0f7d-105">Les exemples suivants montrent comment ajouter la stratégie d’emplacement de **Redmond** définie dans les [stratégies d’emplacement de créer dans Skype pour Business Server 2015](create-location-policies.md) à un site de réseau existant et comment créer un nouveau site de réseau qui utilise le site de **Redmond** stratégie.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="d0f7d-106">Pour plus d’informations sur l’utilisation des sites du réseau, consultez la documentation de Communications Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0f7d-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="d0f7d-107">**Nouvelle-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d0f7d-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="d0f7d-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d0f7d-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="d0f7d-109">**Ensemble-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d0f7d-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="d0f7d-110">**Supprimer-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d0f7d-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="d0f7d-111">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="d0f7d-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="d0f7d-112">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0f7d-113">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="d0f7d-114">Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="d0f7d-115">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="d0f7d-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="d0f7d-116">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0f7d-117">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="d0f7d-118">Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d0f7d-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


