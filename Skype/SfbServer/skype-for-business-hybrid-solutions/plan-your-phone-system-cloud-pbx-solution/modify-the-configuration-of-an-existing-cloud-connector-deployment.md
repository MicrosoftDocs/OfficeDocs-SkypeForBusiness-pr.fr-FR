---
title: Modifier la configuration d'un déploiement Cloud Connector existant
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’un Skype existant pour le nuage connecteur Édition 1.4.1 ou déploiement ultérieur.
ms.openlocfilehash: abe7d9be6ec0ae48ff8cbac09475c6a41bf2a49f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893054"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="030a4-103">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="030a4-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="030a4-104">Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’un Skype existant pour le nuage connecteur Édition 1.4.1 ou déploiement ultérieur.</span><span class="sxs-lookup"><span data-stu-id="030a4-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="030a4-105">Modifier la configuration d'un seul site</span><span class="sxs-lookup"><span data-stu-id="030a4-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="030a4-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-106"></span></span>

<span data-ttu-id="030a4-107">Si le site ne comporte qu'une seule appliance, lorsque vous souhaitez modifier les paramètres de configuration une fois l'appliance déployée, vous pouvez modifier le fichier CloudConnector.ini et recommencer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="030a4-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="030a4-108">Exécutez l'applet de commande suivante pour désinstaller tous les ordinateurs virtuels existants sur le serveur hôte :</span><span class="sxs-lookup"><span data-stu-id="030a4-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="030a4-109">Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :</span><span class="sxs-lookup"><span data-stu-id="030a4-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="030a4-110">Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.</span><span class="sxs-lookup"><span data-stu-id="030a4-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="030a4-111">Exécutez la cmdlet suivante pour mettre à jour la configuration : (cette étape n’est applicable que pour la version 2 ; pour les versions antérieures, passez à l’étape suivante).</span><span class="sxs-lookup"><span data-stu-id="030a4-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="030a4-112">Exécutez l’applet de commande suivante pour inscrire de nouveau l'appliance :</span><span class="sxs-lookup"><span data-stu-id="030a4-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="030a4-113">Exécutez l’applet de commande suivante pour installer Skype Entreprise, version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="030a4-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```
   Install-CcAppliance
   ```

<span data-ttu-id="030a4-114">Si le site comporte plusieurs appliances, vous devez suivre ces étapes, modifier le fichier CloudConnector.ini et redéployer les appliances une par une.</span><span class="sxs-lookup"><span data-stu-id="030a4-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="030a4-115">Exécutez l’applet de commande suivante pour désinstaller tous les ordinateurs virtuels existants dans l’application en cours :</span><span class="sxs-lookup"><span data-stu-id="030a4-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="030a4-116">Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :</span><span class="sxs-lookup"><span data-stu-id="030a4-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="030a4-117">Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.</span><span class="sxs-lookup"><span data-stu-id="030a4-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="030a4-118">Exécutez la cmdlet suivante pour mettre à jour la configuration : (cette étape n’est applicable que pour la version 2 ; pour les versions antérieures, passez à l’étape suivante).</span><span class="sxs-lookup"><span data-stu-id="030a4-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="030a4-119">Exécutez l’applet de commande suivante pour inscrire de nouveau l'appliance :</span><span class="sxs-lookup"><span data-stu-id="030a4-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```
   Register-CcAppliance
   ```

6. <span data-ttu-id="030a4-120">Exécutez l’applet de commande suivante sur toutes les autres appliances du site pour récupérer la dernière configuration :</span><span class="sxs-lookup"><span data-stu-id="030a4-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```
   Publish-CcAppliance
   ```

7. <span data-ttu-id="030a4-121">Exécutez l’applet de commande suivante pour redéployer nuage connecteur sur le matériel en cours :</span><span class="sxs-lookup"><span data-stu-id="030a4-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="030a4-122">Modifier la configuration de plusieurs sites</span><span class="sxs-lookup"><span data-stu-id="030a4-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="030a4-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-123"></span></span>

<span data-ttu-id="030a4-124">Pour modifier la configuration pour plusieurs sites dans un déploiement, suivez les étapes d’un seul site, mise à jour d’un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="030a4-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="030a4-125">Modifier la configuration de votre client Office 365 pour activer les mises à jour automatiques</span><span class="sxs-lookup"><span data-stu-id="030a4-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="030a4-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-126"></span></span>

<span data-ttu-id="030a4-127">Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques de Bits, vous devez utiliser le Skype pour le compte d’administrateur client Business pour la gestion en ligne et l’utilisation de PowerShell à distance des clients comme suit.</span><span class="sxs-lookup"><span data-stu-id="030a4-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="030a4-128">Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou des mises à jour automatiques des fichiers binaires, votre hôte et la machine virtuelle peuvent manquer des mises à jour importantes et nuage connecteur ne seront pas modifiés automatiquement vers la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="030a4-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="030a4-129">Il est vivement recommandé de d’activer les mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="030a4-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="030a4-130">La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="030a4-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="030a4-131">Exécutez l’applet de commande suivante pour vous assurer que EnableAutoUpdate est définie sur True :</span><span class="sxs-lookup"><span data-stu-id="030a4-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="030a4-132">Créez une fenêtre temporelle de mise à jour automatique pour le client.</span><span class="sxs-lookup"><span data-stu-id="030a4-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="030a4-p103">Cette fenêtre temporelle peut être quotidienne, hebdomadaire et mensuelle. Toutes les fenêtres temporelles doivent comporter une heure de début et une durée.</span><span class="sxs-lookup"><span data-stu-id="030a4-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="030a4-135">Pour une fenêtre temporelle quotidienne, seules l'heure de début et la durée sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="030a4-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="030a4-136">Pour une fenêtre temporelle hebdomadaire, les jours de la semaine sont nécessaires, et il peut d'agir d'un seul jour ou de plusieurs jours.</span><span class="sxs-lookup"><span data-stu-id="030a4-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="030a4-p104">Les fenêtres temporelles mensuelles peuvent être de deux types. Le premier consiste à spécifier le jour du mois, et il peut s'agir d'un seul jour. Le second consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, et il peut s'agir d'une seule semaine ou d'un seul jour ou de plusieurs.</span><span class="sxs-lookup"><span data-stu-id="030a4-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="030a4-p105">Chaque client peut disposer de 20 fenêtres temporelles définies. La fenêtre temporelle par défaut est créée pour un nouveau client comme fenêtre temporelle par défaut pour la mise à jour du système d’exploitation et de Bits. Exécutez l’applet ou les applets de commande suivantes pour définir une fenêtre temporelle quotidienne, hebdomadaire ou mensuelle :</span><span class="sxs-lookup"><span data-stu-id="030a4-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="030a4-143">Affecter des périodes de mise à jour sur le site.</span><span class="sxs-lookup"><span data-stu-id="030a4-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="030a4-144">Les fenêtres temporelles de mises à jour d'OS et de Bits sont configurées séparément.</span><span class="sxs-lookup"><span data-stu-id="030a4-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="030a4-145">OS et Bits peuvent recevoir une seule fenêtre temporelle ou plusieurs.</span><span class="sxs-lookup"><span data-stu-id="030a4-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="030a4-146">Chaque fenêtre temporelle peut être affectée à différents sites et pour différents objectifs (mise à jour de Bits et d'OS).</span><span class="sxs-lookup"><span data-stu-id="030a4-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="030a4-147">Exécutez l’applet de commande suivante pour définir la fenêtre de temps pour le site :</span><span class="sxs-lookup"><span data-stu-id="030a4-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="030a4-148">Mettre à jour les informations d’identification d’administration de client dédié</span><span class="sxs-lookup"><span data-stu-id="030a4-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="030a4-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-149"></span></span>

<span data-ttu-id="030a4-150">Modifications d’administration dans le client Office 365 pour le connecteur sur le nuage sont effectuées à partir d’un compte disposant des autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="030a4-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="030a4-151">Dans les versions antérieures nuage connecteur 2.0, ce compte est un compte d’administrateur client globale dédié.</span><span class="sxs-lookup"><span data-stu-id="030a4-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="030a4-152">Dans le nuage connecteur 2.0 et versions ultérieures, ce compte peut être un compte Office 365 avec Skype pour des droits d’administrateur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="030a4-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="030a4-153">Si vos informations d’identification du compte d’administration changent dans Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans le nuage connecteur en exécutant la commande administrateur PowerShell suivante sur chaque appliance nuage connecteur que vous avez déployé :</span><span class="sxs-lookup"><span data-stu-id="030a4-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="030a4-154">Mettre à jour le mot de passe pour le serveur hôte</span><span class="sxs-lookup"><span data-stu-id="030a4-154">Update the password for the host server</span></span>
<span data-ttu-id="030a4-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-155"></span></span>

> [!NOTE]
> <span data-ttu-id="030a4-156">Cette section est applicable à la version en nuage connecteur 2.0 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="030a4-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="030a4-157">Toutes les informations d’identification sur le nuage connecteur sont stockées dans le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».</span><span class="sxs-lookup"><span data-stu-id="030a4-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="030a4-158">Lorsque le mot de passe sur le serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="030a4-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="030a4-159">Pour mettre à jour les informations d’identification stockées localement sur le matériel de nuage connecteur, utilisez les applets de commande [Get-CcCredential](get-cccredential.md) et [Set-CcCredential](set-cccredential.md) et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="030a4-160">Exécutez les commandes suivantes pour récupérer les mots de passe que vous aurez besoin plus tard :</span><span class="sxs-lookup"><span data-stu-id="030a4-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="030a4-161">Get-CcCredential - AccountType DomainAdmin - DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="030a4-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="030a4-162">Get-CcCredential - AccountType VMAdmin - DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="030a4-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="030a4-163">Get-CcCredential - AccountType CceService - DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="030a4-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="030a4-164">Modifier le mot de passe de votre compte sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="030a4-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="030a4-165">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="030a4-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="030a4-166">Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».</span><span class="sxs-lookup"><span data-stu-id="030a4-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="030a4-167">Lancer une console PowerShell en tant qu’administrateur et exécutez « Register-CcAppliance-Local » à entrer les mots de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="030a4-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="030a4-168">Assurez-vous que vous entrez le même mot de que passe avant le déploiement dans le nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="030a4-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="030a4-169">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe en tant que CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="030a4-170">Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyées à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="030a4-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="030a4-171">Exécutez Set-CcCredential - AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="030a4-172">Pour les informations d’identification du compte ancien à l’invite, entrez les informations d’identification que vous avez utilisé pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="030a4-173">Lorsque vous y êtes invité pour les nouvelles informations d’identification du compte, entrez le mot de passe pour le mot de passe DomainAdmin renvoyée à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="030a4-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="030a4-174">Exécutez Set-CcCredential - AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="030a4-175">Pour les informations d’identification du compte ancien à l’invite, entrez les informations d’identification que vous avez utilisé pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="030a4-176">Lorsque vous y êtes invité pour les nouvelles informations d’identification du compte, entrez le mot de passe pour le mot de passe VmAdmin renvoyée à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="030a4-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="030a4-177">Mettre à jour le mot de passe pour le compte CceService</span><span class="sxs-lookup"><span data-stu-id="030a4-177">Update the password for the CceService account</span></span>
<span data-ttu-id="030a4-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-178"></span></span>

> [!NOTE]
> <span data-ttu-id="030a4-179">Cette section est applicable à la version en nuage connecteur 2.0.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="030a4-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="030a4-180">Le service de nuage connecteur s’exécute le service de gestion du connecteur sur le nuage.</span><span class="sxs-lookup"><span data-stu-id="030a4-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="030a4-181">Le compte CceService est créé au cours du déploiement en nuage connecteur Edition et stocké dans les fichiers suivants : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml » et « % SystemDrive%\Programdata\Cloudconnector\credentials... CceService.xml ».</span><span class="sxs-lookup"><span data-stu-id="030a4-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="030a4-182">Pour vous assurer que tous les appareils peuvent accéder au partage de répertoire de site, le mot de passe pour le compte CceService doit être identiques sur tous les appareils déployés au sein du site.</span><span class="sxs-lookup"><span data-stu-id="030a4-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="030a4-183">Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="030a4-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="030a4-184">Par défaut, le compte CceService est configuré comme « Le mot de passe n’expire jamais ».</span><span class="sxs-lookup"><span data-stu-id="030a4-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="030a4-185">Lorsque vous mettez à jour le mot de passe, Microsoft recommande de cette configuration.</span><span class="sxs-lookup"><span data-stu-id="030a4-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="030a4-186">Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation de pointe et en dehors des périodes de mise à jour automatique pour les mises à jour de Windows ou de bits.</span><span class="sxs-lookup"><span data-stu-id="030a4-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="030a4-187">Lorsque vous mettez à jour le mot de passe, l’appliance doit être drainés et redémarré, qui prend un certain temps.</span><span class="sxs-lookup"><span data-stu-id="030a4-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="030a4-188">Redémarrage de l’appliance interrompt les opérations de mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="030a4-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="030a4-189">Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier les informations d’identification et les mettre à jour dans le fichier stocké localement.</span><span class="sxs-lookup"><span data-stu-id="030a4-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="030a4-190">Pour chaque application qui appartient au même site PSTN, vous devez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="030a4-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="030a4-191">Exécutez les commandes suivantes pour récupérer les noms de compte et les mots de passe que vous utiliserez plus tard :</span><span class="sxs-lookup"><span data-stu-id="030a4-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```
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

