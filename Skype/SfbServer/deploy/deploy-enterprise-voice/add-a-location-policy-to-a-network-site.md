---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype Entreprise Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement E9-1-1 à des sites réseau dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804274"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="6fdcf-103">Ajouter une stratégie d’emplacement à un site réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6fdcf-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="6fdcf-104">Affecter des stratégies d’emplacement E9-1-1 à des sites réseau dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="6fdcf-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="6fdcf-105">Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans Créer des stratégies d’emplacement dans [Skype](create-location-policies.md) Entreprise Server à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **de Redmond.**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="6fdcf-106">Pour plus d’informations sur l’working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6fdcf-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="6fdcf-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="6fdcf-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="6fdcf-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="6fdcf-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="6fdcf-111">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="6fdcf-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="6fdcf-112">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6fdcf-113">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="6fdcf-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="6fdcf-114">Affectez la stratégie d’emplacement balisé **Redmond** à un site réseau existant nommé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="6fdcf-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="6fdcf-115">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="6fdcf-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="6fdcf-116">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="6fdcf-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6fdcf-117">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="6fdcf-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="6fdcf-118">Créez un nouveau site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="6fdcf-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


