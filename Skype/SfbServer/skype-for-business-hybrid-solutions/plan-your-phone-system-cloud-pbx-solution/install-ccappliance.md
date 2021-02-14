---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: L'Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, y compris les machines virtuelles AD, Central Management Store, Mediation Server et Edge Server, sur le serveur hôte.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799874"
---
# <a name="install-ccappliance"></a><span data-ttu-id="0e2e4-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e2e4-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="0e2e4-104">L'Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, y compris les machines virtuelles AD, Central Management Store, Mediation Server et Edge Server, sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0e2e4-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="0e2e4-105">Examples</span></span>
<span data-ttu-id="0e2e4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e2e4-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0e2e4-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0e2e4-107">Example 1</span></span>

<span data-ttu-id="0e2e4-108">L’exemple suivant installe une nouvelle appliance Cloud Connector sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="0e2e4-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0e2e4-109">Example 2</span></span>

<span data-ttu-id="0e2e4-110">L’exemple suivant permet de mettre à niveau Cloud Connector vers la dernière version :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="0e2e4-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="0e2e4-111">Example 3</span></span>

<span data-ttu-id="0e2e4-112">L’exemple suivant supprime toutes les informations d’identification Cloud Connector mises en cache sur le serveur hôte, invite l’utilisateur à spécifier à nouveau toutes les informations d’identification, puis installe Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="0e2e4-113">Exemple 4</span><span class="sxs-lookup"><span data-stu-id="0e2e4-113">Example 4</span></span>

<span data-ttu-id="0e2e4-114">L’exemple suivant affiche toutes les étapes de déploiement dans la console PowerShell :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="0e2e4-115">Le paramètre -ShowStepsOnly est uniquement pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="0e2e4-116">Exemple 5</span><span class="sxs-lookup"><span data-stu-id="0e2e4-116">Example 5</span></span>

<span data-ttu-id="0e2e4-117">L’exemple suivant génère des fichiers de configuration pour chaque étape de déploiement sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="0e2e4-118">Les fichiers de configuration sont enregistrés dans le \< dossier ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="0e2e4-119">Pour déterminer la racine de l’appliance, exécutez Get-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="0e2e4-120">Exemple 6</span><span class="sxs-lookup"><span data-stu-id="0e2e4-120">Example 6</span></span>