2. <span data-ttu-id="030a4-192">Exécutez l’applet de commande entrée-CcUpdate pour décharger le matériel et la déplacer en mode maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="030a4-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="030a4-193">Mettre à jour le mot de passe du compte CceService sur le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="030a4-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="030a4-194">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="030a4-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="030a4-195">Exécutez l’applet de commande Restore-CcCredentials pour entrer de nouveau les mots de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="030a4-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="030a4-196">Assurez-vous que vous entrez le même mot de que passe avant le déploiement de nuage connecteur à l’exception du compte CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="030a4-197">Pour le compte CceService, entrez votre nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="030a4-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="030a4-198">Assurez-vous que le nouveau mot de passe pour le compte CceService est la même pour tous les matériels dans le site PSTN.</span><span class="sxs-lookup"><span data-stu-id="030a4-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="030a4-199">Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe en tant que CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="030a4-200">Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyées à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="030a4-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="030a4-201">Exécutez Set-CcCredential - AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="030a4-202">Pour les informations d’identification du compte ancien à l’invite, entrez les informations d’identification que vous avez utilisé pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="030a4-203">Lorsque vous y êtes invité pour les nouvelles informations d’identification du compte, entrez le mot de passe pour le mot de passe DomainAdmin renvoyée à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="030a4-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="030a4-204">Exécutez Set-CcCredential - AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="030a4-205">Pour les informations d’identification du compte ancien à l’invite, entrez les informations d’identification que vous avez utilisé pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="030a4-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="030a4-206">Lorsque vous y êtes invité pour les nouvelles informations d’identification du compte, entrez le mot de passe pour le mot de passe VmAdmin renvoyée à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="030a4-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="030a4-207">Exécutez l’applet de commande Exit-CcUpdate pour déplacer le matériel en mode maintenance manuelle.</span><span class="sxs-lookup"><span data-stu-id="030a4-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="030a4-208">Après avoir terminé ces étapes sur tous les appareils dans le même site PSTN, supprimez les fichiers suivants dans le répertoire racine du site :</span><span class="sxs-lookup"><span data-stu-id="030a4-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="030a4-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="030a4-209">CcLockFile</span></span>
    
    - <span data-ttu-id="030a4-210">Site_\<nom complet du Pool de Sip externe Edge\></span><span class="sxs-lookup"><span data-stu-id="030a4-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="030a4-211">Tenant_\<nom complet du Pool de Sip externe Edge\></span><span class="sxs-lookup"><span data-stu-id="030a4-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="030a4-212">TenantConfigLock_\<nom complet du Pool de Sip externe Edge\></span><span class="sxs-lookup"><span data-stu-id="030a4-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="030a4-213">Ajouter un domaine SIP</span><span class="sxs-lookup"><span data-stu-id="030a4-213">Add a new SIP domain</span></span>
