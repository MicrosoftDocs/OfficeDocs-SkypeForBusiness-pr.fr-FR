---
title: Modifier la configuration d'un déploiement Cloud Connector existant
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version actuelle de Skype entreprise Cloud Connector, ou d’une version ultérieure.
ms.openlocfilehash: ead952c0ba567a8e5d81c52144de597e50d24014
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002284"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="4dbc3-103">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="4dbc3-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="4dbc3-104">Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version actuelle de Skype entreprise Cloud Connector, ou d’une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="4dbc3-105">Modifier la configuration d'un seul site</span><span class="sxs-lookup"><span data-stu-id="4dbc3-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="4dbc3-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-106"></span></span>

<span data-ttu-id="4dbc3-107">Si le site ne comporte qu'une seule appliance, lorsque vous souhaitez modifier les paramètres de configuration une fois l'appliance déployée, vous pouvez modifier le fichier CloudConnector.ini et recommencer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="4dbc3-108">Exécutez l'applet de commande suivante pour désinstaller tous les ordinateurs virtuels existants sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="4dbc3-109">Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="4dbc3-110">Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="4dbc3-111">Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions précédentes, passez à l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="4dbc3-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="4dbc3-112">Exécutez l’applet de commande suivante pour inscrire de nouveau l'appliance :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="4dbc3-113">Exécutez l’applet de commande suivante pour installer Skype Entreprise, version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="4dbc3-114">Si le site comporte plusieurs appliances, vous devez suivre ces étapes, modifier le fichier CloudConnector.ini et redéployer les appliances une par une.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="4dbc3-115">Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur le matériel actuel :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="4dbc3-116">Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="4dbc3-117">Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="4dbc3-118">Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions précédentes, passez à l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="4dbc3-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="4dbc3-119">Exécutez l’applet de commande suivante pour inscrire de nouveau l'appliance :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="4dbc3-120">Exécutez l’applet de commande suivante sur toutes les autres appliances du site pour récupérer la dernière configuration :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="4dbc3-121">Exécutez l’applet de commande suivante pour redéployer le Cloud Connector sur le matériel actuel :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="4dbc3-122">Modifier la configuration de plusieurs sites</span><span class="sxs-lookup"><span data-stu-id="4dbc3-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="4dbc3-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-123"></span></span>

<span data-ttu-id="4dbc3-124">Pour modifier la configuration de plusieurs sites dans un déploiement, suivez les étapes d’un seul site pour mettre à jour un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="4dbc3-125">Modification de la configuration de votre client Office 365 pour activer les mises à jour automatiques</span><span class="sxs-lookup"><span data-stu-id="4dbc3-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="4dbc3-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-126"></span></span>

