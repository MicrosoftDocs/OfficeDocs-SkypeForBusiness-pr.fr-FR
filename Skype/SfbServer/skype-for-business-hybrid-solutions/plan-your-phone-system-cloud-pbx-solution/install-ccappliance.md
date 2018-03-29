---
title: Installation-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: "	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte. "
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a><span data-ttu-id="fb832-103">Installation-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fb832-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="fb832-104">	L'applet de commande Install-CcAppliance installe l’appliance de la version Cloud Connector de Skype Entreprise, notamment les machines virtuelles de l’AD, du magasin central de gestion, du serveur de médiation et du serveur Edge, sur le serveur hôte. </span><span class="sxs-lookup"><span data-stu-id="fb832-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a><span data-ttu-id="fb832-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="fb832-105">Examples</span></span>
<span data-ttu-id="fb832-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fb832-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="fb832-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="fb832-107">Example 1</span></span>

<span data-ttu-id="fb832-108">L’exemple suivant installe un nouveau matériel de nuage connecteur sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="fb832-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="fb832-109">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="fb832-109">Example 2</span></span>

<span data-ttu-id="fb832-110">L’exemple suivant met à niveau le connecteur du nuage vers la dernière version :</span><span class="sxs-lookup"><span data-stu-id="fb832-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="fb832-111">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="fb832-111">Example 3</span></span>

<span data-ttu-id="fb832-112">L’exemple suivant supprime toutes les informations d’identification de nuage connecteur mis en cache sur le serveur hôte, invite l’utilisateur à spécifier à nouveau les informations d’identification tous les, puis installe le connecteur du nuage :</span><span class="sxs-lookup"><span data-stu-id="fb832-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="fb832-113">Exemple 4</span><span class="sxs-lookup"><span data-stu-id="fb832-113">Example 4</span></span>

<span data-ttu-id="fb832-114">L'exempe suivant affiche toutes les étapes de déploiement dans la console PowerShell :</span><span class="sxs-lookup"><span data-stu-id="fb832-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="fb832-115">Le paramètre ShowStepsOnly est uniquement dédié à la résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="fb832-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="fb832-116">Exemple 5</span><span class="sxs-lookup"><span data-stu-id="fb832-116">Example 5</span></span>

<span data-ttu-id="fb832-117">L’exemple suivant crée des fichiers de configuration pour chaque étape de déploiement sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="fb832-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="fb832-118">Fichiers de configuration sont enregistrés dans le \<ApplianceRoot\>\Instances\\< Version\>-dossier default\ExportedConfig sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="fb832-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="fb832-119">Pour déterminer la racine de l’appliance, exécutez l’applet de commande Get-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="fb832-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="fb832-120">Exemple 6</span><span class="sxs-lookup"><span data-stu-id="fb832-120">Example 6</span></span>

<span data-ttu-id="fb832-p102">Dans l’exemple suivant, Cloud Connector exécute les étapes 1,2 et 3 de déploiement pour créer des commutateurs virtuels, une machine virtuelle AD et installer le service de domaine sur le serveur AD. Il passe l’étape si elle a déjà été exécutée :</span><span class="sxs-lookup"><span data-stu-id="fb832-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="fb832-123">Le paramètre SkipExistingObjects doit être utilisé conjointement avec le paramètre Étapes.</span><span class="sxs-lookup"><span data-stu-id="fb832-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb832-124">Le paramètre Étapes est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="fb832-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="fb832-125">N’utilisez pas ce paramètre pour déployer une appliance ou mettre à niveau une appliance en service.</span><span class="sxs-lookup"><span data-stu-id="fb832-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="fb832-126">Pour déterminer les étapes du déploiement, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fb832-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="fb832-127">Installation-CcAppliance - ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="fb832-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="fb832-128">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="fb832-128">Detailed Description</span></span>
<span data-ttu-id="fb832-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fb832-129"></span></span>