<span data-ttu-id="030a4-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-214"></span></span>

<span data-ttu-id="030a4-215">Pour ajouter un domaine SIP (ou plusieurs domaines SIP) à votre déploiement en nuage connecteur existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="030a4-216">Assurez-vous que vous avez effectué les étapes pour mettre à jour votre domaine dans Office 365 et ont la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="030a4-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="030a4-217">Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, voir [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="030a4-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="030a4-218">Mettre à jour le fichier de configuration du connecteur sur le nuage avec le nouveau domaine SIP ou des domaines.</span><span class="sxs-lookup"><span data-stu-id="030a4-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="030a4-219">Demander un nouveau certificat externe Edge avec des noms SAN supplémentaires pour domaine.SIP pour chaque domaine SIP défini dans votre configuration de connecteur dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="030a4-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="030a4-220">Définir le chemin d’accès pour le nouveau certificat externe Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="030a4-221">Suivez les instructions pour [Modifier la configuration d’un seul site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="030a4-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="030a4-222">Modifier le domaine SIP principal</span><span class="sxs-lookup"><span data-stu-id="030a4-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="030a4-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-223"></span></span>

<span data-ttu-id="030a4-224">Si vous devez modifier le domaine SIP principal de votre déploiement en nuage connecteur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="030a4-225">Assurez-vous que vous avez effectué les étapes pour mettre à jour votre domaine dans Office 365 et ont la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="030a4-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="030a4-226">Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, voir [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="030a4-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="030a4-227">Mettre à jour le fichier de configuration du connecteur sur le nuage avec le nouveau domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="030a4-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="030a4-228">Demander un nouveau certificat externe Edge avec des noms SAN supplémentaires pour domaine.SIP pour chaque domaine SIP défini dans votre configuration de connecteur dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="030a4-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="030a4-229">Définir le chemin d’accès pour le nouveau certificat externe Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="030a4-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="030a4-230">Supprimer l’inscription du client pour chaque application dans un site en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur le nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="030a4-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="030a4-231">Supprimer l’inscription de sites pour chaque site en exécutant la cmdlet suivante dans Skype pour Business Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="030a4-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="030a4-232">Désinstaller chaque appliance en exécutant la cmdlet suivante dans administrateur PowerShell sur le nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="030a4-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="030a4-233">Enregistrer chaque appliance en exécutant la cmdlet suivante dans administrateur PowerShell sur le nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="030a4-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="030a4-234">Installer chaque matériel, un par un, en exécutant la cmdlet suivante dans administrateur PowerShell sur le nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="030a4-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="030a4-235">Remplacer le certificat de serveur Edge externe avec un nouveau certificat</span><span class="sxs-lookup"><span data-stu-id="030a4-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="030a4-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="030a4-236"></span></span>

<span data-ttu-id="030a4-237">Lorsque vous devez remplacer le certificat de serveur Edge externe sur vos applications dans le nuage connecteur, vous devez obtenir un nouveau certificat de serveur Edge, préparer le fichier PFX contenant la chaîne de certificats complète et la clé privée, puis procédez comme suit sur chaque appliance :</span><span class="sxs-lookup"><span data-stu-id="030a4-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="030a4-238">Placer l’application en mode maintenance à l’aide de l’applet de commande entrée-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="030a4-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="030a4-239">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="030a4-239">Run the following command:</span></span> 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="030a4-240">Si le mot de passe du nouveau certificat est identique à l’ancien, l’importation sera réussie.</span><span class="sxs-lookup"><span data-stu-id="030a4-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="030a4-241">Si le mot de passe est différent, vous obtenez une erreur que le mot de passe est incorrect, et vous devez réinitialiser le mot de passe en exécutant l’applet de commande Register-CcAppliance avec le paramètre - Local, et puis répéter l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="030a4-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="030a4-242">Prendre l’appliance en mode maintenance à l’aide de l’applet de commande Exit - CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="030a4-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

