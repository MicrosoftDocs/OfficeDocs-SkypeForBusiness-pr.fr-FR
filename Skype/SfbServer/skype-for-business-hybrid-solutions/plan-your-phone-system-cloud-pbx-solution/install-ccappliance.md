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
description: "	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte. "
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799874"
---
# <a name="install-ccappliance"></a><span data-ttu-id="a8b42-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a8b42-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="a8b42-104">	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte. </span><span class="sxs-lookup"><span data-stu-id="a8b42-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a8b42-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="a8b42-105">Examples</span></span>
<span data-ttu-id="a8b42-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b42-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a8b42-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="a8b42-107">Example 1</span></span>

<span data-ttu-id="a8b42-108">Dans l’exemple suivant, une nouvelle application de connecteur Cloud est installée sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="a8b42-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="a8b42-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="a8b42-109">Example 2</span></span>

<span data-ttu-id="a8b42-110">L’exemple suivant met à niveau le Cloud Connector vers la version la plus récente :</span><span class="sxs-lookup"><span data-stu-id="a8b42-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="a8b42-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="a8b42-111">Example 3</span></span>

<span data-ttu-id="a8b42-112">Dans l’exemple suivant, toutes les informations d’identification Cloud Connector sont supprimées sur le serveur hôte, inviter l’utilisateur à spécifier de nouveau toutes les informations d’identification, puis installe Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="a8b42-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="a8b42-113">Exemple 4</span><span class="sxs-lookup"><span data-stu-id="a8b42-113">Example 4</span></span>

<span data-ttu-id="a8b42-114">L'exempe suivant affiche toutes les étapes de déploiement dans la console PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a8b42-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="a8b42-115">Le paramètre ShowStepsOnly est uniquement dédié à la résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="a8b42-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="a8b42-116">Exemple 5</span><span class="sxs-lookup"><span data-stu-id="a8b42-116">Example 5</span></span>

<span data-ttu-id="a8b42-117">L’exemple suivant crée des fichiers de configuration pour chaque étape de déploiement sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="a8b42-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="a8b42-118">Les fichiers de configuration sont enregistrés \<dans\>le\\ dossier ApplianceRoot\>\Instances<version-default\ExportedConfig sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="a8b42-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="a8b42-119">Pour déterminer la racine de l’appliance, exécutez l’applet de commande Get-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="a8b42-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="a8b42-120">Exemple 6</span><span class="sxs-lookup"><span data-stu-id="a8b42-120">Example 6</span></span>

