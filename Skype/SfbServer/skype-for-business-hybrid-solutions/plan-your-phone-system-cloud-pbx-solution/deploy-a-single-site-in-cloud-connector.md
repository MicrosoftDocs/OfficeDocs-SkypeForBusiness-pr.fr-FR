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
description: En savoir plus sur le déploiement d’un seul site PSTN dans Cloud Connector Edition.
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094832"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="df16d-103">Déployer un seul site dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="df16d-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="df16d-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="df16d-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="df16d-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="df16d-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="df16d-106">En savoir plus sur le déploiement d’un seul site PSTN dans Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="df16d-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="df16d-107">Vous pouvez déployer Skype Entreprise, version Cloud Connector avec ou sans la prise en charge de la haute disponibilité (HA).</span><span class="sxs-lookup"><span data-stu-id="df16d-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="df16d-108">Si vous souhaitez activer la ha, vous devez déployer au moins deux appliances au sein d’un site.</span><span class="sxs-lookup"><span data-stu-id="df16d-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="df16d-109">Vous pouvez également convertir une appliance existante pour prendre en charge la ha après son déploiement.</span><span class="sxs-lookup"><span data-stu-id="df16d-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="df16d-110">Déployer la première appliance de la version Cloud Connector de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="df16d-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="df16d-111">Pour déployer la première appliance dans un site, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour inscrire l’appliance :</span><span class="sxs-lookup"><span data-stu-id="df16d-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="df16d-112">Suivez les instructions pour fournir le nom et le mot de passe du compte d’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="df16d-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="df16d-113">Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="df16d-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="df16d-114">Suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe de l’administrateur de la VM.</span><span class="sxs-lookup"><span data-stu-id="df16d-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="df16d-115">Dans la version 1.4.2 et antérieure, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur de la VM.</span><span class="sxs-lookup"><span data-stu-id="df16d-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="df16d-116">Dans la version 2.0 et ultérieure, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="df16d-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="df16d-117">Pour démarrer l’installation, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="df16d-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="df16d-118">Ajouter une appliance à un site existant</span><span class="sxs-lookup"><span data-stu-id="df16d-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="df16d-119">Vous pouvez étendre un site Cloud Connector existant pour prendre en charge la haute qualité de l’expérience en ajoutant des appliances supplémentaires au site.</span><span class="sxs-lookup"><span data-stu-id="df16d-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="df16d-120">Suivez les étapes pour préparer votre appliance Cloud Connector comme décrit dans [Préparer votre appliance Cloud Connector.](prepare-your-cloud-connector-appliance.md)</span><span class="sxs-lookup"><span data-stu-id="df16d-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="df16d-121">Notez que certaines étapes sont requises uniquement pour la première appliance de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="df16d-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="df16d-122">Confirmez que l’annuaire de sites existe et qu’il est correctement configuré pour la prise en charge de la ha.</span><span class="sxs-lookup"><span data-stu-id="df16d-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="df16d-123">Exécutez l’cmdlet suivante uniquement sur le serveur hôte nouvellement ajouté pour mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="df16d-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="df16d-124">Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l’cmdlet sur chaque serveur hôte nouvellement ajouté un par un :</span><span class="sxs-lookup"><span data-stu-id="df16d-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="df16d-125">Mettez à jour la topologie sur les appliances existantes en exécutant l’cmdlet suivante sur chaque serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="df16d-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="df16d-126">Exécutez uniquement l’cmdlet sur les appliances existantes.</span><span class="sxs-lookup"><span data-stu-id="df16d-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="df16d-127">Exécutez l’applet de cmdlet suivante uniquement sur les serveurs hôtes nouvellement ajoutés.</span><span class="sxs-lookup"><span data-stu-id="df16d-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="df16d-128">N’exécutez pas cette cmdlet sur l’appliance existante.</span><span class="sxs-lookup"><span data-stu-id="df16d-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="df16d-129">Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l’cmdlet sur chaque serveur hôte nouvellement ajouté un par un.</span><span class="sxs-lookup"><span data-stu-id="df16d-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="df16d-130">Si l’annuaire de sites a été défini sur un chemin d’accès de dossier local, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin UNC pour l’annuaire de sites sur la nouvelle appliance.</span><span class="sxs-lookup"><span data-stu-id="df16d-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="df16d-131">Vous pouvez laisser le premier répertoire de site appliance avec le chemin d’accès local ou le modifier pour utiliser le chemin d’accès UNC pour le partage vers le même dossier.</span><span class="sxs-lookup"><span data-stu-id="df16d-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="df16d-132">Si l’emplacement de l’annuaire de sites partagés change, toutes les appliances précédemment installées doivent être désinstallées, puis réinstallées.</span><span class="sxs-lookup"><span data-stu-id="df16d-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="df16d-133">> Important : le mot de passe du compte CceService et du compte CABackupFile doit être le même sur toutes les appliances déployées dans le site, afin que les appliances peuvent accéder au partage d’annuaire de sites et au fichier de sauvegarde de l’autorité de contrôle d’accès chiffré dans l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="df16d-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="df16d-134">Supprimer une appliance d’un site existant</span><span class="sxs-lookup"><span data-stu-id="df16d-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="df16d-135">Si vous souhaitez supprimer une appliance d’un site existant :</span><span class="sxs-lookup"><span data-stu-id="df16d-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="df16d-136">Exécutez la cmdlet suivante uniquement sur les serveurs hôtes que vous souhaitez supprimer du site pour mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="df16d-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="df16d-137">Exécutez la cmdlet suivante uniquement sur les serveurs hôtes dont vous souhaitez supprimer tous les ordinateurs virtuels de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="df16d-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```