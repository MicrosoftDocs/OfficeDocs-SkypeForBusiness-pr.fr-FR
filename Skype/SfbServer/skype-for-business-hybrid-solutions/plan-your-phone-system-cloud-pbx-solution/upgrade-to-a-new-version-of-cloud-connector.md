---
title: Effectuer une mise à niveau vers une nouvelle version de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Découvrez comment mettre à niveau votre déploiement en nuage connecteur Edition.
ms.openlocfilehash: 5b3ca4b216bc376c9e23424fb978b5cd83e4aa41
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897649"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="4218d-103">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4218d-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="4218d-104">Découvrez comment mettre à niveau votre déploiement en nuage connecteur Edition.</span><span class="sxs-lookup"><span data-stu-id="4218d-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="4218d-p101">Si vous avez configuré un compte client de gestion en ligne et activé les mises à jour automatiques, votre déploiement existant de Skype Entreprise, version Cloud Connector sera mis à niveau vers la dernière version automatiquement, en fonction de votre configuration de fenêtre de délai de mise à jour automatique. Vous pouvez également effectuer manuellement la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="4218d-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="4218d-107">Versions de connecteur Edition 1.4.1 en nuage et ultérieurement effectuer des mises à jour automatiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="4218d-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="4218d-108">Si vous souhaitez mettre à niveau vers la dernière version (2.1) manuellement, voir [mettre à niveau un seul site vers une nouvelle version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4218d-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="4218d-109">Mise à jour automatique requiert que le service nuage connecteur est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="4218d-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="4218d-110">Les étapes suivantes décrivent le processus de mise à jour automatiques :</span><span class="sxs-lookup"><span data-stu-id="4218d-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="4218d-111">Le processus de mise à jour automatique fonctionnera en fonction de la planification que vous avez configurée pour les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="4218d-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="4218d-112">Tâches de mise à jour du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="4218d-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="4218d-113">Vérifier et télécharger des mises à jour du système d’exploitation sur tous les ordinateurs virtuels de connecteur dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="4218d-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="4218d-114">Installer et mettre à jour tous les ordinateurs dans le nuage connecteur virtuels un par un redémarrage.</span><span class="sxs-lookup"><span data-stu-id="4218d-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="4218d-115">Après le redémarrage d’ordinateurs virtuels dans le nuage connecteur, vérifie si un autre redémarrage est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4218d-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="4218d-116">Après avoir des ordinateurs virtuels dans le nuage connecteur ont été correctement corrigés, répétez le processus pour l’ordinateur hôte de nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="4218d-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="4218d-117">Une fois que l’ordinateur hôte de nuage connecteur correctement démarre, des tâches de mise à jour de système d’exploitation en attente sont terminées.</span><span class="sxs-lookup"><span data-stu-id="4218d-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="4218d-118">Tâches de mise à jour de connecteur en nuage</span><span class="sxs-lookup"><span data-stu-id="4218d-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="4218d-119">Téléchargez et vérifiez le fichier de version à partir du site de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="4218d-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="4218d-120">Téléchargez le fichier .msi de la nouvelle version. </span><span class="sxs-lookup"><span data-stu-id="4218d-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="4218d-121">Désinstaller l’ancien fichier msi ; Installez le nouveau fichier msi.</span><span class="sxs-lookup"><span data-stu-id="4218d-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="4218d-122">Téléchargez la nouvelle version de Skype pour bits de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4218d-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="4218d-123">Enregistrez l’appliance en appelant Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="4218d-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="4218d-124">Installer la nouvelle version de connecteur dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="4218d-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="4218d-125">Nettoyez l’ancienne appliance puis basculez la connexion réseau vers la nouvelle appliance.</span><span class="sxs-lookup"><span data-stu-id="4218d-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="4218d-126">Lorsque nuage connecteur mises à jour vers une nouvelle version, cmdlets de connecteur de nuage ne peut pas mis à jour.</span><span class="sxs-lookup"><span data-stu-id="4218d-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="4218d-127">Cela peut se produire, par exemple, si une fenêtre PowerShell reste ouverte pendant la mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="4218d-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="4218d-128">Pour charger les applets de commande mis à jour, vous pouvez effectuer une de la fermer PowerShell de > : étapes suivantes sur le matériel de nuage connecteur et puis rouvrez ou PowerShell.>, vous pouvez exécuter Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="4218d-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="4218d-129">Mise à niveau d’un site unique vers une nouvelle version</span><span class="sxs-lookup"><span data-stu-id="4218d-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="4218d-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="4218d-130"></span></span>

<span data-ttu-id="4218d-131">Si le site comporte un seul équipement que vous souhaitez mettre à niveau, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4218d-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="4218d-132">Désinstaller la version existante de nuage connecteur dans **le panneau de configuration \> programmes \> programmes et fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="4218d-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="4218d-133">Installer la nouvelle version de CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="4218d-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="4218d-134">Vérifiez que vous disposez du fichier CloudConnector.ini pour la version que vous installez et que les valeurs requises pour votre environnement sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4218d-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="4218d-135">Vous ne pouvez pas utiliser le fichier .ini d’une version précédente.</span><span class="sxs-lookup"><span data-stu-id="4218d-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="4218d-136">Si vous mettez à niveau dans le nuage connecteur, reportez-vous à la rubrique [préparer votre solution de nuage connecteur](prepare-your-cloud-connector-appliance.md) et vérifiez SiteName et EnableReferSupport sont définies dans le fichier CloudConnector.ini à la valeur correcte.</span><span class="sxs-lookup"><span data-stu-id="4218d-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="4218d-137">Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="4218d-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="4218d-138">Exécutez l’applet de commande suivante pour télécharger la dernière version :</span><span class="sxs-lookup"><span data-stu-id="4218d-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="4218d-139">Exécutez l’applet de commande suivante pour démarrer l’installation : </span><span class="sxs-lookup"><span data-stu-id="4218d-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="4218d-140">Exécutez l’applet de commande suivante pour activer le nouveau déploiement et désactiver la version précédente :</span><span class="sxs-lookup"><span data-stu-id="4218d-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="4218d-141">Si le site comporte plusieurs équipements, suivez la procédure précédente pour les mettre à niveau l’un après l’autre.</span><span class="sxs-lookup"><span data-stu-id="4218d-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="4218d-142">Si vous souhaitez mettre à jour d’administrateur de domaine, administrateur de l’ordinateur virtuel, administrateur en Mode sans échec et les informations d’identification administrateur client, vous pouvez exécuter l’applet de commande avec le paramètre _UpdateAllCredentials_ pour réinitialiser tous les informations d’identification :</span><span class="sxs-lookup"><span data-stu-id="4218d-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="4218d-143">Puis, lors de la mise à niveau vers la nouvelle version, vous serez invité à saisir les nouvelles informations d’identification. </span><span class="sxs-lookup"><span data-stu-id="4218d-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="4218d-144">Si vous souhaitez réinitialiser uniquement les informations d’identification d’administrateur de clients, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4218d-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="4218d-145">Mise à niveau de sites multiples vers une nouvelle version</span><span class="sxs-lookup"><span data-stu-id="4218d-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="4218d-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="4218d-146"></span></span>

<span data-ttu-id="4218d-p106">Appliquez la procédure de mise à niveau d’un site unique, un site à la fois dans votre déploiement. Vérifiez et [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) après chaque mise à niveau de site.</span><span class="sxs-lookup"><span data-stu-id="4218d-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

