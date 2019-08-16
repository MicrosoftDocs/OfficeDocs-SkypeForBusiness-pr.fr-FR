---
title: Maintenance et opérations des salles de Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: Pour en savoir plus sur la gestion des salles de Microsoft Teams, reportez-vous à la rubrique nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: 601e9e31f6a874d84dae6f4a3b44c26324a7b6f3
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427942"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="7bb0b-103">Maintenance et opérations des salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="7bb0b-104">Pour en savoir plus sur la gestion des salles de Microsoft Teams, reportez-vous à la rubrique nouvelle génération de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="7bb0b-105">Microsoft teams est la solution de conférence la plus récente de Microsoft conçue pour transformer votre salle de réunion en une expérience riche et collaborative.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="7bb0b-106">Les utilisateurs apprécieront l’interface familière de Microsoft teams ou Skype entreprise et les administrateurs informatiques apprécieront une application de réunion Skype facilement déployée et gérée dans Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="7bb0b-107">Les salles de Microsoft teams sont conçues pour exploiter les équipements existants tels que les écrans LCD pour faciliter l’installation de Microsoft teams ou de Skype entreprise dans votre salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="7bb0b-108">Dans le cadre de la configuration supplémentaire, la gestion à distance est possible à l’aide de l’outil Moniteur Microsoft Azure, comme décrit dans la rubrique planification de la [gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-plan.md), [déploiement](azure-monitor-deploy.md) [ Appareils de salle Microsoft teams avec Azure Monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="7bb0b-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="7bb0b-109">Vous pouvez également [gérer les paramètres de la console de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md), qui inclut l’application d’un thème d’affichage personnalisé.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="7bb0b-110">Collecte de journaux sur les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="7bb0b-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-111"></span></span>

<span data-ttu-id="7bb0b-112">Pour recueillir les journaux, vous devez appeler le script de collection de journaux qui est fourni avec l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="7bb0b-113">En mode admin, démarrez une invite de commandes avec élévation de privilèges et émettez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="7bb0b-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="7bb0b-114">Les journaux seront en sortie sous forme de fichier ZIP dans c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="7bb0b-115">Paramètres de l’écran d’affichage</span><span class="sxs-lookup"><span data-stu-id="7bb0b-115">Front of Room Display Settings</span></span>
<span data-ttu-id="7bb0b-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-116"></span></span>

<span data-ttu-id="7bb0b-117">Configurez l’écran d’affichage en mode étendu.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="7bb0b-118">Cela permet de s’assurer que l’interface utilisateur de la console n’est pas dupliquée sur cet écran lorsque vous allumez le mode d’affichage.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7bb0b-119">Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="7bb0b-120">Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="7bb0b-121">Réinitialisation des salles de Microsoft Teams (restauration d’usine)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="7bb0b-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-122"></span></span>

<span data-ttu-id="7bb0b-123">Si Microsoft Teams ne fonctionne pas correctement, il peut être utile d’effectuer une réinitialisation d’usine.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="7bb0b-124">Pour cela, vous pouvez utiliser l’application paramètres dans l’onglet **récupération** . sous **réinitialiser ce PC**, sélectionnez **commencer**, puis supprimez **tout**.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="7bb0b-125">Suivez les invites restantes pour réinitialiser l’appareil.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7bb0b-126">Il existe un problème connu pour lequel les salles de Microsoft teams peuvent être désactivées si l’option **conserver mes fichiers-supprime des applications et des paramètres, mais** que vous avez sélectionné l’option conservation de vos fichiers personnels lors du processus de réinitialisation de Windows.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="7bb0b-127">N’utilisez _pas_ cette option.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="7bb0b-128">Options distantes prises en charge</span><span class="sxs-lookup"><span data-stu-id="7bb0b-128">Supported Remote Options</span></span>
<span data-ttu-id="7bb0b-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-129"></span></span>