<span data-ttu-id="4dbc3-127">Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques bits, vous devez utiliser le compte d’administrateur de clients Skype entreprise pour une gestion en ligne et utiliser PowerShell distant client comme suit.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="4dbc3-128">Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou les mises à jour automatiques bits, il est possible que votre hôte et votre ordinateur virtuel manquent de nouvelles mises à jour Windows, et que Cloud Connector ne sera pas automatiquement mis à niveau vers la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="4dbc3-129">Il est vivement recommandé de d’activer les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="4dbc3-130">La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="4dbc3-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="4dbc3-131">Exécutez l’applet de commande suivante pour vous assurer que EnableAutoUpdate est définie sur True :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="4dbc3-132">Créez une fenêtre temporelle de mise à jour automatique pour le client.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="4dbc3-p103">Cette fenêtre temporelle peut être quotidienne, hebdomadaire et mensuelle. Toutes les fenêtres temporelles doivent comporter une heure de début et une durée.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="4dbc3-135">Pour une fenêtre temporelle quotidienne, seules l'heure de début et la durée sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="4dbc3-136">Pour une fenêtre temporelle hebdomadaire, les jours de la semaine sont nécessaires, et il peut d'agir d'un seul jour ou de plusieurs jours.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="4dbc3-p104">Les fenêtres temporelles mensuelles peuvent être de deux types. Le premier consiste à spécifier le jour du mois, et il peut s'agir d'un seul jour. Le second consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, et il peut s'agir d'une seule semaine ou d'un seul jour ou de plusieurs.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="4dbc3-p105">Chaque client peut disposer de 20 fenêtres temporelles définies. La fenêtre temporelle par défaut est créée pour un nouveau client comme fenêtre temporelle par défaut pour la mise à jour du système d’exploitation et de Bits. Exécutez l’applet ou les applets de commande suivantes pour définir une fenêtre temporelle quotidienne, hebdomadaire ou mensuelle :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="4dbc3-143">Attribuez des heures de mise à jour à votre site.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="4dbc3-144">Les fenêtres temporelles de mises à jour d'OS et de Bits sont configurées séparément.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="4dbc3-145">OS et Bits peuvent recevoir une seule fenêtre temporelle ou plusieurs.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="4dbc3-146">Chaque fenêtre temporelle peut être affectée à différents sites et pour différents objectifs (mise à jour de Bits et d'OS).</span><span class="sxs-lookup"><span data-stu-id="4dbc3-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="4dbc3-147">Exécutez l’applet de commande suivante pour définir la fenêtre délai pour le site :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="4dbc3-148">Mettre à jour les informations d’identification d’administrateur de clients dédiées</span><span class="sxs-lookup"><span data-stu-id="4dbc3-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="4dbc3-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-149"></span></span>

<span data-ttu-id="4dbc3-150">Les modifications d’administration apportées au client 365 pour le Cloud Connector sont effectuées à partir d’un compte disposant des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="4dbc3-151">Dans les versions Cloud Connector antérieures à 2,0, ce compte est un compte d’administrateur de clients global dédié.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="4dbc3-152">Dans Cloud Connector versions 2,0 et ultérieures, ce compte peut être un compte Office 365 avec des droits d’administrateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="4dbc3-153">Si les informations d’identification de votre compte d’administrateur sont modifiées dans Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans Cloud Connector en exécutant la commande PowerShell d’administration suivante sur chacun des appareils Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="4dbc3-154">Mettre à jour le mot de passe du serveur hôte</span><span class="sxs-lookup"><span data-stu-id="4dbc3-154">Update the password for the host server</span></span>
<span data-ttu-id="4dbc3-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-155"></span></span>

> [!NOTE]
> <span data-ttu-id="4dbc3-156">Cette section s’applique à la version 2,0 et les versions ultérieures du connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="4dbc3-157">Les informations d’identification de tous les connecteurs Cloud sont stockées dans le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="4dbc3-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="4dbc3-158">Lorsque le mot de passe du serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="4dbc3-159">Pour mettre à jour les informations d’identification stockées localement sur le périphérique Cloud Connector, utilisez les applets de connexion [Get-CcCredential](get-cccredential.md) et [Set-CcCredential](set-cccredential.md) , et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="4dbc3-160">Pour récupérer les mots de passe dont vous aurez besoin plus tard, exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="4dbc3-161">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="4dbc3-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="4dbc3-162">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="4dbc3-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="4dbc3-163">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="4dbc3-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="4dbc3-164">Modifiez le mot de passe de votre compte sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="4dbc3-165">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="4dbc3-166">Supprimez le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="4dbc3-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="4dbc3-167">Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance-local » pour entrer de nouveau le mot de passe suivi de la description.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="4dbc3-168">Assurez-vous d’entrer le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="4dbc3-169">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="4dbc3-170">Si le mot de passe DomainAdmin, VMAdmin et CceService renvoyé à l’étape 1 est différent, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="4dbc3-171">Exécutez Set-CcCredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="4dbc3-172">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="4dbc3-173">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="4dbc3-174">Exécutez Set-CcCredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="4dbc3-175">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="4dbc3-176">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="4dbc3-177">Mettez à jour le mot de passe du compte CceService</span><span class="sxs-lookup"><span data-stu-id="4dbc3-177">Update the password for the CceService account</span></span>
<span data-ttu-id="4dbc3-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-178"></span></span>

