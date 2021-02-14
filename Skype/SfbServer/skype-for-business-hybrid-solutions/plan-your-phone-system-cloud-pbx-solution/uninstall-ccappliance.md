---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: La cmdlet Uninstall-CcAppliance désinstalle l’appliance de la version Cloud Connector de Skype Entreprise en cours d’exécution du serveur hôte.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824138"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="02676-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="02676-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="02676-104">La cmdlet Uninstall-CcAppliance désinstalle l’appliance de la version Cloud Connector de Skype Entreprise en cours d’exécution du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="02676-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="02676-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="02676-105">Examples</span></span>
<span data-ttu-id="02676-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="02676-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="02676-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="02676-107">Example 1</span></span>

<span data-ttu-id="02676-108">L’exemple suivant draine et désinstalle l’appliance Cloud Connector du serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="02676-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="02676-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="02676-109">Example 2</span></span>

<span data-ttu-id="02676-110">L’exemple suivant draine et force la désinstallation de l’appliance Cloud Connector en cours d’exécution sur le serveur hôte, même si le processus de drainage a échoué :</span><span class="sxs-lookup"><span data-stu-id="02676-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="02676-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="02676-111">Example 3</span></span>

<span data-ttu-id="02676-112">L’exemple suivant désinstalle une version de sauvegarde Cloud Connector sans confirmation de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="02676-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="02676-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="02676-113">Detailed Description</span></span>
<span data-ttu-id="02676-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="02676-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="02676-115">Si vous désinstallez la version actuelle de Cloud Connector, les services de drainage sont d’abord exécutés sur le serveur de médiation et le serveur Edge pour laisser les appels simultanés se terminer avant de désinstaller les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="02676-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="02676-116">Si vous désinstallez une version de sauvegarde, le drainage n’est pas effectué.</span><span class="sxs-lookup"><span data-stu-id="02676-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="02676-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="02676-117">Parameters</span></span>
<span data-ttu-id="02676-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="02676-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="02676-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="02676-119">**Parameter**</span></span>|<span data-ttu-id="02676-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="02676-120">**Required**</span></span>|<span data-ttu-id="02676-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="02676-121">**Type**</span></span>|<span data-ttu-id="02676-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="02676-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="02676-123">Version</span><span class="sxs-lookup"><span data-stu-id="02676-123">Version</span></span> <br/> | <span data-ttu-id="02676-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="02676-124">Optional</span></span> <br/> |<span data-ttu-id="02676-125">System.String</span><span class="sxs-lookup"><span data-stu-id="02676-125">System.String</span></span>  <br/> | <span data-ttu-id="02676-126">Version de Cloud Connector qui sera désinstallée du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="02676-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="02676-127">Si elle n’est pas spécifiée, désinstallez la version en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="02676-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="02676-128">Force</span><span class="sxs-lookup"><span data-stu-id="02676-128">Force</span></span>  <br/> |<span data-ttu-id="02676-129">Facultatif</span><span class="sxs-lookup"><span data-stu-id="02676-129">Optional</span></span>  <br/> |<span data-ttu-id="02676-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="02676-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="02676-131">Si vous désinstallez la version en cours d’exécution, essayez de vider les serveurs sur le serveur de médiation et le serveur Edge avant de désinstaller les ordinateurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="02676-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="02676-132">Si vous spécifiez le commutateur « Force », même si les services de drainage échouent, les machines virtuelles sont désinstallées.</span><span class="sxs-lookup"><span data-stu-id="02676-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="02676-133">Ce paramètre est utilisé uniquement pour désinstaller la version en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="02676-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="02676-134">Confirmer</span><span class="sxs-lookup"><span data-stu-id="02676-134">Confirm</span></span>  <br/> |<span data-ttu-id="02676-135">Facultatif</span><span class="sxs-lookup"><span data-stu-id="02676-135">Optional</span></span>  <br/> |<span data-ttu-id="02676-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="02676-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="02676-137">Demandez la confirmation de l’utilisateur pour désinstaller les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="02676-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="02676-138">La valeur par défaut est TRUE.</span><span class="sxs-lookup"><span data-stu-id="02676-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="02676-139">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="02676-139">Input Types</span></span>
<span data-ttu-id="02676-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="02676-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="02676-141">Aucun.</span><span class="sxs-lookup"><span data-stu-id="02676-141">None.</span></span> <span data-ttu-id="02676-142">La cmdlet Uninstall-CcAppliance n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="02676-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="02676-143">Types de retour</span><span class="sxs-lookup"><span data-stu-id="02676-143">Return Types</span></span>
<span data-ttu-id="02676-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="02676-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="02676-145">Aucun</span><span class="sxs-lookup"><span data-stu-id="02676-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02676-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02676-146">See also</span></span>
<span data-ttu-id="02676-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="02676-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="02676-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="02676-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="02676-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="02676-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="02676-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="02676-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="02676-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="02676-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

