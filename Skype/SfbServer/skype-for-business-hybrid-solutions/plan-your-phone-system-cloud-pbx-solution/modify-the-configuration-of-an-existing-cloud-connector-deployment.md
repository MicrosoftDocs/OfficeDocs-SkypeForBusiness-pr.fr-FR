---
title: Modifier la configuration d’un déploiement Cloud Connector existant
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version de Skype entreprise et du déploiement de la version ultérieure de Skype entreprise.
ms.openlocfilehash: 4b551d7cd7a61a1113b4b2bb05e2c0f5ca4f3288
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220294"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="7706b-103">Modifier la configuration d’un déploiement Cloud Connector existant</span><span class="sxs-lookup"><span data-stu-id="7706b-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="7706b-104">Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version de Skype entreprise et du déploiement de la version ultérieure de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="7706b-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="7706b-105">Modifier la configuration d’un seul site</span><span class="sxs-lookup"><span data-stu-id="7706b-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="7706b-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="7706b-107">S’il n’y a qu’une seule Appliance dans le site, lorsque vous souhaitez modifier les paramètres de configuration après le déploiement de l’appliance, vous pouvez modifier le fichier CloudConnector. ini et relancer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7706b-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="7706b-108">Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="7706b-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="7706b-109">Exécutez l’applet de commande suivante pour annuler l’inscription de l’appliance :</span><span class="sxs-lookup"><span data-stu-id="7706b-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="7706b-110">Mettez à jour le fichier CloudConnector. ini dans le répertoire de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="7706b-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="7706b-111">Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions antérieures, passez à l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="7706b-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="7706b-112">Exécutez l’applet de commande suivante pour réinscrire l’appliance :</span><span class="sxs-lookup"><span data-stu-id="7706b-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="7706b-113">Exécutez l’applet de commande suivante pour installer Skype entreprise, version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7706b-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="7706b-114">S’il y a plusieurs Appliances dans le site, vous devrez suivre ces étapes, modifier le fichier CloudConnector. ini et redéployer les appliances une par une.</span><span class="sxs-lookup"><span data-stu-id="7706b-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="7706b-115">Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="7706b-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="7706b-116">Exécutez l’applet de commande suivante pour annuler l’inscription de l’appliance :</span><span class="sxs-lookup"><span data-stu-id="7706b-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="7706b-117">Mettez à jour le fichier CloudConnector. ini dans le répertoire de l’appliance.</span><span class="sxs-lookup"><span data-stu-id="7706b-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="7706b-118">Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions antérieures, passez à l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="7706b-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="7706b-119">Exécutez l’applet de commande suivante pour réinscrire l’appliance :</span><span class="sxs-lookup"><span data-stu-id="7706b-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="7706b-120">Exécutez l’applet de commande suivante sur toutes les autres Appliances du site pour récupérer la dernière configuration :</span><span class="sxs-lookup"><span data-stu-id="7706b-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="7706b-121">Exécutez l’applet de commande suivante pour redéployer Cloud Connector sur l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="7706b-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="7706b-122">Modifier la configuration de plusieurs sites</span><span class="sxs-lookup"><span data-stu-id="7706b-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="7706b-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="7706b-124">Pour modifier la configuration de plusieurs sites dans un déploiement, suivez les étapes d’un seul site, mettant à jour un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="7706b-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="7706b-125">Modifier la configuration de votre organisation Microsoft 365 ou Office 365 pour activer les mises à jour automatiques</span><span class="sxs-lookup"><span data-stu-id="7706b-125">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="7706b-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="7706b-127">Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques bits, vous devez utiliser le compte d’administrateur client Skype entreprise pour la gestion en ligne et utiliser l’environnement PowerShell distant client comme suit.</span><span class="sxs-lookup"><span data-stu-id="7706b-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="7706b-128">Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou les mises à jour automatiques bits, votre ordinateur hôte et votre ordinateur virtuel risquent de manquer d’importantes mises à jour Windows, et Cloud Connector ne sera pas mis à niveau automatiquement vers la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="7706b-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="7706b-129">Il est vivement recommandé d’activer les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="7706b-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="7706b-130">La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="7706b-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="7706b-131">Exécutez l’applet de commande suivante pour vous assurer que la valeur de EnableAutoUpdate est true :</span><span class="sxs-lookup"><span data-stu-id="7706b-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="7706b-132">Créer une fenêtre de mise à jour automatique pour le client.</span><span class="sxs-lookup"><span data-stu-id="7706b-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="7706b-133">La fenêtre de temps peut être quotidienne, hebdomadaire et mensuelle.</span><span class="sxs-lookup"><span data-stu-id="7706b-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="7706b-134">Toutes les fenêtres temporelles ont besoin d’une heure de début et d’une durée.</span><span class="sxs-lookup"><span data-stu-id="7706b-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="7706b-135">Pour une fenêtre de temps quotidien, seule l’heure de début et la durée sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7706b-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="7706b-136">Pour une fenêtre de temps hebdomadaire, les jours de la semaine sont nécessaires, ce qui peut être un seul jour ou plusieurs jours.</span><span class="sxs-lookup"><span data-stu-id="7706b-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="7706b-137">Pour une fenêtre de temps mensuelle, il peut y avoir deux types.</span><span class="sxs-lookup"><span data-stu-id="7706b-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="7706b-138">Le premier type consiste à spécifier le jour du mois, qui peut être un seul jour.</span><span class="sxs-lookup"><span data-stu-id="7706b-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="7706b-139">Le deuxième type consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, qui peuvent être un ou plusieurs éléments.</span><span class="sxs-lookup"><span data-stu-id="7706b-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="7706b-140">Chaque client peut avoir 20 fenêtres de temps définies.</span><span class="sxs-lookup"><span data-stu-id="7706b-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="7706b-141">La fenêtre de temps par défaut est créée pour un nouveau client comme fenêtre temporelle par défaut pour la mise à jour du système d’exploitation et la mise à jour bits.</span><span class="sxs-lookup"><span data-stu-id="7706b-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="7706b-142">Exécutez les cmdlets suivantes pour définir la période quotidienne, hebdomadaire ou mensuelle :</span><span class="sxs-lookup"><span data-stu-id="7706b-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="7706b-143">Affectez les fenêtres heure de mise à jour au site.</span><span class="sxs-lookup"><span data-stu-id="7706b-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="7706b-144">Les fenêtres heure de mise à jour bits et heure de mise à jour du système d’exploitation sont configurées séparément.</span><span class="sxs-lookup"><span data-stu-id="7706b-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="7706b-145">Elles peuvent toutes deux être affectées à une ou plusieurs fenêtres temporelles.</span><span class="sxs-lookup"><span data-stu-id="7706b-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="7706b-146">Chaque fenêtre de temps peut être affectée à différents sites et à différentes fins (mise à jour bits et mise à jour du système d’exploitation).</span><span class="sxs-lookup"><span data-stu-id="7706b-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="7706b-147">Exécutez l’applet de commande suivante pour définir la fenêtre de temps pour le site :</span><span class="sxs-lookup"><span data-stu-id="7706b-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="7706b-148">Mettre à jour les informations d’identification d’administrateur client dédié</span><span class="sxs-lookup"><span data-stu-id="7706b-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="7706b-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="7706b-150">Les modifications administratives dans l’organisation Microsoft 365 ou Office 365 pour Cloud Connector sont effectuées à partir d’un compte disposant des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7706b-150">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="7706b-151">Dans les versions de Cloud Connector antérieures à 2,0, ce compte est un compte d’administrateur client global dédié.</span><span class="sxs-lookup"><span data-stu-id="7706b-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="7706b-152">Dans le Cloud Connector versions 2,0 et versions ultérieures, ce compte peut être un compte Microsoft 365 ou Office 365 avec des droits d’administrateur de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="7706b-152">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="7706b-153">Si les informations d’identification de votre compte d’administrateur changent dans Microsoft 365 ou Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans Cloud Connector en exécutant la commande PowerShell d’administration suivante sur chaque appliance Cloud Connector que vous avez déployée :</span><span class="sxs-lookup"><span data-stu-id="7706b-153">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="7706b-154">Mettre à jour le mot de passe du serveur hôte</span><span class="sxs-lookup"><span data-stu-id="7706b-154">Update the password for the host server</span></span>
<span data-ttu-id="7706b-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="7706b-156">Cette section s’applique à Cloud Connector version 2,0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="7706b-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="7706b-157">Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . Xml».</span><span class="sxs-lookup"><span data-stu-id="7706b-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="7706b-158">Lorsque le mot de passe sur le serveur hôte est modifié, vous devez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="7706b-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="7706b-159">Pour mettre à jour les informations d’identification stockées localement sur le matériel de Cloud Connector, utilisez les cmdlets [Get-applet cccredential](get-cccredential.md) et [Set-applet cccredential](set-cccredential.md) et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="7706b-160">Exécutez les commandes suivantes pour récupérer les mots de passe dont vous aurez besoin plus tard :</span><span class="sxs-lookup"><span data-stu-id="7706b-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="7706b-161">Get-applet cccredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="7706b-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="7706b-162">Get-applet cccredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="7706b-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="7706b-163">Get-applet cccredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="7706b-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="7706b-164">Modifiez le mot de passe de votre compte sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7706b-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="7706b-165">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7706b-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="7706b-166">Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . Xml».</span><span class="sxs-lookup"><span data-stu-id="7706b-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="7706b-167">Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description.</span><span class="sxs-lookup"><span data-stu-id="7706b-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="7706b-168">Veillez à entrer le même mot de passe que celui que vous avez entré auparavant pour le déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7706b-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="7706b-169">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="7706b-170">Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7706b-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="7706b-171">Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="7706b-172">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="7706b-173">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="7706b-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="7706b-174">Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="7706b-175">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="7706b-176">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="7706b-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="7706b-177">Mettre à jour le mot de passe du compte CceService</span><span class="sxs-lookup"><span data-stu-id="7706b-177">Update the password for the CceService account</span></span>
<span data-ttu-id="7706b-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="7706b-179">Cette section s’applique à Cloud Connector version 2.0.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="7706b-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="7706b-180">Le service Cloud Connector exécute le service de gestion de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7706b-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="7706b-181">Le compte CceService est créé pendant le déploiement de Cloud Connector Edition et stocké dans les fichiers suivants : "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml» et «%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. Xml».</span><span class="sxs-lookup"><span data-stu-id="7706b-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="7706b-182">Pour vous assurer que toutes les appliances peuvent accéder au partage de l’annuaire de sites, le mot de passe du compte CceService doit être le même sur toutes les appliances déployées dans le site.</span><span class="sxs-lookup"><span data-stu-id="7706b-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="7706b-183">Gardez les éléments suivants à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="7706b-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="7706b-184">Par défaut, le compte CceService est configuré comme « le mot de passe n’expire jamais ».</span><span class="sxs-lookup"><span data-stu-id="7706b-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="7706b-185">Lorsque vous mettez à jour le mot de passe, Microsoft vous recommande de conserver cette configuration.</span><span class="sxs-lookup"><span data-stu-id="7706b-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="7706b-186">Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation non-pics et en dehors des fenêtres de temps de mise à jour automatique pour les mises à jour de bits ou Windows.</span><span class="sxs-lookup"><span data-stu-id="7706b-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="7706b-187">Lorsque vous mettez à jour le mot de passe, l’appliance doit être vidée et redémarrée, ce qui prend un peu de temps.</span><span class="sxs-lookup"><span data-stu-id="7706b-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="7706b-188">Le redémarrage de l’appliance interrompt les opérations de mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="7706b-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="7706b-189">Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier toutes les informations d’identification et les mettre à jour dans le fichier stocké localement.</span><span class="sxs-lookup"><span data-stu-id="7706b-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="7706b-190">Pour chaque appliance qui appartient au même site RTC, vous devez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7706b-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="7706b-191">Exécutez les commandes suivantes pour récupérer les noms de compte et les mots de passe que vous utiliserez plus tard :</span><span class="sxs-lookup"><span data-stu-id="7706b-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="7706b-192">Exécutez la cmdlet Enter-applet ccupdate pour décharger l’appliance et la déplacer en mode de maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="7706b-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="7706b-193">Mettez à jour le mot de passe du compte CceService sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7706b-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="7706b-194">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7706b-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="7706b-195">Exécutez la cmdlet Restore-CcCredentials pour entrer de nouveau les mots de passe à la suite de la description.</span><span class="sxs-lookup"><span data-stu-id="7706b-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="7706b-196">Assurez-vous d’entrer le mot de passe que vous avez entré auparavant pour le déploiement de Cloud Connector, à l’exception du compte CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="7706b-197">Pour le compte CceService, entrez votre nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7706b-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="7706b-198">Assurez-vous que le nouveau mot de passe du compte CceService est le même pour toutes les appliances dans le site RTC.</span><span class="sxs-lookup"><span data-stu-id="7706b-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="7706b-199">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="7706b-200">Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7706b-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="7706b-201">Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="7706b-202">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="7706b-203">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="7706b-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="7706b-204">Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="7706b-205">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="7706b-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="7706b-206">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="7706b-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="7706b-207">Exécutez la cmdlet Exit-applet ccupdate pour déplacer l’appliance en mode de maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="7706b-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="7706b-208">Après avoir effectué ces étapes sur toutes les appliances du même site RTC, supprimez les fichiers suivants dans le répertoire racine du site :</span><span class="sxs-lookup"><span data-stu-id="7706b-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="7706b-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="7706b-209">CcLockFile</span></span>
    
    - <span data-ttu-id="7706b-210">\<Nom de domaine complet du pool SIP externe Site_ Edge\></span><span class="sxs-lookup"><span data-stu-id="7706b-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="7706b-211">\<Nom de domaine complet du pool SIP externe Tenant_ Edge\></span><span class="sxs-lookup"><span data-stu-id="7706b-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="7706b-212">\<Nom de domaine complet du pool SIP externe TenantConfigLock_ Edge\></span><span class="sxs-lookup"><span data-stu-id="7706b-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="7706b-213">Ajouter un nouveau domaine SIP</span><span class="sxs-lookup"><span data-stu-id="7706b-213">Add a new SIP domain</span></span>
