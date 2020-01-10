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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'L’applet de commande Uninstall-CcAppliance désinstalle l’exécution de l’appliance de la version Cloud Connector de Skype Entreprise à partir du serveur hôte. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003144"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="807b8-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="807b8-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="807b8-104">L’applet de commande Uninstall-CcAppliance désinstalle l’exécution de l’appliance de la version Cloud Connector de Skype Entreprise à partir du serveur hôte. </span><span class="sxs-lookup"><span data-stu-id="807b8-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="807b8-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="807b8-105">Examples</span></span>
<span data-ttu-id="807b8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="807b8-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="807b8-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="807b8-107">Example 1</span></span>

<span data-ttu-id="807b8-108">Dans l’exemple suivant, l’appareil Cloud Connector est vidé et désinstallé du serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="807b8-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="807b8-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="807b8-109">Example 2</span></span>

<span data-ttu-id="807b8-110">L’exemple qui suit draine et force la désinstallation de l’application Cloud Connector sur le serveur hôte même si le processus de drainage a échoué :</span><span class="sxs-lookup"><span data-stu-id="807b8-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="807b8-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="807b8-111">Example 3</span></span>

<span data-ttu-id="807b8-112">Dans l’exemple suivant, la version de sauvegarde du connecteur Cloud est désinstallée sans confirmation de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="807b8-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="807b8-113">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="807b8-113">Detailed Description</span></span>
<span data-ttu-id="807b8-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="807b8-114"></span></span>

<span data-ttu-id="807b8-115">Si vous désinstallez la version actuelle du Cloud Connector, les services de drainage s’exécutent pour la première fois sur le serveur de médiation et sur le serveur Edge pour permettre aux appels concurrents de se terminer avant de désinstaller les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="807b8-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="807b8-116">Si vous êtes en train de désinstaller une version de sauvegarde, le nettoyage n'est pas exécuté :</span><span class="sxs-lookup"><span data-stu-id="807b8-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="807b8-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="807b8-117">Parameters</span></span>
<span data-ttu-id="807b8-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="807b8-118"></span></span>

|<span data-ttu-id="807b8-119">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="807b8-119">**Parameter**</span></span>|<span data-ttu-id="807b8-120">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="807b8-120">**Required**</span></span>|<span data-ttu-id="807b8-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="807b8-121">**Type**</span></span>|<span data-ttu-id="807b8-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="807b8-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="807b8-123">Version</span><span class="sxs-lookup"><span data-stu-id="807b8-123">Version</span></span> <br/> | <span data-ttu-id="807b8-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="807b8-124">Optional</span></span> <br/> |<span data-ttu-id="807b8-125">System.String</span><span class="sxs-lookup"><span data-stu-id="807b8-125">System.String</span></span>  <br/> | <span data-ttu-id="807b8-126">Version de Cloud Connector qui sera désinstallée à partir du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="807b8-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="807b8-127">Si cela n'est pas précisé, désinstallez la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="807b8-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="807b8-128">Force</span><span class="sxs-lookup"><span data-stu-id="807b8-128">Force</span></span>  <br/> |<span data-ttu-id="807b8-129">Facultatif</span><span class="sxs-lookup"><span data-stu-id="807b8-129">Optional</span></span>  <br/> |<span data-ttu-id="807b8-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="807b8-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="807b8-p103">Si vous désinstallez la version actuelle, essayez de nettoyer les serveurs sur le serveur de médiation et le serveur Edge avant de désinstaller les machines virtuelles. Si vous spécifiez le commutateur "Force", même si les services de nettoyage échouent, les machines virtuelles seront désinstallées. Ce paramètre est uniquement utilisé pour désinstaller la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="807b8-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="807b8-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="807b8-134">Confirm</span></span>  <br/> |<span data-ttu-id="807b8-135">Facultatif</span><span class="sxs-lookup"><span data-stu-id="807b8-135">Optional</span></span>  <br/> |<span data-ttu-id="807b8-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="807b8-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="807b8-137">Demandez confirmation à l’utilisateur de désinstaller les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="807b8-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="807b8-138">La valeur par défaut est TRUE.</span><span class="sxs-lookup"><span data-stu-id="807b8-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="807b8-139">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="807b8-139">Input Types</span></span>
<span data-ttu-id="807b8-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="807b8-140"></span></span>

<span data-ttu-id="807b8-p105">Aucun. L’applet de commande Uninstall-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="807b8-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="807b8-143">Types de retours</span><span class="sxs-lookup"><span data-stu-id="807b8-143">Return Types</span></span>
<span data-ttu-id="807b8-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="807b8-144"></span></span>

<span data-ttu-id="807b8-145">Aucun</span><span class="sxs-lookup"><span data-stu-id="807b8-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="807b8-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="807b8-146">See also</span></span>
<span data-ttu-id="807b8-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="807b8-147"></span></span>

[<span data-ttu-id="807b8-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="807b8-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="807b8-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="807b8-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="807b8-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="807b8-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="807b8-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="807b8-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

