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
description: Découvrez comment mettre à niveau votre déploiement de Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359290"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="5364d-103">Effectuer une mise à niveau vers une nouvelle version de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5364d-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="5364d-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="5364d-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="5364d-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="5364d-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="5364d-106">Découvrez comment mettre à niveau votre déploiement de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5364d-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="5364d-107">Si vous avez configuré un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype entreprise, version Cloud Connector, sera automatiquement mis à niveau vers la version la plus récente, en fonction de la configuration de la fenêtre de mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="5364d-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="5364d-108">Vous pouvez également effectuer une mise à niveau manuelle.</span><span class="sxs-lookup"><span data-stu-id="5364d-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="5364d-109">La version de Cloud Connector version 1.4.1 et les versions ultérieures effectuent des mises à jour automatiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="5364d-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="5364d-110">Si vous souhaitez effectuer une mise à niveau vers la dernière version (2,1) manuellement, consultez la rubrique [mise à niveau d’un site unique vers une nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5364d-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="5364d-111">La mise à jour automatique nécessite que le service Cloud Connector soit en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="5364d-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="5364d-112">Les étapes suivantes décrivent le processus de mise à jour automatique :</span><span class="sxs-lookup"><span data-stu-id="5364d-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="5364d-113">Le processus de mise à jour automatique s’exécute en fonction de la planification que vous avez configurée pour les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="5364d-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="5364d-114">Tâches de mise à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="5364d-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="5364d-115">Vérifiez et téléchargez les mises à jour du système d’exploitation sur tous les ordinateurs virtuels Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5364d-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="5364d-116">Installez et mettez à jour tous les ordinateurs virtuels Cloud Connector un par un et redémarrez.</span><span class="sxs-lookup"><span data-stu-id="5364d-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="5364d-117">Après le redémarrage des machines virtuelles de Cloud Connector, vérifiez si un autre redémarrage est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5364d-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="5364d-118">Une fois que les machines virtuelles Cloud Connector ont été mises à jour avec succès, répétez le processus pour l’ordinateur hôte Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5364d-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="5364d-119">Une fois que la machine hôte Cloud Connector s’est exécutée correctement, toutes les tâches de mise à jour du système d’exploitation en suspens sont effectuées.</span><span class="sxs-lookup"><span data-stu-id="5364d-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="5364d-120">Tâches de mise à jour de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5364d-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="5364d-121">Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="5364d-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="5364d-122">Téléchargez le fichier. msi de la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="5364d-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="5364d-123">Désinstallez l’ancien fichier MSI ; Installez le nouveau fichier msi.</span><span class="sxs-lookup"><span data-stu-id="5364d-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="5364d-124">Téléchargez la nouvelle version de Skype entreprise bits.</span><span class="sxs-lookup"><span data-stu-id="5364d-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="5364d-125">Inscrivez l’appliance en appelant Register-applet ccappliance.</span><span class="sxs-lookup"><span data-stu-id="5364d-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="5364d-126">Installez la nouvelle version de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5364d-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="5364d-127">Déchargez l’ancien matériel et basculez la connexion réseau vers le nouveau matériel.</span><span class="sxs-lookup"><span data-stu-id="5364d-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="5364d-128">Lorsque Cloud Connector est mis à jour vers une nouvelle version, les cmdlets de Cloud Connector ne sont peut-être pas mises à jour.</span><span class="sxs-lookup"><span data-stu-id="5364d-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="5364d-129">Cela peut se produire, par exemple, si une fenêtre PowerShell est laissée ouverte pendant que la mise à jour automatique se produit.</span><span class="sxs-lookup"><span data-stu-id="5364d-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="5364d-130">Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes : > fermer PowerShell sur l’appliance Cloud Connector, puis rouvrir PowerShell. > ou exécuter import-module CloudConnector-force.</span><span class="sxs-lookup"><span data-stu-id="5364d-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="5364d-131">Mettre à niveau un site unique vers une nouvelle version</span><span class="sxs-lookup"><span data-stu-id="5364d-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="5364d-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="5364d-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="5364d-133">S’il n’y a qu’une seule Appliance dans le site que vous souhaitez mettre à niveau, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5364d-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="5364d-134">Désinstallez la version de Cloud Connector existante dans programmes **du panneau de configuration programmes \> \> et fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="5364d-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="5364d-135">Installez la nouvelle version de CloudConnector.msi à partir de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="5364d-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="5364d-136">Vérifiez que vous disposez du fichier de CloudConnector.ini pour la version que vous installez et que vous avez mis à jour toutes les valeurs requises pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="5364d-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="5364d-137">Vous ne pouvez pas utiliser le fichier. ini d’une version précédente.</span><span class="sxs-lookup"><span data-stu-id="5364d-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="5364d-138">Si vous mettez à niveau Cloud Connector, reportez-vous à la rubrique [Prepare Your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md) et assurez-vous que SiteName and EnableReferSupport sont définis sur la valeur correcte dans le fichier CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="5364d-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="5364d-139">Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="5364d-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="5364d-140">Exécutez l’applet de commande suivante pour télécharger la dernière version :</span><span class="sxs-lookup"><span data-stu-id="5364d-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="5364d-141">Exécutez l’applet de commande suivante pour démarrer l’installation :</span><span class="sxs-lookup"><span data-stu-id="5364d-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="5364d-142">Exécutez l’applet de commande suivante pour activer le nouveau déploiement et désactiver la version précédente :</span><span class="sxs-lookup"><span data-stu-id="5364d-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="5364d-143">S’il y a plusieurs Appliances dans le site, suivez les étapes précédentes pour mettre à niveau chaque appliance une par une.</span><span class="sxs-lookup"><span data-stu-id="5364d-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="5364d-144">Si vous souhaitez mettre à jour les informations d’identification de l’administrateur de domaine, de l’administrateur de la machine virtuelle, du mode sans échec et de l’administrateur client, vous pouvez exécuter l’applet de commande avec le paramètre  _UpdateAllCredentials_ pour réinitialiser toutes les informations d’identification :</span><span class="sxs-lookup"><span data-stu-id="5364d-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="5364d-145">Ensuite, lorsque vous commencez à effectuer une mise à niveau vers une nouvelle version, vous serez invité à entrer les nouvelles informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="5364d-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="5364d-146">Si vous souhaitez uniquement réinitialiser les informations d’identification d’administrateur de client, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5364d-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="5364d-147">Mettre à niveau plusieurs sites vers une nouvelle version</span><span class="sxs-lookup"><span data-stu-id="5364d-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="5364d-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="5364d-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="5364d-149">Suivez les étapes de mise à niveau d’un site unique, mettant à niveau un site à la fois pour chaque site de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="5364d-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="5364d-150">Assurez-vous et [validez votre déploiement de Cloud Connector après la](validate-your-cloud-connector-deployment.md) mise à niveau de chaque site.</span><span class="sxs-lookup"><span data-stu-id="5364d-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