<span data-ttu-id="fb832-130">L’applet de commande Install-CcAppliance est utilisé pour déployer le Cloud connecteur sur un nouveau matériel ou d’une appliance existante de mise à niveau vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="fb832-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="fb832-131">Si vous disposez d’une nouvelle appliance, commencez par lire Préparation de votre environnement pour Cloud Connector, exécutez l’applet de commande Register-CcAppliance afin d’enregistrer l’appliance, puis exécutez l’applet de commande Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="fb832-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="fb832-132">Pour plus d’informations, voir [déployer un site unique dans le connecteur du nuage](deploy-a-single-site-in-cloud-connector.md) et [déployer plusieurs sites dans le connecteur de nuage](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fb832-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="fb832-133">Si vous avez un déploiement existant de connecteur du nuage et que vous souhaitez mettre à niveau, suivez les instructions de [mise à niveau vers une nouvelle version de connecteur de nuage](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fb832-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fb832-134">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fb832-134">Parameters</span></span>
<span data-ttu-id="fb832-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fb832-135"></span></span>

|<span data-ttu-id="fb832-136">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="fb832-136">**Parameter**</span></span>|<span data-ttu-id="fb832-137">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="fb832-137">**Required**</span></span>|<span data-ttu-id="fb832-138">**Type de**</span><span class="sxs-lookup"><span data-stu-id="fb832-138">**Type**</span></span>|<span data-ttu-id="fb832-139">**Description**</span><span class="sxs-lookup"><span data-stu-id="fb832-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb832-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="fb832-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="fb832-141">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fb832-141">Optional</span></span>  <br/> |<span data-ttu-id="fb832-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fb832-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="fb832-p105">Création de fichiers de configuration pour chaque étape de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes. </span><span class="sxs-lookup"><span data-stu-id="fb832-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="fb832-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="fb832-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="fb832-146">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fb832-146">Optional</span></span>  <br/> |<span data-ttu-id="fb832-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fb832-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fb832-p106">Affichage des noms des étapes de déploiement uniquement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="fb832-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="fb832-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="fb832-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="fb832-151">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fb832-151">Optional</span></span>  <br/> |<span data-ttu-id="fb832-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fb832-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fb832-p107">Ce paramètre doit être utilisé conjointement avec le paramètre Étapes. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="fb832-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="fb832-155">Étapes</span><span class="sxs-lookup"><span data-stu-id="fb832-155">Steps</span></span>  <br/> |<span data-ttu-id="fb832-156">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fb832-156">Optional</span></span>  <br/> |<span data-ttu-id="fb832-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="fb832-157">System.Array</span></span>  <br/> |<span data-ttu-id="fb832-p108">Exécution des étapes de déploiement. Ce paramètre est uniquement fourni à des fins de résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="fb832-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="fb832-160">Mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fb832-160">Upgrade</span></span>  <br/> |<span data-ttu-id="fb832-161">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fb832-161">Optional</span></span>  <br/> |<span data-ttu-id="fb832-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fb832-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fb832-163">Mise à niveau du Cloud Connector existant vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="fb832-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="fb832-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="fb832-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="fb832-165">Facultatif</span><span class="sxs-lookup"><span data-stu-id="fb832-165">Optional</span></span>  <br/> |<span data-ttu-id="fb832-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fb832-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fb832-167">Supprimer toutes les informations d’identification de connecteur du Cloud dans le cache.</span><span class="sxs-lookup"><span data-stu-id="fb832-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="fb832-168">Demandez à l’utilisateur de spécifier de nouvelles informations pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="fb832-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fb832-169">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="fb832-169">Input Types</span></span>
<span data-ttu-id="fb832-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb832-170"></span></span>

<span data-ttu-id="fb832-p110">Aucun. L’applet de commande Install-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="fb832-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fb832-173">Types de retours</span><span class="sxs-lookup"><span data-stu-id="fb832-173">Return Types</span></span>
<span data-ttu-id="fb832-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb832-174"></span></span>

<span data-ttu-id="fb832-175">Aucun</span><span class="sxs-lookup"><span data-stu-id="fb832-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb832-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb832-176">See also</span></span>
<span data-ttu-id="fb832-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb832-177"></span></span>

[<span data-ttu-id="fb832-178">Publication-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fb832-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="fb832-179">Registre-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fb832-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="fb832-180">Annuler l’inscription-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fb832-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="fb832-181">CcAppliance-désinstaller</span><span class="sxs-lookup"><span data-stu-id="fb832-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

