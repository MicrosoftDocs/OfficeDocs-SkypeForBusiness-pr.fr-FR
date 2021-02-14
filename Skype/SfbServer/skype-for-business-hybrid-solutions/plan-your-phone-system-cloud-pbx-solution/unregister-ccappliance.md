---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: La cmdlet Unregister-CcAppliance désinsère l’appliance actuelle de la version Cloud Connector de Skype Entreprise à partir d’un site PSTN dans la configuration client en ligne.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824128"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="58ae8-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="58ae8-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="58ae8-104">La cmdlet Unregister-CcAppliance désinsère l’appliance actuelle de la version Cloud Connector de Skype Entreprise à partir d’un site PSTN dans la configuration client en ligne.</span><span class="sxs-lookup"><span data-stu-id="58ae8-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="58ae8-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="58ae8-105">Examples</span></span>
<span data-ttu-id="58ae8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="58ae8-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="58ae8-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="58ae8-107">Example 1</span></span>

<span data-ttu-id="58ae8-108">L’exemple suivant désinsère une appliance actuelle de la configuration du client en ligne :</span><span class="sxs-lookup"><span data-stu-id="58ae8-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="58ae8-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="58ae8-109">Example 2</span></span>

<span data-ttu-id="58ae8-110">L’exemple suivant vérifie la configuration pour la désinsister localement sans se connecter à la configuration du client en ligne :</span><span class="sxs-lookup"><span data-stu-id="58ae8-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="58ae8-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="58ae8-111">Example 3</span></span>

<span data-ttu-id="58ae8-112">L’exemple suivant désinsère l’appliance actuelle avec le nom « Appliance1 » sur le site PSTN « Site1 » :</span><span class="sxs-lookup"><span data-stu-id="58ae8-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="58ae8-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="58ae8-113">Detailed Description</span></span>
<span data-ttu-id="58ae8-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="58ae8-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="58ae8-115">À l'Register-CcAppliance, SiteName associé au nom de groupe externe du serveur Edge dans le fichier CloudConnector.ini est considéré comme une identité de site PSTN.</span><span class="sxs-lookup"><span data-stu-id="58ae8-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="58ae8-116">De même, ApplianceName combiné au nom de CloudConnector.ini serveur de médiation est considéré comme une identité d’appliance.</span><span class="sxs-lookup"><span data-stu-id="58ae8-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="58ae8-117">Une fois l’appliance désinsérée, redémarrez le service de gestion Cloud Connector et connectez-vous en tant que compte NetworkService.</span><span class="sxs-lookup"><span data-stu-id="58ae8-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="58ae8-118">Paramètres</span><span class="sxs-lookup"><span data-stu-id="58ae8-118">Parameters</span></span>
<span data-ttu-id="58ae8-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="58ae8-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="58ae8-120">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="58ae8-120">**Parameter**</span></span>|<span data-ttu-id="58ae8-121">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="58ae8-121">**Required**</span></span>|<span data-ttu-id="58ae8-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="58ae8-122">**Type**</span></span>|<span data-ttu-id="58ae8-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="58ae8-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="58ae8-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="58ae8-124">SiteName</span></span> <br/> |<span data-ttu-id="58ae8-125">Facultatif</span><span class="sxs-lookup"><span data-stu-id="58ae8-125">Optional</span></span>  <br/> |<span data-ttu-id="58ae8-126">System.String</span><span class="sxs-lookup"><span data-stu-id="58ae8-126">System.String</span></span>  <br/> |<span data-ttu-id="58ae8-127">Nom du site PSTN où l’appliance est inscrite.</span><span class="sxs-lookup"><span data-stu-id="58ae8-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="58ae8-128">La valeur par défaut est La valeur SiteName dans CloudConnector.ini fichier.</span><span class="sxs-lookup"><span data-stu-id="58ae8-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="58ae8-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="58ae8-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="58ae8-130">Facultatif</span><span class="sxs-lookup"><span data-stu-id="58ae8-130">Optional</span></span>  <br/> |<span data-ttu-id="58ae8-131">System.String</span><span class="sxs-lookup"><span data-stu-id="58ae8-131">System.String</span></span>  <br/> |<span data-ttu-id="58ae8-132">Nom de l’appliance actuelle.</span><span class="sxs-lookup"><span data-stu-id="58ae8-132">Name of the current appliance.</span></span> <span data-ttu-id="58ae8-133">La valeur par défaut est le nom de l’ordinateur du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="58ae8-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="58ae8-134">Local</span><span class="sxs-lookup"><span data-stu-id="58ae8-134">Local</span></span>  <br/> |<span data-ttu-id="58ae8-135">Facultatif</span><span class="sxs-lookup"><span data-stu-id="58ae8-135">Optional</span></span>  <br/> |<span data-ttu-id="58ae8-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="58ae8-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="58ae8-137">Vérifiez la configuration de l’inscription localement sans vous connecter à une configuration client en ligne.</span><span class="sxs-lookup"><span data-stu-id="58ae8-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="58ae8-138">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="58ae8-138">Input Types</span></span>
<span data-ttu-id="58ae8-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="58ae8-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="58ae8-140">Aucun.</span><span class="sxs-lookup"><span data-stu-id="58ae8-140">None.</span></span> <span data-ttu-id="58ae8-141">La cmdlet Unregister-CcAppliance n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="58ae8-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="58ae8-142">Types de retour</span><span class="sxs-lookup"><span data-stu-id="58ae8-142">Return Types</span></span>
<span data-ttu-id="58ae8-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="58ae8-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="58ae8-144">Aucun</span><span class="sxs-lookup"><span data-stu-id="58ae8-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58ae8-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58ae8-145">See also</span></span>
<span data-ttu-id="58ae8-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="58ae8-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="58ae8-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="58ae8-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="58ae8-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="58ae8-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="58ae8-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="58ae8-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="58ae8-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="58ae8-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

