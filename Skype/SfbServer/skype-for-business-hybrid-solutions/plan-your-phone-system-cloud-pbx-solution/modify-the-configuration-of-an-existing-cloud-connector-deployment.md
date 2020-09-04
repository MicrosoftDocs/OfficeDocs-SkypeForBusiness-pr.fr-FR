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
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359110"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="c42ab-103">Modifier la configuration d’un déploiement Cloud Connector existant</span><span class="sxs-lookup"><span data-stu-id="c42ab-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="c42ab-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="c42ab-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c42ab-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="c42ab-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="c42ab-106">Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version de Skype entreprise et du déploiement de la version ultérieure de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c42ab-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="c42ab-107">Modifier la configuration d’un seul site</span><span class="sxs-lookup"><span data-stu-id="c42ab-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="c42ab-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="c42ab-109">S’il n’y a qu’une seule Appliance dans le site, lorsque vous souhaitez modifier les paramètres de configuration après le déploiement de l’appliance, vous pouvez modifier le fichier CloudConnector.ini et relancer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="c42ab-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="c42ab-110">Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="c42ab-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="c42ab-111">Exécutez l’applet de commande suivante pour annuler l’inscription de l’appliance :</span><span class="sxs-lookup"><span data-stu-id="c42ab-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="c42ab-112">Mettez à jour le fichier CloudConnector.ini dans l’annuaire d’appliances.</span><span class="sxs-lookup"><span data-stu-id="c42ab-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="c42ab-113">Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions antérieures, passez à l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="c42ab-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="c42ab-114">Exécutez l’applet de commande suivante pour réinscrire l’appliance :</span><span class="sxs-lookup"><span data-stu-id="c42ab-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="c42ab-115">Exécutez l’applet de commande suivante pour installer Skype entreprise, version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="c42ab-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="c42ab-116">S’il y a plusieurs Appliances dans le site, vous devrez suivre ces étapes, modifier le fichier CloudConnector.ini et redéployer les appliances une par une.</span><span class="sxs-lookup"><span data-stu-id="c42ab-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="c42ab-117">Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="c42ab-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="c42ab-118">Exécutez l’applet de commande suivante pour annuler l’inscription de l’appliance :</span><span class="sxs-lookup"><span data-stu-id="c42ab-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="c42ab-119">Mettez à jour le fichier CloudConnector.ini dans l’annuaire d’appliances.</span><span class="sxs-lookup"><span data-stu-id="c42ab-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="c42ab-120">Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions antérieures, passez à l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="c42ab-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="c42ab-121">Exécutez l’applet de commande suivante pour réinscrire l’appliance :</span><span class="sxs-lookup"><span data-stu-id="c42ab-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="c42ab-122">Exécutez l’applet de commande suivante sur toutes les autres Appliances du site pour récupérer la dernière configuration :</span><span class="sxs-lookup"><span data-stu-id="c42ab-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="c42ab-123">Exécutez l’applet de commande suivante pour redéployer Cloud Connector sur l’appliance actuelle :</span><span class="sxs-lookup"><span data-stu-id="c42ab-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="c42ab-124">Modifier la configuration de plusieurs sites</span><span class="sxs-lookup"><span data-stu-id="c42ab-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="c42ab-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="c42ab-126">Pour modifier la configuration de plusieurs sites dans un déploiement, suivez les étapes d’un seul site, mettant à jour un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="c42ab-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="c42ab-127">Modifier la configuration de votre organisation Microsoft 365 ou Office 365 pour activer les mises à jour automatiques</span><span class="sxs-lookup"><span data-stu-id="c42ab-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="c42ab-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="c42ab-129">Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques bits, vous devez utiliser le compte d’administrateur client Skype entreprise pour la gestion en ligne et utiliser l’environnement PowerShell distant client comme suit.</span><span class="sxs-lookup"><span data-stu-id="c42ab-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="c42ab-130">Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou les mises à jour automatiques bits, votre ordinateur hôte et votre ordinateur virtuel risquent de manquer d’importantes mises à jour Windows, et Cloud Connector ne sera pas mis à niveau automatiquement vers la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="c42ab-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="c42ab-131">Il est vivement recommandé d’activer les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="c42ab-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="c42ab-132">La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="c42ab-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="c42ab-133">Exécutez l’applet de commande suivante pour vous assurer que la valeur de EnableAutoUpdate est true :</span><span class="sxs-lookup"><span data-stu-id="c42ab-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="c42ab-134">Créer une fenêtre de mise à jour automatique pour le client.</span><span class="sxs-lookup"><span data-stu-id="c42ab-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="c42ab-135">La fenêtre de temps peut être quotidienne, hebdomadaire et mensuelle.</span><span class="sxs-lookup"><span data-stu-id="c42ab-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="c42ab-136">Toutes les fenêtres temporelles ont besoin d’une heure de début et d’une durée.</span><span class="sxs-lookup"><span data-stu-id="c42ab-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="c42ab-137">Pour une fenêtre de temps quotidien, seule l’heure de début et la durée sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="c42ab-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="c42ab-138">Pour une fenêtre de temps hebdomadaire, les jours de la semaine sont nécessaires, ce qui peut être un seul jour ou plusieurs jours.</span><span class="sxs-lookup"><span data-stu-id="c42ab-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="c42ab-139">Pour une fenêtre de temps mensuelle, il peut y avoir deux types.</span><span class="sxs-lookup"><span data-stu-id="c42ab-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="c42ab-140">Le premier type consiste à spécifier le jour du mois, qui peut être un seul jour.</span><span class="sxs-lookup"><span data-stu-id="c42ab-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="c42ab-141">Le deuxième type consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, qui peuvent être un ou plusieurs éléments.</span><span class="sxs-lookup"><span data-stu-id="c42ab-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="c42ab-142">Chaque client peut avoir 20 fenêtres de temps définies.</span><span class="sxs-lookup"><span data-stu-id="c42ab-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="c42ab-143">La fenêtre de temps par défaut est créée pour un nouveau client comme fenêtre temporelle par défaut pour la mise à jour du système d’exploitation et la mise à jour bits.</span><span class="sxs-lookup"><span data-stu-id="c42ab-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="c42ab-144">Exécutez les cmdlets suivantes pour définir la période quotidienne, hebdomadaire ou mensuelle :</span><span class="sxs-lookup"><span data-stu-id="c42ab-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="c42ab-145">Affectez les fenêtres heure de mise à jour au site.</span><span class="sxs-lookup"><span data-stu-id="c42ab-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="c42ab-146">Les fenêtres heure de mise à jour bits et heure de mise à jour du système d’exploitation sont configurées séparément.</span><span class="sxs-lookup"><span data-stu-id="c42ab-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="c42ab-147">Elles peuvent toutes deux être affectées à une ou plusieurs fenêtres temporelles.</span><span class="sxs-lookup"><span data-stu-id="c42ab-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="c42ab-148">Chaque fenêtre de temps peut être affectée à différents sites et à différentes fins (mise à jour bits et mise à jour du système d’exploitation).</span><span class="sxs-lookup"><span data-stu-id="c42ab-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="c42ab-149">Exécutez l’applet de commande suivante pour définir la fenêtre de temps pour le site :</span><span class="sxs-lookup"><span data-stu-id="c42ab-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="c42ab-150">Mettre à jour les informations d’identification d’administrateur client dédié</span><span class="sxs-lookup"><span data-stu-id="c42ab-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="c42ab-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="c42ab-152">Les modifications administratives dans l’organisation Microsoft 365 ou Office 365 pour Cloud Connector sont effectuées à partir d’un compte disposant des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="c42ab-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="c42ab-153">Dans les versions de Cloud Connector antérieures à 2,0, ce compte est un compte d’administrateur client global dédié.</span><span class="sxs-lookup"><span data-stu-id="c42ab-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="c42ab-154">Dans le Cloud Connector versions 2,0 et versions ultérieures, ce compte peut être un compte Microsoft 365 ou Office 365 avec des droits d’administrateur de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c42ab-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="c42ab-155">Si les informations d’identification de votre compte d’administrateur changent dans Microsoft 365 ou Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans Cloud Connector en exécutant la commande PowerShell d’administration suivante sur chaque appliance Cloud Connector que vous avez déployée :</span><span class="sxs-lookup"><span data-stu-id="c42ab-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="c42ab-156">Mettre à jour le mot de passe du serveur hôte</span><span class="sxs-lookup"><span data-stu-id="c42ab-156">Update the password for the host server</span></span>
<span data-ttu-id="c42ab-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="c42ab-158">Cette section s’applique à Cloud Connector version 2,0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="c42ab-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="c42ab-159">Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».</span><span class="sxs-lookup"><span data-stu-id="c42ab-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="c42ab-160">Lorsque le mot de passe sur le serveur hôte est modifié, vous devez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="c42ab-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="c42ab-161">Pour mettre à jour les informations d’identification stockées localement sur le matériel de Cloud Connector, utilisez les cmdlets [Get-applet cccredential](get-cccredential.md) et [Set-applet cccredential](set-cccredential.md) et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="c42ab-162">Exécutez les commandes suivantes pour récupérer les mots de passe dont vous aurez besoin plus tard :</span><span class="sxs-lookup"><span data-stu-id="c42ab-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="c42ab-163">Get-applet cccredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="c42ab-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="c42ab-164">Get-applet cccredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="c42ab-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="c42ab-165">Get-applet cccredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="c42ab-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="c42ab-166">Modifiez le mot de passe de votre compte sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="c42ab-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="c42ab-167">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="c42ab-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="c42ab-168">Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».</span><span class="sxs-lookup"><span data-stu-id="c42ab-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="c42ab-169">Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description.</span><span class="sxs-lookup"><span data-stu-id="c42ab-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="c42ab-170">Veillez à entrer le même mot de passe que celui que vous avez entré auparavant pour le déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c42ab-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="c42ab-171">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="c42ab-172">Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c42ab-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="c42ab-173">Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="c42ab-174">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="c42ab-175">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="c42ab-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="c42ab-176">Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="c42ab-177">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="c42ab-178">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="c42ab-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="c42ab-179">Mettre à jour le mot de passe du compte CceService</span><span class="sxs-lookup"><span data-stu-id="c42ab-179">Update the password for the CceService account</span></span>
<span data-ttu-id="c42ab-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="c42ab-181">Cette section s’applique à Cloud Connector version 2.0.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="c42ab-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="c42ab-182">Le service Cloud Connector exécute le service de gestion de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c42ab-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="c42ab-183">Le compte CceService est créé pendant le déploiement de Cloud Connector Edition et stocké dans les fichiers suivants : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML» et « % SystemDrive% \Programdata\Cloudconnector\credentials..CceService.xml ».</span><span class="sxs-lookup"><span data-stu-id="c42ab-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="c42ab-184">Pour vous assurer que toutes les appliances peuvent accéder au partage de l’annuaire de sites, le mot de passe du compte CceService doit être le même sur toutes les appliances déployées dans le site.</span><span class="sxs-lookup"><span data-stu-id="c42ab-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="c42ab-185">Gardez les éléments suivants à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="c42ab-186">Par défaut, le compte CceService est configuré comme « le mot de passe n’expire jamais ».</span><span class="sxs-lookup"><span data-stu-id="c42ab-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="c42ab-187">Lorsque vous mettez à jour le mot de passe, Microsoft vous recommande de conserver cette configuration.</span><span class="sxs-lookup"><span data-stu-id="c42ab-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="c42ab-188">Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation non-pics et en dehors des fenêtres de temps de mise à jour automatique pour les mises à jour de bits ou Windows.</span><span class="sxs-lookup"><span data-stu-id="c42ab-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="c42ab-189">Lorsque vous mettez à jour le mot de passe, l’appliance doit être vidée et redémarrée, ce qui prend un peu de temps.</span><span class="sxs-lookup"><span data-stu-id="c42ab-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="c42ab-190">Le redémarrage de l’appliance interrompt les opérations de mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="c42ab-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="c42ab-191">Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier toutes les informations d’identification et les mettre à jour dans le fichier stocké localement.</span><span class="sxs-lookup"><span data-stu-id="c42ab-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="c42ab-192">Pour chaque appliance qui appartient au même site RTC, vous devez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c42ab-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="c42ab-193">Exécutez les commandes suivantes pour récupérer les noms de compte et les mots de passe que vous utiliserez plus tard :</span><span class="sxs-lookup"><span data-stu-id="c42ab-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="c42ab-194">Exécutez la cmdlet Enter-applet ccupdate pour décharger l’appliance et la déplacer en mode de maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="c42ab-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="c42ab-195">Mettez à jour le mot de passe du compte CceService sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="c42ab-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="c42ab-196">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="c42ab-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="c42ab-197">Exécutez la cmdlet Restore-CcCredentials pour entrer de nouveau les mots de passe à la suite de la description.</span><span class="sxs-lookup"><span data-stu-id="c42ab-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="c42ab-198">Assurez-vous d’entrer le mot de passe que vous avez entré auparavant pour le déploiement de Cloud Connector, à l’exception du compte CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="c42ab-199">Pour le compte CceService, entrez votre nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c42ab-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="c42ab-200">Assurez-vous que le nouveau mot de passe du compte CceService est le même pour toutes les appliances dans le site RTC.</span><span class="sxs-lookup"><span data-stu-id="c42ab-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="c42ab-201">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="c42ab-202">Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c42ab-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="c42ab-203">Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="c42ab-204">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="c42ab-205">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="c42ab-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="c42ab-206">Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="c42ab-207">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="c42ab-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="c42ab-208">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="c42ab-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="c42ab-209">Exécutez la cmdlet Exit-applet ccupdate pour déplacer l’appliance en mode de maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="c42ab-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="c42ab-210">Après avoir effectué ces étapes sur toutes les appliances du même site RTC, supprimez les fichiers suivants dans le répertoire racine du site :</span><span class="sxs-lookup"><span data-stu-id="c42ab-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="c42ab-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="c42ab-211">CcLockFile</span></span>
    
    - <span data-ttu-id="c42ab-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="c42ab-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="c42ab-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="c42ab-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="c42ab-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="c42ab-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="c42ab-215">Ajouter un nouveau domaine SIP</span><span class="sxs-lookup"><span data-stu-id="c42ab-215">Add a new SIP domain</span></span>
