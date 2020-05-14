---
title: Déployer un seul site dans Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Découvrez comment déployer un seul site RTC dans la version Cloud Connector.
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220534"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="ebc41-103">Déployer un seul site dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ebc41-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="ebc41-104">Découvrez comment déployer un seul site RTC dans la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ebc41-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="ebc41-105">Vous pouvez déployer Skype entreprise, version Cloud Connector avec ou sans prise en charge de la haute disponibilité (HA).</span><span class="sxs-lookup"><span data-stu-id="ebc41-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="ebc41-106">Si vous souhaitez activer la haute disponibilité, vous devez déployer au moins deux Appliances au sein d’un site.</span><span class="sxs-lookup"><span data-stu-id="ebc41-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="ebc41-107">Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité après son déploiement.</span><span class="sxs-lookup"><span data-stu-id="ebc41-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="ebc41-108">Déployer la première Appliance Skype entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ebc41-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="ebc41-109">Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance :</span><span class="sxs-lookup"><span data-stu-id="ebc41-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="ebc41-110">Suivez les instructions pour indiquer le nom du compte et le mot de passe de l’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="ebc41-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="ebc41-111">Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ebc41-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="ebc41-112">Suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe administrateur en mode sans échec, le mot de passe administrateur de domaine et le mot de passe d’administrateur de l’ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="ebc41-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="ebc41-113">Dans la version 1.4.2 et les versions antérieures, suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur VM.</span><span class="sxs-lookup"><span data-stu-id="ebc41-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="ebc41-114">Dans la version 2,0 et les versions ultérieures, suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="ebc41-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="ebc41-115">Pour démarrer l’installation, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ebc41-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="ebc41-116">Ajouter une appliance à un site existant</span><span class="sxs-lookup"><span data-stu-id="ebc41-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="ebc41-117">Vous pouvez étendre un site Cloud Connector existant pour prendre en charge la haute disponibilité en ajoutant des appliances supplémentaires au site.</span><span class="sxs-lookup"><span data-stu-id="ebc41-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="ebc41-118">Suivez les étapes de préparation de votre appliance Cloud Connector comme décrit dans [prepare the Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="ebc41-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="ebc41-119">Certaines étapes sont requises uniquement pour la première appliance de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ebc41-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="ebc41-120">Vérifiez que l’annuaire de sites existe et qu’il est correctement configuré pour la prise en charge de la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ebc41-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="ebc41-121">Exécutez l’applet de commande suivante uniquement sur le serveur hôte nouvellement ajouté afin de mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebc41-121">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="ebc41-122">Si vous souhaitez ajouter plusieurs Appliances en même temps, exécutez l’applet de commande sur chaque serveur hôte nouvellement ajouté un par un :</span><span class="sxs-lookup"><span data-stu-id="ebc41-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="ebc41-123">Mettez à jour la topologie sur les appliances existantes en exécutant l’applet de commande suivante sur chaque serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="ebc41-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="ebc41-124">N’exécutez l’applet de commande que sur les appliances existantes.</span><span class="sxs-lookup"><span data-stu-id="ebc41-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="ebc41-125">Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes nouvellement ajoutés.</span><span class="sxs-lookup"><span data-stu-id="ebc41-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="ebc41-126">N’exécutez pas cette applet de commande sur l’appliance existante.</span><span class="sxs-lookup"><span data-stu-id="ebc41-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="ebc41-127">Si vous souhaitez ajouter plusieurs Appliances en même temps, exécutez l’applet de commande sur chaque serveur hôte nouvellement ajouté un par un.</span><span class="sxs-lookup"><span data-stu-id="ebc41-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="ebc41-128">Si l’annuaire de sites a été défini sur un chemin d’accès au dossier local, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin d’accès UNC pour l’annuaire de sites sur le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="ebc41-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="ebc41-129">Vous pouvez laisser le premier annuaire de sites de matériel avec le chemin d’accès local ou le modifier pour utiliser le chemin d’accès UNC du partage vers le même dossier.</span><span class="sxs-lookup"><span data-stu-id="ebc41-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="ebc41-130">Si l’emplacement de l’annuaire de sites partagé change, les appliances précédemment installées doivent être désinstallées, puis réinstallées.</span><span class="sxs-lookup"><span data-stu-id="ebc41-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="ebc41-131">> important : le mot de passe pour le compte CceService et le compte CABackupFile doit être le même sur toutes les appliances déployées au sein du site, afin que les appliances puissent accéder au partage de l’annuaire de sites et au fichier de sauvegarde de l’autorité de certification chiffré dans l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="ebc41-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="ebc41-132">Supprimer une appliance d’un site existant</span><span class="sxs-lookup"><span data-stu-id="ebc41-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="ebc41-133">Si vous souhaitez supprimer une appliance d’un site existant :</span><span class="sxs-lookup"><span data-stu-id="ebc41-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="ebc41-134">Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes que vous souhaitez supprimer du site afin de mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebc41-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="ebc41-135">Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes dont vous souhaitez supprimer tous les ordinateurs virtuels de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="ebc41-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