<span data-ttu-id="a8b42-p102">Dans l’exemple suivant, Cloud Connector exécute les étapes 1,2 et 3 de déploiement pour créer des commutateurs virtuels, une machine virtuelle AD et installer le service de domaine sur le serveur AD. Il passe l’étape si elle a déjà été exécutée :</span><span class="sxs-lookup"><span data-stu-id="a8b42-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="a8b42-123">Le paramètre SkipExistingObjects doit être utilisé conjointement avec le paramètre Étapes.</span><span class="sxs-lookup"><span data-stu-id="a8b42-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8b42-124">Le paramètre Étapes est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="a8b42-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="a8b42-125">N’utilisez pas ce paramètre pour déployer une appliance ou mettre à niveau une appliance en service.</span><span class="sxs-lookup"><span data-stu-id="a8b42-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="a8b42-126">Pour déterminer les étapes du déploiement, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a8b42-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="a8b42-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="a8b42-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="a8b42-128">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="a8b42-128">Detailed Description</span></span>
<span data-ttu-id="a8b42-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b42-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a8b42-130">L’applet de contrôle install-CcAppliance est utilisée pour déployer le Cloud Connector sur une nouvelle application ou pour mettre à niveau un appareil existant vers la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="a8b42-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="a8b42-131">Si vous disposez d’une nouvelle appliance, commencez par lire Préparation de votre environnement pour Cloud Connector, exécutez l’applet de commande Register-CcAppliance afin d’enregistrer l’appliance, puis exécutez l’applet de commande Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="a8b42-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="a8b42-132">Pour plus d’informations, reportez-vous à la rubrique [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a8b42-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="a8b42-133">Si vous avez un déploiement de Cloud Connector et que vous souhaitez effectuer une mise à niveau, suivez les instructions de la procédure de [mise à niveau vers une nouvelle version de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a8b42-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a8b42-134">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a8b42-134">Parameters</span></span>
<span data-ttu-id="a8b42-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b42-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a8b42-136">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="a8b42-136">**Parameter**</span></span>|<span data-ttu-id="a8b42-137">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="a8b42-137">**Required**</span></span>|<span data-ttu-id="a8b42-138">**Type**</span><span class="sxs-lookup"><span data-stu-id="a8b42-138">**Type**</span></span>|<span data-ttu-id="a8b42-139">**Description**</span><span class="sxs-lookup"><span data-stu-id="a8b42-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8b42-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="a8b42-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="a8b42-141">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a8b42-141">Optional</span></span>  <br/> |<span data-ttu-id="a8b42-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a8b42-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="a8b42-p105">Création de fichiers de configuration pour chaque étape de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes. </span><span class="sxs-lookup"><span data-stu-id="a8b42-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="a8b42-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="a8b42-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="a8b42-146">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a8b42-146">Optional</span></span>  <br/> |<span data-ttu-id="a8b42-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a8b42-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a8b42-p106">Affichage des noms des étapes de déploiement uniquement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="a8b42-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="a8b42-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="a8b42-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="a8b42-151">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a8b42-151">Optional</span></span>  <br/> |<span data-ttu-id="a8b42-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a8b42-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a8b42-p107">Ce paramètre doit être utilisé conjointement avec le paramètre Étapes. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="a8b42-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="a8b42-155">Étapes</span><span class="sxs-lookup"><span data-stu-id="a8b42-155">Steps</span></span>  <br/> |<span data-ttu-id="a8b42-156">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a8b42-156">Optional</span></span>  <br/> |<span data-ttu-id="a8b42-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="a8b42-157">System.Array</span></span>  <br/> |<span data-ttu-id="a8b42-p108">Exécution des étapes de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="a8b42-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="a8b42-160">Mise à niveau</span><span class="sxs-lookup"><span data-stu-id="a8b42-160">Upgrade</span></span>  <br/> |<span data-ttu-id="a8b42-161">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a8b42-161">Optional</span></span>  <br/> |<span data-ttu-id="a8b42-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a8b42-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a8b42-163">Mise à niveau du Cloud Connector existant vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="a8b42-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="a8b42-164">Mise à jour de toutes les informations</span><span class="sxs-lookup"><span data-stu-id="a8b42-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="a8b42-165">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a8b42-165">Optional</span></span>  <br/> |<span data-ttu-id="a8b42-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a8b42-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a8b42-167">Supprimez toutes les informations d’identification Cloud Connector dans le cache.</span><span class="sxs-lookup"><span data-stu-id="a8b42-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="a8b42-168">Demandez à l’utilisateur de spécifier de nouvelles informations pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="a8b42-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a8b42-169">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="a8b42-169">Input Types</span></span>
<span data-ttu-id="a8b42-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b42-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a8b42-p110">Aucun. L’applet de commande Install-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="a8b42-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a8b42-173">Types de retours</span><span class="sxs-lookup"><span data-stu-id="a8b42-173">Return Types</span></span>
<span data-ttu-id="a8b42-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b42-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a8b42-175">Aucun</span><span class="sxs-lookup"><span data-stu-id="a8b42-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8b42-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8b42-176">See also</span></span>
<span data-ttu-id="a8b42-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b42-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a8b42-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a8b42-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="a8b42-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a8b42-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="a8b42-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a8b42-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="a8b42-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a8b42-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

