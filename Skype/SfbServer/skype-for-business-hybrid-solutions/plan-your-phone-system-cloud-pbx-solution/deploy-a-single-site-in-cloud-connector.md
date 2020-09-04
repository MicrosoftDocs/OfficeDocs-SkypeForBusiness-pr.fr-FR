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
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358930"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="1487f-103">Déployer un seul site dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1487f-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="1487f-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="1487f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="1487f-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="1487f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="1487f-106">Découvrez comment déployer un seul site RTC dans la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1487f-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="1487f-107">Vous pouvez déployer Skype entreprise, version Cloud Connector avec ou sans prise en charge de la haute disponibilité (HA).</span><span class="sxs-lookup"><span data-stu-id="1487f-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="1487f-108">Si vous souhaitez activer la haute disponibilité, vous devez déployer au moins deux Appliances au sein d’un site.</span><span class="sxs-lookup"><span data-stu-id="1487f-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="1487f-109">Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité après son déploiement.</span><span class="sxs-lookup"><span data-stu-id="1487f-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="1487f-110">Déployer la première Appliance Skype entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1487f-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="1487f-111">Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour enregistrer l’appliance :</span><span class="sxs-lookup"><span data-stu-id="1487f-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="1487f-112">Suivez les instructions pour indiquer le nom du compte et le mot de passe de l’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="1487f-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="1487f-113">Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1487f-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="1487f-114">Suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe administrateur en mode sans échec, le mot de passe administrateur de domaine et le mot de passe d’administrateur de l’ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="1487f-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="1487f-115">Dans la version 1.4.2 et les versions antérieures, suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur VM.</span><span class="sxs-lookup"><span data-stu-id="1487f-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="1487f-116">Dans la version 2,0 et les versions ultérieures, suivez également les instructions pour indiquer le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="1487f-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="1487f-117">Pour démarrer l’installation, ouvrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1487f-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="1487f-118">Ajouter une appliance à un site existant</span><span class="sxs-lookup"><span data-stu-id="1487f-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="1487f-119">Vous pouvez étendre un site Cloud Connector existant pour prendre en charge la haute disponibilité en ajoutant des appliances supplémentaires au site.</span><span class="sxs-lookup"><span data-stu-id="1487f-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="1487f-120">Suivez les étapes de préparation de votre appliance Cloud Connector comme décrit dans [prepare the Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="1487f-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="1487f-121">Certaines étapes sont requises uniquement pour la première appliance de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1487f-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="1487f-122">Vérifiez que l’annuaire de sites existe et qu’il est correctement configuré pour la prise en charge de la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1487f-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="1487f-123">Exécutez l’applet de commande suivante uniquement sur le serveur hôte nouvellement ajouté afin de mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="1487f-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="1487f-124">Si vous souhaitez ajouter plusieurs Appliances en même temps, exécutez l’applet de commande sur chaque serveur hôte nouvellement ajouté un par un :</span><span class="sxs-lookup"><span data-stu-id="1487f-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="1487f-125">Mettez à jour la topologie sur les appliances existantes en exécutant l’applet de commande suivante sur chaque serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="1487f-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="1487f-126">N’exécutez l’applet de commande que sur les appliances existantes.</span><span class="sxs-lookup"><span data-stu-id="1487f-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="1487f-127">Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes nouvellement ajoutés.</span><span class="sxs-lookup"><span data-stu-id="1487f-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="1487f-128">N’exécutez pas cette applet de commande sur l’appliance existante.</span><span class="sxs-lookup"><span data-stu-id="1487f-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="1487f-129">Si vous souhaitez ajouter plusieurs Appliances en même temps, exécutez l’applet de commande sur chaque serveur hôte nouvellement ajouté un par un.</span><span class="sxs-lookup"><span data-stu-id="1487f-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="1487f-130">Si l’annuaire de sites a été défini sur un chemin d’accès au dossier local, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin d’accès UNC pour l’annuaire de sites sur le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="1487f-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="1487f-131">Vous pouvez laisser le premier annuaire de sites de matériel avec le chemin d’accès local ou le modifier pour utiliser le chemin d’accès UNC du partage vers le même dossier.</span><span class="sxs-lookup"><span data-stu-id="1487f-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="1487f-132">Si l’emplacement de l’annuaire de sites partagé change, les appliances précédemment installées doivent être désinstallées, puis réinstallées.</span><span class="sxs-lookup"><span data-stu-id="1487f-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="1487f-133">> important : le mot de passe pour le compte CceService et le compte CABackupFile doit être le même sur toutes les appliances déployées au sein du site, afin que les appliances puissent accéder au partage de l’annuaire de sites et au fichier de sauvegarde de l’autorité de certification chiffré dans l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="1487f-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="1487f-134">Supprimer une appliance d’un site existant</span><span class="sxs-lookup"><span data-stu-id="1487f-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="1487f-135">Si vous souhaitez supprimer une appliance d’un site existant :</span><span class="sxs-lookup"><span data-stu-id="1487f-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="1487f-136">Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes que vous souhaitez supprimer du site afin de mettre à jour les informations de topologie dans la configuration de votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="1487f-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="1487f-137">Exécutez l’applet de commande suivante uniquement sur les serveurs hôtes dont vous souhaitez supprimer tous les ordinateurs virtuels de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="1487f-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