<span data-ttu-id="7bb0b-130">Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="7bb0b-131">\*\*Groupe de travail \*\*</span><span class="sxs-lookup"><span data-stu-id="7bb0b-131">**Workgroup**</span></span>|<span data-ttu-id="7bb0b-132">**Aucun domaine joint**</span><span class="sxs-lookup"><span data-stu-id="7bb0b-132">**Not domain joined**</span></span>|<span data-ttu-id="7bb0b-133">**Domaine joint**</span><span class="sxs-lookup"><span data-stu-id="7bb0b-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7bb0b-134">Redémarrer</span><span class="sxs-lookup"><span data-stu-id="7bb0b-134">Restart</span></span>  <br/> |<span data-ttu-id="7bb0b-135">Bureau distant</span><span class="sxs-lookup"><span data-stu-id="7bb0b-135">Remote desktop</span></span>  <br/> <span data-ttu-id="7bb0b-136">Powershell distant</span><span class="sxs-lookup"><span data-stu-id="7bb0b-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="7bb0b-137">Bureau à distance (nécessite une configuration supplémentaire)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="7bb0b-138">PowerShell distant (nécessite une configuration supplémentaire)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="7bb0b-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="7bb0b-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="7bb0b-140">Mise à jour du SE</span><span class="sxs-lookup"><span data-stu-id="7bb0b-140">Update OS</span></span>  <br/> |<span data-ttu-id="7bb0b-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="7bb0b-141">Windows Update</span></span>  <br/> |<span data-ttu-id="7bb0b-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="7bb0b-142">Windows Update</span></span>  <br/> <span data-ttu-id="7bb0b-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="7bb0b-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="7bb0b-144">Mise à jour de l';application</span><span class="sxs-lookup"><span data-stu-id="7bb0b-144">App update</span></span>  <br/> |<span data-ttu-id="7bb0b-145">	Windows Store</span><span class="sxs-lookup"><span data-stu-id="7bb0b-145">Windows Store</span></span>  <br/> |<span data-ttu-id="7bb0b-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="7bb0b-146">Windows Store</span></span>  <br/> <span data-ttu-id="7bb0b-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="7bb0b-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="7bb0b-148">Configuration du compte Skype</span><span class="sxs-lookup"><span data-stu-id="7bb0b-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="7bb0b-149">Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="7bb0b-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="7bb0b-150">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="7bb0b-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="7bb0b-151">Accès aux journaux</span><span class="sxs-lookup"><span data-stu-id="7bb0b-151">Access logs</span></span>  <br/> |<span data-ttu-id="7bb0b-152">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="7bb0b-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="7bb0b-153">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="7bb0b-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="7bb0b-154">Configuration d’une stratégie de groupe pour les salles Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="7bb0b-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-155"></span></span>

