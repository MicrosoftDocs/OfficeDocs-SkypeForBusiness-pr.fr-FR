---
title: Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Découvrez comment mettre à niveau votre déploiement de la version Cloud Connector.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359290"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="952d9-103">Effectuer une mise à niveau vers une nouvelle version de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="952d9-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="952d9-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="952d9-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="952d9-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="952d9-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="952d9-106">Découvrez comment mettre à niveau votre déploiement de la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="952d9-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="952d9-107">Si vous avez installé un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype Entreprise, version Cloud Connector sera automatiquement mis à niveau vers la version la plus récente, en fonction de la configuration de votre fenêtre de temps de mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="952d9-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="952d9-108">Vous pouvez également effectuer une mise à niveau manuelle.</span><span class="sxs-lookup"><span data-stu-id="952d9-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="952d9-109">Les versions 1.4.1 et ultérieures de Cloud Connector effectuent des mises à jour automatiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="952d9-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="952d9-110">Si vous souhaitez mettre à niveau vers la dernière version (2.1) manuellement, voir Mettre à niveau un site unique vers une [nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="952d9-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="952d9-111">La mise à jour automatique nécessite que le service Cloud Connector soit en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="952d9-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="952d9-112">Les étapes suivantes décrivent le processus de mise à jour automatique :</span><span class="sxs-lookup"><span data-stu-id="952d9-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="952d9-113">Le processus de mise à jour automatique s’exécute en fonction de la planification que vous avez configurée pour les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="952d9-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="952d9-114">Tâches de mise à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="952d9-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="952d9-115">Vérifiez et téléchargez les mises à jour du système d’exploitation sur toutes les VM Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="952d9-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="952d9-116">Installez et mettez à jour toutes les VM Cloud Connector une par une, puis redémarrez.</span><span class="sxs-lookup"><span data-stu-id="952d9-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="952d9-117">Après le redémarrage des VM Cloud Connector, vérifiez si un autre redémarrage est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="952d9-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="952d9-118">Une fois que les machines VM Cloud Connector ont été correctement corrigés, répétez le processus pour l’ordinateur hôte Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="952d9-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="952d9-119">Une fois l’ordinateur hôte Cloud Connector correctement lancé, toutes les tâches de mise à jour du système d’exploitation en suspens sont terminées.</span><span class="sxs-lookup"><span data-stu-id="952d9-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="952d9-120">Tâches de mise à jour cloud Connector</span><span class="sxs-lookup"><span data-stu-id="952d9-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="952d9-121">Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="952d9-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="952d9-122">Téléchargez le fichier .msi de la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="952d9-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="952d9-123">Désinstallez l’ancien fichier msi ; installez le nouveau fichier msi.</span><span class="sxs-lookup"><span data-stu-id="952d9-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="952d9-124">Téléchargez la nouvelle version de Skype Entreprise Bits.</span><span class="sxs-lookup"><span data-stu-id="952d9-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="952d9-125">Enregistrez l’appliance en appelant Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="952d9-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="952d9-126">Installez la nouvelle version de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="952d9-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="952d9-127">Drainez l’ancienne appliance et basculez la connexion réseau vers la nouvelle appliance.</span><span class="sxs-lookup"><span data-stu-id="952d9-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="952d9-128">Lorsque Cloud Connector est mis à jour vers une nouvelle build, il se peut que les cmdlets Cloud Connector ne soient pas mises à jour.</span><span class="sxs-lookup"><span data-stu-id="952d9-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="952d9-129">Cela peut se produire, par exemple, si une fenêtre PowerShell reste ouverte pendant la mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="952d9-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="952d9-130">Pour charger les cmdlets mises à jour, vous pouvez exécuter l’une des étapes suivantes : > Fermez PowerShell sur l’appliance Cloud Connector, puis rouvrez PowerShell.> Ou, vous pouvez exécuter Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="952d9-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="952d9-131">Mettre à niveau un site unique vers une nouvelle version</span><span class="sxs-lookup"><span data-stu-id="952d9-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="952d9-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="952d9-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="952d9-133">S’il n’existe qu’une seule appliance dans le site que vous souhaitez mettre à niveau, faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="952d9-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="952d9-134">Désinstallez la version Cloud Connector existante dans programmes et fonctionnalités du Panneau **\> de \> contrôle.**</span><span class="sxs-lookup"><span data-stu-id="952d9-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="952d9-135">Installez la nouvelle version de CloudConnector.msi à partir [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) de .</span><span class="sxs-lookup"><span data-stu-id="952d9-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="952d9-136">Confirmez que vous avez le fichier CloudConnector.ini pour la version que vous installez et que vous avez mis à jour toutes les valeurs requises pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="952d9-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="952d9-137">Vous ne pouvez pas utiliser le fichier .ini d’une version précédente.</span><span class="sxs-lookup"><span data-stu-id="952d9-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="952d9-138">Si vous êtes en cours de mise à niveau de Cloud Connector, reportez-vous à la rubrique Préparer votre appliance [Cloud Connector](prepare-your-cloud-connector-appliance.md) et assurez-vous que SiteName et EnableReferSupport sont définies sur la valeur correcte dans le fichier CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="952d9-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="952d9-139">Démarrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour inscrire l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="952d9-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="952d9-140">Exécutez l’cmdlet suivante pour télécharger la dernière version :</span><span class="sxs-lookup"><span data-stu-id="952d9-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="952d9-141">Exécutez l’cmdlet suivante pour démarrer l’installation :</span><span class="sxs-lookup"><span data-stu-id="952d9-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="952d9-142">Exécutez l’cmdlet suivante pour activer le nouveau déploiement et désactiver la version précédente :</span><span class="sxs-lookup"><span data-stu-id="952d9-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="952d9-143">S’il existe plusieurs appliances dans le site, suivez les étapes précédentes pour mettre à niveau chaque appliance une par une.</span><span class="sxs-lookup"><span data-stu-id="952d9-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="952d9-144">Si vous souhaitez mettre à jour les informations d’identification d’administrateur de domaine, d’administrateur de machine virtuelle, d’administrateur en mode sans échec et d’administrateur client, vous pouvez exécuter l’cmdlet avec le paramètre  _UpdateAllCredentials_ pour réinitialiser toutes les informations d’identification :</span><span class="sxs-lookup"><span data-stu-id="952d9-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="952d9-145">Ensuite, lorsque vous commencez à mettre à niveau vers une nouvelle version, vous êtes promu pour entrer les nouvelles informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="952d9-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="952d9-146">Si vous souhaitez uniquement réinitialiser vos informations d’identification d’administrateur client, exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="952d9-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="952d9-147">Mettre à niveau plusieurs sites vers une nouvelle version</span><span class="sxs-lookup"><span data-stu-id="952d9-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="952d9-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="952d9-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="952d9-149">Suivez les étapes de mise à niveau d’un site unique, mise à niveau d’un site à la fois pour chaque site de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="952d9-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="952d9-150">Assurez-vous et [validez votre déploiement Cloud Connector après](validate-your-cloud-connector-deployment.md) la mise à niveau de chaque site.</span><span class="sxs-lookup"><span data-stu-id="952d9-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