<span data-ttu-id="7706b-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="7706b-215">Pour ajouter un nouveau domaine SIP (ou plusieurs domaines SIP) à votre déploiement Cloud Connector existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="7706b-216">Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="7706b-216">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="7706b-217">Pour plus d’informations sur la configuration de votre domaine dans Microsoft 365 ou Office 365, consultez la rubrique [Ajouter un domaine à microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="7706b-217">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="7706b-218">Mettez à jour le fichier de configuration de Cloud Connector avec le ou les nouveaux domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="7706b-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="7706b-219">Demandez un nouveau certificat externe de serveur Edge avec des noms SAN supplémentaires pour SIP. domain pour chaque domaine SIP défini dans la configuration de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7706b-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="7706b-220">Définissez le chemin d’accès pour le nouveau certificat externe de serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="7706b-221">Suivez les instructions pour [modifier la configuration d’un seul site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="7706b-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="7706b-222">Modifier le domaine SIP principal</span><span class="sxs-lookup"><span data-stu-id="7706b-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="7706b-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="7706b-224">Si vous devez modifier le domaine SIP principal dans votre déploiement de Cloud Connector, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="7706b-225">Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="7706b-225">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="7706b-226">Pour plus d’informations sur la configuration de votre domaine dans Microsoft 365 ou Office 365, consultez la rubrique [Ajouter un domaine à microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="7706b-226">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="7706b-227">Mettez à jour le fichier de configuration de Cloud Connector avec le nouveau domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="7706b-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="7706b-228">Demandez un nouveau certificat externe de serveur Edge avec des noms SAN supplémentaires pour SIP. domain pour chaque domaine SIP défini dans la configuration de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7706b-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="7706b-229">Définissez le chemin d’accès pour le nouveau certificat externe de serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="7706b-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="7706b-230">Supprimez l’inscription du client pour chaque appliance dans un site en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7706b-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="7706b-231">Supprimez l’inscription de site pour chaque site en exécutant l’applet de commande suivante dans Skype entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="7706b-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="7706b-232">Désinstallez chaque appliance en exécutant l’applet de commande suivante dans la session PowerShell d’administrateur sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7706b-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="7706b-233">Enregistrez chaque appliance en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7706b-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="7706b-234">Installez chaque appliance, une par une, en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7706b-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="7706b-235">Remplacer le certificat de serveur Edge externe par un nouveau certificat</span><span class="sxs-lookup"><span data-stu-id="7706b-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="7706b-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7706b-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="7706b-237">Lorsque vous devez remplacer le certificat de serveur Edge externe sur vos appareils Cloud Connector, vous devez obtenir un nouveau certificat de serveur Edge, préparer le fichier PFX contenant la clé privée et la chaîne de certificats complète, puis effectuer les opérations suivantes sur chaque appliance :</span><span class="sxs-lookup"><span data-stu-id="7706b-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="7706b-238">Placez l’appliance en mode maintenance à l’aide de la cmdlet Enter-applet ccupdate.</span><span class="sxs-lookup"><span data-stu-id="7706b-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="7706b-239">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7706b-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="7706b-240">Si le mot de passe du nouveau certificat est le même que l’ancien, l’importation réussit.</span><span class="sxs-lookup"><span data-stu-id="7706b-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="7706b-241">Si le mot de passe est différent, vous recevrez un message d’erreur indiquant que le mot de passe est incorrect, et vous devrez réinitialiser le mot de passe en exécutant la cmdlet Register-applet ccappliance avec le paramètre-local, puis en répétant l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="7706b-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="7706b-242">Désactivez l’appliance en mode maintenance à l’aide de la cmdlet Exit-applet ccupdate.</span><span class="sxs-lookup"><span data-stu-id="7706b-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