<span data-ttu-id="c42ab-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="c42ab-217">Pour ajouter un nouveau domaine SIP (ou plusieurs domaines SIP) à votre déploiement Cloud Connector existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="c42ab-218">Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="c42ab-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="c42ab-219">Pour plus d’informations sur la configuration de votre domaine dans Microsoft 365 ou Office 365, consultez la rubrique [Ajouter un domaine à microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="c42ab-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="c42ab-220">Mettez à jour le fichier de configuration de Cloud Connector avec le ou les nouveaux domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="c42ab-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="c42ab-221">Demandez un nouveau certificat externe de serveur Edge avec des noms SAN supplémentaires pour SIP. domain pour chaque domaine SIP défini dans la configuration de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c42ab-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="c42ab-222">Définissez le chemin d’accès pour le nouveau certificat externe de serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="c42ab-223">Suivez les instructions pour [modifier la configuration d’un seul site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="c42ab-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="c42ab-224">Modifier le domaine SIP principal</span><span class="sxs-lookup"><span data-stu-id="c42ab-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="c42ab-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="c42ab-226">Si vous devez modifier le domaine SIP principal dans votre déploiement de Cloud Connector, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="c42ab-227">Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="c42ab-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="c42ab-228">Pour plus d’informations sur la configuration de votre domaine dans Microsoft 365 ou Office 365, consultez la rubrique [Ajouter un domaine à microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="c42ab-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="c42ab-229">Mettez à jour le fichier de configuration de Cloud Connector avec le nouveau domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="c42ab-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="c42ab-230">Demandez un nouveau certificat externe de serveur Edge avec des noms SAN supplémentaires pour SIP. domain pour chaque domaine SIP défini dans la configuration de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c42ab-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="c42ab-231">Définissez le chemin d’accès pour le nouveau certificat externe de serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="c42ab-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="c42ab-232">Supprimez l’inscription du client pour chaque appliance dans un site en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="c42ab-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="c42ab-233">Supprimez l’inscription de site pour chaque site en exécutant l’applet de commande suivante dans Skype entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="c42ab-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="c42ab-234">Désinstallez chaque appliance en exécutant l’applet de commande suivante dans la session PowerShell d’administrateur sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="c42ab-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="c42ab-235">Enregistrez chaque appliance en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="c42ab-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="c42ab-236">Installez chaque appliance, une par une, en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="c42ab-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="c42ab-237">Remplacer le certificat de serveur Edge externe par un nouveau certificat</span><span class="sxs-lookup"><span data-stu-id="c42ab-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="c42ab-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="c42ab-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="c42ab-239">Lorsque vous devez remplacer le certificat de serveur Edge externe sur vos appareils Cloud Connector, vous devez obtenir un nouveau certificat de serveur Edge, préparer le fichier PFX contenant la clé privée et la chaîne de certificats complète, puis effectuer les opérations suivantes sur chaque appliance :</span><span class="sxs-lookup"><span data-stu-id="c42ab-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="c42ab-240">Placez l’appliance en mode maintenance à l’aide de la cmdlet Enter-applet ccupdate.</span><span class="sxs-lookup"><span data-stu-id="c42ab-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="c42ab-241">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c42ab-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="c42ab-242">Si le mot de passe du nouveau certificat est le même que l’ancien, l’importation réussit.</span><span class="sxs-lookup"><span data-stu-id="c42ab-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="c42ab-243">Si le mot de passe est différent, vous recevrez un message d’erreur indiquant que le mot de passe est incorrect, et vous devrez réinitialiser le mot de passe en exécutant la cmdlet Register-applet ccappliance avec le paramètre-local, puis en répétant l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="c42ab-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="c42ab-244">Désactivez l’appliance en mode maintenance à l’aide de la cmdlet Exit-applet ccupdate.</span><span class="sxs-lookup"><span data-stu-id="c42ab-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