<span data-ttu-id="0e2e4-121">Dans l’exemple suivant, Cloud Connector exécute les étapes de déploiement 1, 2 et 3 pour créer des commutateurs virtuels, créer une machine virtuelle AD et installer le service de domaine sur le serveur AD.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="0e2e4-122">Il ignore l’étape si l’étape a déjà été exécutée :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="0e2e4-123">Le paramètre SkipExistingObjects doit être utilisé conjointement avec le paramètre Steps.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e2e4-124">Le paramètre Steps est uniquement à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="0e2e4-125">N’utilisez pas ce paramètre pour déployer une appliance ou mettre à niveau une appliance en service.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="0e2e4-126">Pour déterminer les étapes du déploiement, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0e2e4-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="0e2e4-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="0e2e4-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="0e2e4-128">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="0e2e4-128">Detailed Description</span></span>
<span data-ttu-id="0e2e4-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e2e4-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0e2e4-130">LInstall-CcAppliance cmdlet est utilisée pour déployer Cloud Connector sur une nouvelle appliance ou pour mettre à niveau une appliance existante vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="0e2e4-131">Si vous avez une nouvelle appliance, lisez d’abord Préparer votre environnement pour Cloud Connector, exécutez l’cmdlet Register-CcAppliance pour inscrire l’appliance, puis exécutez l'Install-CcAppliance cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="0e2e4-132">Pour plus d’informations, voir [Déployer un seul site dans Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et Déployer plusieurs sites dans Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="0e2e4-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="0e2e4-133">Si vous avez un déploiement existant de Cloud Connector et que vous souhaitez mettre à niveau, suivez les instructions de la mise à niveau vers une [nouvelle version de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="0e2e4-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0e2e4-134">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0e2e4-134">Parameters</span></span>
<span data-ttu-id="0e2e4-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e2e4-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0e2e4-136">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="0e2e4-136">**Parameter**</span></span>|<span data-ttu-id="0e2e4-137">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="0e2e4-137">**Required**</span></span>|<span data-ttu-id="0e2e4-138">**Type**</span><span class="sxs-lookup"><span data-stu-id="0e2e4-138">**Type**</span></span>|<span data-ttu-id="0e2e4-139">**Description**</span><span class="sxs-lookup"><span data-stu-id="0e2e4-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e2e4-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="0e2e4-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="0e2e4-141">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0e2e4-141">Optional</span></span>  <br/> |<span data-ttu-id="0e2e4-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0e2e4-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="0e2e4-143">Générer des fichiers de configuration pour chaque étape de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="0e2e4-144">Ce paramètre est uniquement pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="0e2e4-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="0e2e4-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="0e2e4-146">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0e2e4-146">Optional</span></span>  <br/> |<span data-ttu-id="0e2e4-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0e2e4-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0e2e4-148">Afficher uniquement les noms des étapes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-148">Display deployment step names only.</span></span> <span data-ttu-id="0e2e4-149">Ce paramètre est uniquement pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="0e2e4-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="0e2e4-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="0e2e4-151">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0e2e4-151">Optional</span></span>  <br/> |<span data-ttu-id="0e2e4-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0e2e4-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0e2e4-153">Ce paramètre doit être utilisé conjointement avec le paramètre Steps.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="0e2e4-154">Ce paramètre est uniquement pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="0e2e4-155">Étapes</span><span class="sxs-lookup"><span data-stu-id="0e2e4-155">Steps</span></span>  <br/> |<span data-ttu-id="0e2e4-156">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0e2e4-156">Optional</span></span>  <br/> |<span data-ttu-id="0e2e4-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="0e2e4-157">System.Array</span></span>  <br/> |<span data-ttu-id="0e2e4-158">Exécutez les étapes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-158">Run the deployment steps.</span></span> <span data-ttu-id="0e2e4-159">Ce paramètre est uniquement pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="0e2e4-160">Mise à niveau</span><span class="sxs-lookup"><span data-stu-id="0e2e4-160">Upgrade</span></span>  <br/> |<span data-ttu-id="0e2e4-161">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0e2e4-161">Optional</span></span>  <br/> |<span data-ttu-id="0e2e4-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0e2e4-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0e2e4-163">Mettre à niveau le Cloud Connector existant vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="0e2e4-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="0e2e4-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="0e2e4-165">Facultatif</span><span class="sxs-lookup"><span data-stu-id="0e2e4-165">Optional</span></span>  <br/> |<span data-ttu-id="0e2e4-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0e2e4-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0e2e4-167">Supprimez toutes les informations d’identification Cloud Connector dans le cache.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="0e2e4-168">Invitez l’utilisateur à spécifier de nouvelles informations d’identification pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0e2e4-169">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="0e2e4-169">Input Types</span></span>
<span data-ttu-id="0e2e4-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e2e4-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0e2e4-171">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-171">None.</span></span> <span data-ttu-id="0e2e4-172">La cmdlet Install-CcAppliance n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="0e2e4-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0e2e4-173">Types de retour</span><span class="sxs-lookup"><span data-stu-id="0e2e4-173">Return Types</span></span>
<span data-ttu-id="0e2e4-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e2e4-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0e2e4-175">Aucun</span><span class="sxs-lookup"><span data-stu-id="0e2e4-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e2e4-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e2e4-176">See also</span></span>
<span data-ttu-id="0e2e4-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e2e4-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0e2e4-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e2e4-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="0e2e4-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e2e4-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="0e2e4-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e2e4-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="0e2e4-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0e2e4-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