> [!NOTE]
> <span data-ttu-id="4dbc3-179">Cette section s’applique à Cloud Connector version 2.0.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="4dbc3-180">Le service Cloud Connector exécute le service de gestion de connecteurs Cloud.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="4dbc3-181">Le compte CceService est créé lors du déploiement de l’édition Cloud Connector et est stocké dans les fichiers suivants : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "et"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. Xml».</span><span class="sxs-lookup"><span data-stu-id="4dbc3-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="4dbc3-182">Pour vous assurer que tous les appareils peuvent accéder au partage de l’annuaire de sites, le mot de passe du compte CceService doit être le même sur tous les appareils déployés dans le site.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="4dbc3-183">Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="4dbc3-184">Par défaut, le compte CceService est configuré comme « le mot de passe n’expire jamais ».</span><span class="sxs-lookup"><span data-stu-id="4dbc3-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="4dbc3-185">Lorsque vous mettez à jour le mot de passe, Microsoft vous recommande de le protéger.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="4dbc3-186">Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation sans pointe et en dehors des mises à jour automatiques de Windows pour les bits ou les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="4dbc3-187">Lorsque vous mettez à jour le mot de passe, l’application doit être vidée et redémarrée, ce qui prend du temps.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="4dbc3-188">Le redémarrage de l’application interrompt les opérations de mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="4dbc3-189">Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier toutes les informations d’identification et les mettre à jour dans le fichier stocké localement.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="4dbc3-190">Pour chaque appareil qui appartient au même site RTC, vous devez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="4dbc3-191">Pour récupérer les noms de compte et mots de passe que vous utiliserez plus tard, exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="4dbc3-192">Exécutez l’applet de conduite Enter-CcUpdate pour décharger l’appareil et le déplacer vers le mode de maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="4dbc3-193">Mettez à jour le mot de passe du compte CceService sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="4dbc3-194">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="4dbc3-195">Exécutez l’applet de commande Restore-CcCredentials pour entrer de nouveau le mot de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="4dbc3-196">Assurez-vous d’entrer le mot de passe que vous avez entré précédemment pour le déploiement du Cloud Connector, sauf pour le compte CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="4dbc3-197">Pour le compte CceService, entrez votre nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="4dbc3-198">Vérifiez que le nouveau mot de passe du compte CceService est le même pour tous les appareils du site PSTN.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="4dbc3-199">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="4dbc3-200">Si le mot de passe DomainAdmin, VMAdmin et CceService renvoyé à l’étape 1 est différent, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="4dbc3-201">Exécutez Set-CcCredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="4dbc3-202">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="4dbc3-203">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="4dbc3-204">Exécutez Set-CcCredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="4dbc3-205">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="4dbc3-206">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="4dbc3-207">Exécutez l’applet de connexion Exit-CcUpdate pour éloigner l’application du mode de maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="4dbc3-208">Après avoir effectué ces étapes sur tous les appareils du même site RTC, supprimez les fichiers suivants dans le répertoire racine du site :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="4dbc3-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="4dbc3-209">CcLockFile</span></span>
    
    - <span data-ttu-id="4dbc3-210">Nom\<de domaine complet du pool Sip externe Site_ Edge\></span><span class="sxs-lookup"><span data-stu-id="4dbc3-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="4dbc3-211">Nom\<de domaine complet du pool Sip externe Tenant_ Edge\></span><span class="sxs-lookup"><span data-stu-id="4dbc3-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="4dbc3-212">Nom\<de domaine complet du pool Sip externe TenantConfigLock_ Edge\></span><span class="sxs-lookup"><span data-stu-id="4dbc3-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="4dbc3-213">Ajouter un nouveau domaine SIP</span><span class="sxs-lookup"><span data-stu-id="4dbc3-213">Add a new SIP domain</span></span>