<span data-ttu-id="7bb0b-156">Cette section décrit les paramètres système dont dépend le fonctionnement des salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="7bb0b-157">Lorsque vous rejoignez des salles de Microsoft teams à un domaine, vérifiez que votre stratégie de groupe ne remplace pas les paramètres du tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="7bb0b-158">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="7bb0b-158">**Setting**</span></span>|<span data-ttu-id="7bb0b-159">**Permet**</span><span class="sxs-lookup"><span data-stu-id="7bb0b-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7bb0b-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="7bb0b-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="7bb0b-161">Permet au démarrage de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="7bb0b-162">Gestion de l'\> alimentation-sur le ca, éteindre l’écran après 10 minutes</span><span class="sxs-lookup"><span data-stu-id="7bb0b-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="7bb0b-163">Gestion de l'\> alimentation-sur le secteur, jamais mettre le système en veille</span><span class="sxs-lookup"><span data-stu-id="7bb0b-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="7bb0b-164">Activation de l’affichage et de la réactivation des salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="7bb0b-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="7bb0b-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="7bb0b-166">Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="7bb0b-167">Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="7bb0b-168">Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="7bb0b-169">Active le compte Skype avec lequel toujours se connecter</span><span class="sxs-lookup"><span data-stu-id="7bb0b-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="7bb0b-170">Pour transférer des fichiers à l’aide de stratégies de groupe, voir [configurer un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7bb0b-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="7bb0b-171">Lorsque l’appareil de salle Microsoft teams est compatible avec la version suivante du système d’exploitation Windows 10, l’appareil est automatiquement mis à jour vers la version suivante par le biais de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-171">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="7bb0b-172">La mise à niveau vers la nouvelle version de Windows 10, ou via l’activation de la stratégie de groupe Windows Update pour les entreprises (WUFB) de Microsoft Teams ne peut pas être mise à niveau vers une version ultérieure de Windows 10 Les mises à jour de fonctionnalités sont reçues par le biais d’un objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-172">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="7bb0b-173">Un appareil doté de ces stratégies de groupe activé est connu pour rencontrer des problèmes liés à la mise à jour de Windows 10 du système d’exploitation par l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-173">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="7bb0b-174">Gestion distante à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bb0b-174">Remote Management using PowerShell</span></span>
<span data-ttu-id="7bb0b-175"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-175"></span></span>

<span data-ttu-id="7bb0b-176">Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (voir le tableau ci-dessous pour les exemples de script):</span><span class="sxs-lookup"><span data-stu-id="7bb0b-176">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="7bb0b-177">Obtenir les périphériques raccordés</span><span class="sxs-lookup"><span data-stu-id="7bb0b-177">Get attached devices</span></span>
    
- <span data-ttu-id="7bb0b-178">Obtenir l';état de l';application</span><span class="sxs-lookup"><span data-stu-id="7bb0b-178">Get app status</span></span>
    
- <span data-ttu-id="7bb0b-179">Obtenir les informations système</span><span class="sxs-lookup"><span data-stu-id="7bb0b-179">Get system info</span></span>
    
- <span data-ttu-id="7bb0b-180">Redémarrer le système</span><span class="sxs-lookup"><span data-stu-id="7bb0b-180">Reboot system</span></span>
    
- <span data-ttu-id="7bb0b-181">Récupérer les journaux</span><span class="sxs-lookup"><span data-stu-id="7bb0b-181">Retrieve logs</span></span>
    
- <span data-ttu-id="7bb0b-182">Transférer des fichiers (nécessite une salle Microsoft teams dans un domaine)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-182">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="7bb0b-183">Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-183">This functionality is off by default.</span></span> <span data-ttu-id="7bb0b-184">Pour effectuer les opérations suivantes, vous devez activer PowerShell distant pour votre environnement dans le système de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-184">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="7bb0b-185">Pour plus d’informations sur la façon d’activer PowerShell à distance, consultez la documentation sur **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="7bb0b-185">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="7bb0b-186">Par exemple, vous pouvez activer PowerShell à distance comme suit :</span><span class="sxs-lookup"><span data-stu-id="7bb0b-186">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="7bb0b-187">Connectez-vous en tant qu’administrateur sur un appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-187">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="7bb0b-188">Ouvrez une invite de commandes PowerShell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-188">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="7bb0b-189">Entrez la commande suivante : Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="7bb0b-189">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="7bb0b-190">Pour effectuer une opération de gestion :</span><span class="sxs-lookup"><span data-stu-id="7bb0b-190">To perform a management operation:</span></span>
  
1. <span data-ttu-id="7bb0b-191">Connectez-vous à un PC à l’aide d’informations d’identification de compte disposant des autorisations d’exécution des commandes PowerShell sur un appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-191">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="7bb0b-192">Ouvrez une invite de commandes PowerShell normale sur le PC.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-192">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="7bb0b-193">Copiez le texte de commande du tableau ci-dessous, puis collez-le à l’invite.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-193">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="7bb0b-194">Remplacez `<Device fqdn>` les champs par des valeurs FQDN appropriées à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-194">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="7bb0b-195">Remplacez \* \<Path\> \* par le nom de fichier et le chemin d’accès local du fichier de configuration SkypeSettings. xml principal (ou de l’image de thème).</span><span class="sxs-lookup"><span data-stu-id="7bb0b-195">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="7bb0b-196">Pour obtenir des appareils connectés</span><span class="sxs-lookup"><span data-stu-id="7bb0b-196">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="7bb0b-197">Obtenir l’état de l’application</span><span class="sxs-lookup"><span data-stu-id="7bb0b-197">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="7bb0b-198">Obtenir les informations système</span><span class="sxs-lookup"><span data-stu-id="7bb0b-198">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="7bb0b-199">Redémarrer le système</span><span class="sxs-lookup"><span data-stu-id="7bb0b-199">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="7bb0b-200">Récupérer les journaux</span><span class="sxs-lookup"><span data-stu-id="7bb0b-200">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="7bb0b-201">Transférer un fichier de configuration XML (ou graphique de thème)</span><span class="sxs-lookup"><span data-stu-id="7bb0b-201">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="7bb0b-202">Mises à jour logicielles</span><span class="sxs-lookup"><span data-stu-id="7bb0b-202">Software updates</span></span>
<span data-ttu-id="7bb0b-203"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-203"></span></span>

<span data-ttu-id="7bb0b-204">Par défaut, Microsoft teams services tente de se connecter au Windows Store pour obtenir la dernière version du logiciel de salle Microsoft Teams, de sorte que l’appareil exige un accès Internet régulier.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-204">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="7bb0b-205">Avant de contacter Microsoft avec des problèmes de support, assurez-vous que l’appareil Microsoft teams est chargé avec la dernière version de l’application.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-205">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="7bb0b-206">Par défaut, Microsoft teams se connecte à Windows Update pour extraire les mises à jour du microprogramme du système d’exploitation et du périphérique USB, et les installe en dehors des heures d’activité configurées.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-206">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="7bb0b-207">Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-207">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="7bb0b-208">Si vous souhaitez gérer les mises à jour manuellement et ne parvenez pas à suivre les procédures normales de la [Boutique Microsoft pour les entreprises](https://businessstore.microsoft.com/store) afin de [distribuer des applications hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), vous pouvez acquérir le fichier AppX approprié et les dépendances du [Kit de déploiement](https://go.microsoft.com/fwlink/?linkid=851168) (de les instructions de [configuration d’une console de salle Microsoft teams](console.md)) qui peuvent être utilisées avec SCCM.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-208">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="7bb0b-209">Le kit de déploiement est en retard sur le Windows Store, il se peut donc que la version ne corresponde pas toujours à la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-209">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="7bb0b-210">Pour effectuer une mise à jour à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bb0b-210">To update using Powershell</span></span>

1. <span data-ttu-id="7bb0b-211">Extrayez le package de l’installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) vers un partage auquel le périphérique peut accéder.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-211">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="7bb0b-212">Exécutez le script suivant ciblant les appareils de salle Microsoft Teams, en modifiant \<le partage\> sur le partage de l’appareil, selon le cas:</span><span class="sxs-lookup"><span data-stu-id="7bb0b-212">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="7bb0b-213">Mode Administrateur et gestion des appareils</span><span class="sxs-lookup"><span data-stu-id="7bb0b-213">Admin mode and device management</span></span>
<span data-ttu-id="7bb0b-214"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-214"></span></span>

<span data-ttu-id="7bb0b-215">Certaines fonctions de gestion (par exemple, l’installation manuelle d’un certificat d’autorité de certification privée) nécessitent la mise en mode d’administration de l’appareil surface Pro.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-215">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="7bb0b-216">Basculement en mode administrateur et retour lors de l’exécution de l’application Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7bb0b-216">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="7bb0b-217">Raccrochez tout appel en cours et retournez sur l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-217">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="7bb0b-218">Sélectionner l’icône d’engrenage et afficher le menu (les options sont **paramètres**, **accessibilité**et redémarrage de l' **appareil** ).</span><span class="sxs-lookup"><span data-stu-id="7bb0b-218">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="7bb0b-219">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-219">Select **Settings**.</span></span>
    
4. <span data-ttu-id="7bb0b-220">Entrez le mot de passe de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-220">Enter the Administrator Password.</span></span> <span data-ttu-id="7bb0b-221">L’écran d’installation s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-221">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7bb0b-222">Si l’appareil n’est pas joint à un domaine, le compte d’administrateur local (nom d’utilisateur «administrateur») est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-222">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="7bb0b-223">Le mot de passe par défaut de ce compte est "sfb", mais il est recommandé que votre organisation le change dès que possible pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-223">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="7bb0b-224">Si l’ordinateur est joint à un domaine, vous pouvez vous connecter à l’aide d’un compte de domaine à privilèges appropriés.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-224">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="7bb0b-225">Dans la colonne de gauche, sélectionnez **Paramètres Windows** .</span><span class="sxs-lookup"><span data-stu-id="7bb0b-225">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="7bb0b-226">Sélectionnez **Atteindre connexion d’administration**.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-226">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="7bb0b-227">Entrez le mot de passe de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-227">Enter the Administrator Password.</span></span> <span data-ttu-id="7bb0b-228">Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-228">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="7bb0b-229">Connectez-vous au bureau avec vos informations d’identification administrateur.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-229">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="7bb0b-230">Vous disposez des autorisations nécessaires pour gérer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-230">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="7bb0b-231">Exécutez les tâches administratives requises.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-231">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="7bb0b-232">Déconnectez-vous du compte Administrateur.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-232">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="7bb0b-233">Revenez à la page de Microsoft teams en sélectionnant l’icône du compte d’utilisateur dans la partie gauche de l’écran, puis sélectionnez **Skype**.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-233">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="7bb0b-234">Si l’utilisateur **Skype** n’est pas répertorié, vous devrez peut-être sélectionner **autre utilisateur** et entrer **.\skype** comme nom d’utilisateur et vous connecter.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-234">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="7bb0b-235">La console est à présent en mode de fonctionnement normal. Pour utiliser la procédure suivante, vous devez joindre un clavier à l’appareil s’il n’y a pas encore de pièce jointe.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-235">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="7bb0b-236">Basculement en mode administrateur et retour lorsque l’application Microsoft teams se bloque</span><span class="sxs-lookup"><span data-stu-id="7bb0b-236">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="7bb0b-237">Appuyez rapidement cinq fois sur la touche Windows.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-237">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="7bb0b-238">L’écran de connexion de Windows apparaît.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-238">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="7bb0b-239">Connectez-vous au bureau avec vos informations d’identification administrateur.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-239">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7bb0b-240">Cette méthode n’entraîne pas la connexion de l’utilisateur Skype ou l’arrêt normal de l’application, mais vous pouvez l’utiliser si l’application ne répond pas et que l’autre méthode n’a pas été disponible.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-240">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="7bb0b-241">Exécutez les tâches administratives requises.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-241">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="7bb0b-242">Lorsque vous avez terminé, redémarrez l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-242">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="7bb0b-243">La console redémarre en mode de fonctionnement normal et exécute l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-243">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="7bb0b-244">Vous pouvez supprimer le clavier, s’il est attaché pour vous permettre d’effectuer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-244">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="7bb0b-245">Astuces de dépannage</span><span class="sxs-lookup"><span data-stu-id="7bb0b-245">Troubleshooting tips</span></span>
   <span data-ttu-id="7bb0b-246"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="7bb0b-246"></span></span>

- <span data-ttu-id="7bb0b-247">Les invitations aux réunions risquent de ne pas apparaître lors de leur envoi dans les limites du domaine (par exemple, entre deux sociétés).</span><span class="sxs-lookup"><span data-stu-id="7bb0b-247">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="7bb0b-248">Dans ces cas, l’administrateur informatique doit décider d’autoriser ou non les utilisateurs externes à planifier une réunion.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-248">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="7bb0b-249">Les salles de Microsoft Teams ne prennent pas en charge la découverte automatique Exchange redirectionne via Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-249">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="7bb0b-250">En règle générale, il est conseillé aux administrateurs informatiques de désactiver les points de terminaison audio qu’il n’est pas prévu d’utiliser.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-250">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="7bb0b-251">Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-251">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="7bb0b-252">La perte de l’accès à l’écran tactile de la console est connue.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-252">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="7bb0b-253">Dans ce cas, le problème peut être résolu en redémarrant le système de salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-253">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="7bb0b-254">La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-254">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="7bb0b-255">Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.</span><span class="sxs-lookup"><span data-stu-id="7bb0b-255">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
