---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: L’applet de commande Unregister-CcAppliance annule l’inscription de l’appliance actuelle de la version Cloud Connector de Skype Entreprise à partir d’un site RTC dans la configuration client en ligne.
ms.openlocfilehash: 6ee21f66c2b189aff8c8aa7d831369536618b18c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250607"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="dd61f-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="dd61f-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="dd61f-104">L’applet de commande Unregister-CcAppliance annule l’inscription de l’appliance actuelle de la version Cloud Connector de Skype Entreprise à partir d’un site RTC dans la configuration client en ligne.</span><span class="sxs-lookup"><span data-stu-id="dd61f-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="dd61f-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="dd61f-105">Examples</span></span>
<span data-ttu-id="dd61f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="dd61f-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="dd61f-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="dd61f-107">Example 1</span></span>

<span data-ttu-id="dd61f-108">L’exemple suivant annule l’inscription d’une appliance actuelle à partir de la configuration client en ligne :</span><span class="sxs-lookup"><span data-stu-id="dd61f-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="dd61f-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="dd61f-109">Example 2</span></span>

<span data-ttu-id="dd61f-110">L’exemple suivant vérifie la configuration d’annulation d’inscription sans connexion à une configuration client en ligne :</span><span class="sxs-lookup"><span data-stu-id="dd61f-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="dd61f-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="dd61f-111">Example 3</span></span>

<span data-ttu-id="dd61f-112">L’exemple suivant annule l’inscription de l’appliance actuelle avec le nom « Appliance1 » vers le site RTC « Site1 » :</span><span class="sxs-lookup"><span data-stu-id="dd61f-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="dd61f-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="dd61f-113">Detailed Description</span></span>
<span data-ttu-id="dd61f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dd61f-114"></span></span>

<span data-ttu-id="dd61f-p101">Identique à l’applet de commande Register-CcAppliance, SiteName associé au FQDN externe du serveur Edge dans le fichier .ini de CloudConnector est considéré comme une identité de site RTC. De même, ApplianceName associé au FQDN du serveur de médiation dans le fichier .ini de CloudConnector est considéré comme une identité d’appliance.</span><span class="sxs-lookup"><span data-stu-id="dd61f-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="dd61f-117">Une fois que l’application est annulée, redémarrez le service de gestion en nuage connecteur et le journal sur le compte NetworkService.</span><span class="sxs-lookup"><span data-stu-id="dd61f-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="dd61f-118">Paramètres</span><span class="sxs-lookup"><span data-stu-id="dd61f-118">Parameters</span></span>
<span data-ttu-id="dd61f-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dd61f-119"></span></span>

|<span data-ttu-id="dd61f-120">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="dd61f-120">**Parameter**</span></span>|<span data-ttu-id="dd61f-121">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="dd61f-121">**Required**</span></span>|<span data-ttu-id="dd61f-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="dd61f-122">**Type**</span></span>|<span data-ttu-id="dd61f-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="dd61f-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="dd61f-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="dd61f-124">SiteName</span></span> <br/> |<span data-ttu-id="dd61f-125">Facultatif </span><span class="sxs-lookup"><span data-stu-id="dd61f-125">Optional</span></span>  <br/> |<span data-ttu-id="dd61f-126">System.String</span><span class="sxs-lookup"><span data-stu-id="dd61f-126">System.String</span></span>  <br/> |<span data-ttu-id="dd61f-p102">Le nom du site RTC où l’appliance est enregistrée. La valeur par défaut est la valeur SiteName dans le fichier CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="dd61f-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="dd61f-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="dd61f-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="dd61f-130">Facultatif </span><span class="sxs-lookup"><span data-stu-id="dd61f-130">Optional</span></span>  <br/> |<span data-ttu-id="dd61f-131">System.String</span><span class="sxs-lookup"><span data-stu-id="dd61f-131">System.String</span></span>  <br/> |<span data-ttu-id="dd61f-p103">Nom de l’appliance actuelle. La valeur par défaut est le nom de l’ordinateur du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="dd61f-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="dd61f-134">Local</span><span class="sxs-lookup"><span data-stu-id="dd61f-134">Local</span></span>  <br/> |<span data-ttu-id="dd61f-135">Facultatif</span><span class="sxs-lookup"><span data-stu-id="dd61f-135">Optional</span></span>  <br/> |<span data-ttu-id="dd61f-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="dd61f-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="dd61f-137">Vérifiez la configuration d’inscription locale sans connexion à une configuration client en ligne.</span><span class="sxs-lookup"><span data-stu-id="dd61f-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="dd61f-138">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="dd61f-138">Input Types</span></span>
<span data-ttu-id="dd61f-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dd61f-139"></span></span>

<span data-ttu-id="dd61f-p104">Aucun. L’applet de commande Unregister-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="dd61f-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="dd61f-142">Types de retours</span><span class="sxs-lookup"><span data-stu-id="dd61f-142">Return Types</span></span>
<span data-ttu-id="dd61f-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dd61f-143"></span></span>

<span data-ttu-id="dd61f-144">Aucun</span><span class="sxs-lookup"><span data-stu-id="dd61f-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd61f-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd61f-145">See also</span></span>
<span data-ttu-id="dd61f-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dd61f-146"></span></span>

[<span data-ttu-id="dd61f-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="dd61f-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="dd61f-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="dd61f-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="dd61f-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="dd61f-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="dd61f-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="dd61f-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