<span data-ttu-id="4dbc3-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-214"></span></span>

<span data-ttu-id="4dbc3-215">Pour ajouter un nouveau domaine SIP (ou plusieurs domaines SIP) à votre déploiement Cloud Cloud actuel, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="4dbc3-216">Vérifiez que vous avez terminé les étapes de mise à jour de votre domaine dans Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="4dbc3-217">Pour plus d’informations sur la configuration de votre domaine dans Office 365, voir [Ajouter un domaine à office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="4dbc3-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="4dbc3-218">Mettez à jour le fichier de configuration du connecteur Cloud avec le nouveau domaine ou domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="4dbc3-219">Demandez un nouveau certificat externe avec des noms de réseau SIP supplémentaires pour SIP. domain pour chaque domaine SIP défini dans votre configuration Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="4dbc3-220">Définissez le chemin pour le nouveau certificat externe du périmètre comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="4dbc3-221">Suivez les instructions pour [modifier la configuration d’un site unique](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou pour [modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="4dbc3-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="4dbc3-222">Modifier le domaine SIP principal</span><span class="sxs-lookup"><span data-stu-id="4dbc3-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="4dbc3-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-223"></span></span>

<span data-ttu-id="4dbc3-224">Si vous devez modifier le domaine SIP principal dans votre déploiement Cloud Connector, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="4dbc3-225">Vérifiez que vous avez terminé les étapes de mise à jour de votre domaine dans Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="4dbc3-226">Pour plus d’informations sur la configuration de votre domaine dans Office 365, voir [Ajouter un domaine à office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="4dbc3-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="4dbc3-227">Mettez à jour le fichier de configuration du connecteur Cloud avec le nouveau domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="4dbc3-228">Demandez un nouveau certificat externe avec des noms de réseau SIP supplémentaires pour SIP. domain pour chaque domaine SIP défini dans votre configuration Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="4dbc3-229">Définissez le chemin pour le nouveau certificat externe du périmètre comme suit :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="4dbc3-230">Supprimez l’inscription de locataire pour chaque application dans un site en exécutant l’applet de commande suivante dans PowerShell PowerShell sur le Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="4dbc3-231">Supprimez l’inscription de site pour chaque site en exécutant l’applet de commande suivante dans Skype entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="4dbc3-232">Désinstallez chaque application en exécutant l’applet de commande suivante dans PowerShell PowerShell dans Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="4dbc3-233">Enregistrez chaque application en exécutant l’applet de commande suivante dans PowerShell PowerShell dans Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="4dbc3-234">Installez chaque application, une par une, en exécutant l’applet de commande suivante dans PowerShell PowerShell sur le Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="4dbc3-235">Remplacer le certificat de bord externe par un nouveau certificat</span><span class="sxs-lookup"><span data-stu-id="4dbc3-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="4dbc3-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4dbc3-236"></span></span>

<span data-ttu-id="4dbc3-237">Lorsque vous avez besoin de remplacer le certificat de frontière externe sur vos appareils Cloud Connector, vous devez obtenir un nouveau certificat de bord, préparer le fichier PFX contenant la clé privée et la chaîne de certificats complète, puis effectuer les opérations suivantes sur chaque application :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="4dbc3-238">Placez l’application en mode de maintenance à l’aide de l’applet de passe Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="4dbc3-239">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4dbc3-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="4dbc3-240">Si le mot de passe du nouveau certificat est identique à l’ancien, l’importation est réussie.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="4dbc3-241">Si le mot de passe est différent, vous recevez un message d’erreur indiquant que le mot de passe est incorrect, et vous devez réinitialiser le mot de passe en exécutant l’applet de passe Register-CcAppliance à l’aide du paramètre-local, puis répéter l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="4dbc3-242">Emportez l’application en mode de maintenance à l’aide de l’applet de connexion Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="4dbc3-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

