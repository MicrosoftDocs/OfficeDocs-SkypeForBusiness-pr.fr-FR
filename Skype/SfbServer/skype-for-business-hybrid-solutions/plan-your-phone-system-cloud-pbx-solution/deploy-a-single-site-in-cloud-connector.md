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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: En savoir plus sur le déploiement d’un seul site RTC dans la version Cloud Connector.
ms.openlocfilehash: 10d9e5f286b00af8791097707dc0345e100e55d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287362"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="9a678-103">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="9a678-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="9a678-104">En savoir plus sur le déploiement d’un seul site RTC dans la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9a678-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="9a678-105">Vous pouvez déployer Skype entreprise version Cloud Connector avec ou sans prise en charge de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9a678-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="9a678-106">Si vous souhaitez activer la haute disponibilité, vous devrez déployer au moins 2 appliances sur un site.</span><span class="sxs-lookup"><span data-stu-id="9a678-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="9a678-107">Vous pouvez également convertir une appliance existante pour prendre en charge la haute disponibilité une fois celle-ci déployée.</span><span class="sxs-lookup"><span data-stu-id="9a678-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="9a678-108">Déployer la première instance Skype Entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="9a678-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="9a678-109">Pour déployer la première appliance sur un site, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante afin d'inscrire l'appliance :</span><span class="sxs-lookup"><span data-stu-id="9a678-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```
Register-CcAppliance
```

<span data-ttu-id="9a678-110">Suivez les instructions pour spécifier le mot de passe et le nom de compte d'administration du client.</span><span class="sxs-lookup"><span data-stu-id="9a678-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="9a678-111">Utilisez le compte que vous avez créé pour la gestion en ligne dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9a678-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="9a678-112">Suivez également les instructions pour spécifier les mots de passe de certificat externe, d'administration de mode sans échec, d'administration de domaine et d'administration d'ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="9a678-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="9a678-113">Dans la version 1.4.2 et les versions antérieures, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur du mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur</span><span class="sxs-lookup"><span data-stu-id="9a678-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="9a678-114">Dans la version 2,0 et les versions ultérieures, suivez également les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="9a678-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="9a678-115">Pour commencer l'installation, ouvrez une console PowerShell en tant qu'administrateur et exécutez l'applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9a678-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="9a678-116">Ajouter une appliance à un site existant</span><span class="sxs-lookup"><span data-stu-id="9a678-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="9a678-117">Vous pouvez développer un site de connecteur Cloud existant pour prendre en charge le HA en ajoutant des appareils supplémentaires au site.</span><span class="sxs-lookup"><span data-stu-id="9a678-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="9a678-118">Suivez les étapes pour préparer votre appareil Cloud Connector comme décrit dans [la rubrique préparer votre appareil Cloud Connector](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="9a678-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="9a678-119">Notez que certaines étapes sont requises uniquement pour la première appliance dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9a678-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="9a678-120">Confirmez que l’annuaire de sites existe et qu’il est correctement configuré pour une prise en charge haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9a678-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="9a678-p104">N'exécutez l'applet de commande suivante que sur le serveur hôte nouvellement ajouté pour mettre les informations de topologie à jour dans votre configuration de client Office 365. Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l'applet de commande sur chaque serveur hôte nouvellement ajouté un par un :</span><span class="sxs-lookup"><span data-stu-id="9a678-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```
   Register-CcAppliance
   ```

3. <span data-ttu-id="9a678-p105">Mettez la topologie à jour sur les appliances existantes en exécutant l'applet de commande suivante sur chaque serveur hôte. N'exécutez l'applet de commande que sur les appliances existantes.</span><span class="sxs-lookup"><span data-stu-id="9a678-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
   ```
   Publish-CcAppliance
   ```

4. <span data-ttu-id="9a678-125">N'exécutez l'applet de commande suivante que sur les serveurs hôtes nouvellement ajoutés.</span><span class="sxs-lookup"><span data-stu-id="9a678-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="9a678-126">N'exécutez pas cet applet de commande sur l'appliance existante.</span><span class="sxs-lookup"><span data-stu-id="9a678-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="9a678-127">Si vous souhaitez ajouter plusieurs appliances en même temps, exécutez l'applet de commande sur chaque serveur hôte nouvellement ajouté un par un :</span><span class="sxs-lookup"><span data-stu-id="9a678-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="9a678-128">Si le chemin d’accès du dossier local de l’annuaire de sites est défini, vous devez définir un partage de fichiers pour ce dossier et utiliser un chemin d’accès UNC pour l’annuaire de sites sur la nouvelle appliance.</span><span class="sxs-lookup"><span data-stu-id="9a678-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="9a678-129">Vous pouvez faire en sorte que le premier annuaire du site du matériel soit associé au chemin d’accès local ou qu’il utilise le chemin UNC du partage dans le même dossier.</span><span class="sxs-lookup"><span data-stu-id="9a678-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="9a678-130">Si l’emplacement de l’annuaire de sites partagés change, tous les appareils précédemment installés doivent être désinstallés puis réinstallés.</span><span class="sxs-lookup"><span data-stu-id="9a678-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="9a678-131">> important: le mot de passe du compte CceService et du compte CABackupFile doit être le même sur toutes les applications déployées dans le site, de sorte que les appareils puissent accéder au partage de l’annuaire de sites et au fichier de sauvegarde de l’autorité de certification crypté dans l’annuaire de sites.</span><span class="sxs-lookup"><span data-stu-id="9a678-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="9a678-132">Supprimer une appliance d'un site existant</span><span class="sxs-lookup"><span data-stu-id="9a678-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="9a678-133">Pour supprimer une appliance d'un site existant :</span><span class="sxs-lookup"><span data-stu-id="9a678-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="9a678-134">N'exécutez l'applet de commande suivante que sur les serveurs hôtes à supprimer du site pour mettre les informations de topologie à jour dans votre configuration de client Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a678-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="9a678-135">N'exécutez l'applet de commande suivante que sur les serveurs hôtes à partir desquels vous souhaitez supprimer tous les ordinateurs virtuels de l'appliance.</span><span class="sxs-lookup"><span data-stu-id="9a678-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```
   Uninstall-CcAppliance
   ```


