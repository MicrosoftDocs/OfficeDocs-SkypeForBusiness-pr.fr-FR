---
title: Opérations et gestion des salles d’équipes Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Lisez cette rubrique pour en savoir plus sur la gestion des salles d’équipes Microsoft, la nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: efaf2a1bae7980855501b826d6a2ee902f0f56b2
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362789"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="eb57a-103">Opérations et gestion des salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="eb57a-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="eb57a-104">Lisez cette rubrique pour en savoir plus sur la gestion des salles d’équipes Microsoft, la nouvelle génération de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="eb57a-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="eb57a-105">Salles d’équipes Microsoft est conçue pour transformer la salle de réunion en une expérience riche et collaborative la solution conférence le plus récent de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb57a-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="eb57a-106">Les utilisateurs bénéficiera de son Teams Microsoft familière ou Skype pour l’interface de l’entreprise et les administrateurs informatiques apprécierez une application Windows 10 Skype réunion facilement déployée et gérée.</span><span class="sxs-lookup"><span data-stu-id="eb57a-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="eb57a-107">Salles d’équipes Microsoft est conçu pour tirer parti de l’équipement existant comme panneaux LCD pour faciliter d’installation pour intégrer des Teams Microsoft ou Skype pour les entreprises à la salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="eb57a-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="eb57a-108">Avec une configuration supplémentaire, la gestion à distance est possible à l’aide de Microsoft Azure Monitor comme décrit dans la [gestion de planification Microsoft équipes salles avec Azure moniteur](azure-monitor-plan.md), [gestion de déployer Microsoft équipes salles avec Azure moniteur](azure-monitor-deploy.md), [gérer Périphériques de salles d’équipes Microsoft Azure moniteur](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="eb57a-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="eb57a-109">Vous pouvez également [Gérer les salles d’équipes Microsoft paramètres à distance avec un fichier XML de configuration de la console](xml-config-file.md), qui inclut l’application d’un thème d’affichage personnalisé.</span><span class="sxs-lookup"><span data-stu-id="eb57a-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="eb57a-110">Collecte de journaux sur salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="eb57a-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="eb57a-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-111"></span></span>

<span data-ttu-id="eb57a-112">Pour collecter des journaux, vous devez appeler le script de collection de journal est fourni avec l’application Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="eb57a-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="eb57a-113">En mode d’administration, démarrez une invite de commandes avec élévation de privilèges et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb57a-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="eb57a-114">Les journaux seront sortie dans un fichier ZIP c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="eb57a-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="eb57a-115">Paramètres de l’écran d’affichage</span><span class="sxs-lookup"><span data-stu-id="eb57a-115">Front of Room Display Settings</span></span>
<span data-ttu-id="eb57a-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-116"></span></span>

<span data-ttu-id="eb57a-117">Configurez l’écran d’affichage en mode étendu.</span><span class="sxs-lookup"><span data-stu-id="eb57a-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="eb57a-118">Cela permet de garantir que la console de que l’interface utilisateur n’est pas dupliquée sur qui s’affichent lorsque vous interrompre l’alimentation de l’affichage.</span><span class="sxs-lookup"><span data-stu-id="eb57a-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb57a-119">Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille.</span><span class="sxs-lookup"><span data-stu-id="eb57a-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="eb57a-120">Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs.</span><span class="sxs-lookup"><span data-stu-id="eb57a-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="eb57a-121">Les équipes Microsoft salles réinitialisation (restaurer usine)</span><span class="sxs-lookup"><span data-stu-id="eb57a-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="eb57a-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-122"></span></span>

<span data-ttu-id="eb57a-123">Si les salles d’équipes Microsoft ne fonctionne pas correctement, effectuer une réinitialisation peut-être vous aider.</span><span class="sxs-lookup"><span data-stu-id="eb57a-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="eb57a-124">Cela peut s’effectuer dans l’application des paramètres sous l’onglet **récupération** sous **Réinitialiser ce PC**, sélectionnez **Démarrer**, puis **supprimez tout le contenu**.</span><span class="sxs-lookup"><span data-stu-id="eb57a-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="eb57a-125">Suivez les invites restantes pour réinitialiser le périphérique.</span><span class="sxs-lookup"><span data-stu-id="eb57a-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb57a-126">Il existe un problème connu où les salles d’équipes Microsoft peut devenir inutilisables si l’option **Conserver mes fichiers - supprime les applications et les paramètres, mais conserve vos fichiers personnels** est sélectionnée au cours du processus de réinitialiser Windows.</span><span class="sxs-lookup"><span data-stu-id="eb57a-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="eb57a-127">Effectuez _pas_ utiliser cette option.</span><span class="sxs-lookup"><span data-stu-id="eb57a-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="eb57a-128">Options distantes prises en charge</span><span class="sxs-lookup"><span data-stu-id="eb57a-128">Supported Remote Options</span></span>
<span data-ttu-id="eb57a-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-129"></span></span>

<span data-ttu-id="eb57a-130">Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.</span><span class="sxs-lookup"><span data-stu-id="eb57a-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="eb57a-131">\*\*Groupe de travail \*\*</span><span class="sxs-lookup"><span data-stu-id="eb57a-131">**Workgroup**</span></span>|<span data-ttu-id="eb57a-132">**Aucun domaine joint**</span><span class="sxs-lookup"><span data-stu-id="eb57a-132">**Not domain joined**</span></span>|<span data-ttu-id="eb57a-133">**Domaine joint**</span><span class="sxs-lookup"><span data-stu-id="eb57a-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb57a-134">Redémarrer</span><span class="sxs-lookup"><span data-stu-id="eb57a-134">Restart</span></span>  <br/> |<span data-ttu-id="eb57a-135">Bureau distant</span><span class="sxs-lookup"><span data-stu-id="eb57a-135">Remote desktop</span></span>  <br/> <span data-ttu-id="eb57a-136">Powershell distant</span><span class="sxs-lookup"><span data-stu-id="eb57a-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="eb57a-137">Bureau à distance (nécessite une configuration supplémentaire)</span><span class="sxs-lookup"><span data-stu-id="eb57a-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="eb57a-138">Powershell distant (nécessite une configuration supplémentaire)</span><span class="sxs-lookup"><span data-stu-id="eb57a-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="eb57a-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="eb57a-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="eb57a-140">Mise à jour du SE</span><span class="sxs-lookup"><span data-stu-id="eb57a-140">Update OS</span></span>  <br/> |<span data-ttu-id="eb57a-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="eb57a-141">Windows Update</span></span>  <br/> |<span data-ttu-id="eb57a-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="eb57a-142">Windows Update</span></span>  <br/> <span data-ttu-id="eb57a-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="eb57a-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="eb57a-144">Mise à jour de l';application</span><span class="sxs-lookup"><span data-stu-id="eb57a-144">App update</span></span>  <br/> |<span data-ttu-id="eb57a-145">	Windows Store</span><span class="sxs-lookup"><span data-stu-id="eb57a-145">Windows Store</span></span>  <br/> |<span data-ttu-id="eb57a-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="eb57a-146">Windows Store</span></span>  <br/> <span data-ttu-id="eb57a-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="eb57a-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="eb57a-148">Configuration du compte Skype</span><span class="sxs-lookup"><span data-stu-id="eb57a-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="eb57a-149">Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="eb57a-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="eb57a-150">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="eb57a-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="eb57a-151">Accès aux journaux</span><span class="sxs-lookup"><span data-stu-id="eb57a-151">Access logs</span></span>  <br/> |<span data-ttu-id="eb57a-152">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="eb57a-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="eb57a-153">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="eb57a-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="eb57a-154">Configuration de la stratégie de groupe pour les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="eb57a-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="eb57a-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-155"></span></span>

<span data-ttu-id="eb57a-156">Cette section traite des paramètres système qui dépend de salles d’équipes Microsoft fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="eb57a-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="eb57a-157">Pour prendre part à des salles d’équipes Microsoft à un domaine, assurez-vous que votre stratégie de groupe ne remplace pas les paramètres dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="eb57a-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="eb57a-158">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="eb57a-158">**Setting**</span></span>|<span data-ttu-id="eb57a-159">**Permet de**</span><span class="sxs-lookup"><span data-stu-id="eb57a-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eb57a-160">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="eb57a-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="eb57a-161">Permet de salles d’équipes Microsoft amorçage</span><span class="sxs-lookup"><span data-stu-id="eb57a-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="eb57a-162">Gestion - de l’alimentation\> sur CA, désactiver écran au bout de 10 minutes</span><span class="sxs-lookup"><span data-stu-id="eb57a-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="eb57a-163">Gestion - de l’alimentation\> sur CA, placez jamais système en mode veille</span><span class="sxs-lookup"><span data-stu-id="eb57a-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="eb57a-164">Permet de salles d’équipes Microsoft activer affiche attaché et réactiver automatiquement</span><span class="sxs-lookup"><span data-stu-id="eb57a-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="eb57a-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="eb57a-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="eb57a-166">Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local.</span><span class="sxs-lookup"><span data-stu-id="eb57a-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="eb57a-167">Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="eb57a-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="eb57a-168">Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.</span><span class="sxs-lookup"><span data-stu-id="eb57a-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="eb57a-169">Active le compte Skype avec lequel toujours se connecter</span><span class="sxs-lookup"><span data-stu-id="eb57a-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="eb57a-170">Transfert de fichiers à l’aide de stratégies de groupe est traitée dans [un élément de fichier de configuration](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb57a-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="eb57a-171">Gestion distante à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb57a-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="eb57a-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-172"></span></span>

<span data-ttu-id="eb57a-173">Vous pouvez effectuer les opérations suivantes de gestion à distance à l’aide de PowerShell (voir le tableau ci-dessous pour les exemples de script) :</span><span class="sxs-lookup"><span data-stu-id="eb57a-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="eb57a-174">Obtenir les périphériques raccordés</span><span class="sxs-lookup"><span data-stu-id="eb57a-174">Get attached devices</span></span>
    
- <span data-ttu-id="eb57a-175">Obtenir l';état de l';application</span><span class="sxs-lookup"><span data-stu-id="eb57a-175">Get app status</span></span>
    
- <span data-ttu-id="eb57a-176">Obtenir les informations système</span><span class="sxs-lookup"><span data-stu-id="eb57a-176">Get system info</span></span>
    
- <span data-ttu-id="eb57a-177">Redémarrer le système</span><span class="sxs-lookup"><span data-stu-id="eb57a-177">Reboot system</span></span>
    
- <span data-ttu-id="eb57a-178">Récupérer les journaux</span><span class="sxs-lookup"><span data-stu-id="eb57a-178">Retrieve logs</span></span>
    
- <span data-ttu-id="eb57a-179">Transférer des fichiers (requiert un salles d’équipes Microsoft à un domaine)</span><span class="sxs-lookup"><span data-stu-id="eb57a-179">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb57a-180">Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="eb57a-180">This functionality is off by default.</span></span> <span data-ttu-id="eb57a-181">Vous devez activer PowerShell à distance pour votre environnement sur le système de salles d’équipes Microsoft effectuer les opérations ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="eb57a-181">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="eb57a-182">Reportez-vous à la documentation sur **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** pour plus d’informations sur l’activation de PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="eb57a-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="eb57a-183">Par exemple, vous pouvez activer PowerShell à distance comme suit :</span><span class="sxs-lookup"><span data-stu-id="eb57a-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="eb57a-184">Connectez-vous en tant qu’administrateur sur un appareil Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="eb57a-184">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="eb57a-185">Ouvrez une invite de commandes PowerShell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="eb57a-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="eb57a-186">Entrez la commande suivante : Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="eb57a-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="eb57a-187">Pour effectuer une opération de gestion :</span><span class="sxs-lookup"><span data-stu-id="eb57a-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="eb57a-188">Connectez-vous à un ordinateur avec les informations d’identification de compte qui est autorisé à exécuter des commandes PowerShell sur un appareil Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="eb57a-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="eb57a-189">Ouvrez une invite de commandes PowerShell régulière sur le PC.</span><span class="sxs-lookup"><span data-stu-id="eb57a-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="eb57a-190">Copiez le texte de commande à partir du tableau ci-après et collez-le à l’invite.</span><span class="sxs-lookup"><span data-stu-id="eb57a-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="eb57a-191">Remplacez `<Device fqdn>` champs dont les valeurs de nom de domaine complet approprié à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="eb57a-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="eb57a-192">Remplacez \* \<chemin d’accès\> \* avec le nom de fichier et chemin d’accès local du fichier de configuration maître SkypeSettings.xml (ou image de thème).</span><span class="sxs-lookup"><span data-stu-id="eb57a-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="eb57a-193">Pour obtenir des équipements</span><span class="sxs-lookup"><span data-stu-id="eb57a-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="eb57a-194">Obtenir l’état de l’application</span><span class="sxs-lookup"><span data-stu-id="eb57a-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="eb57a-195">Obtenir les informations système</span><span class="sxs-lookup"><span data-stu-id="eb57a-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="eb57a-196">Redémarrer le système</span><span class="sxs-lookup"><span data-stu-id="eb57a-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="eb57a-197">Récupérer les journaux</span><span class="sxs-lookup"><span data-stu-id="eb57a-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="eb57a-198">Distribuer un fichier de configuration XML (ou les graphismes)</span><span class="sxs-lookup"><span data-stu-id="eb57a-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="eb57a-199">Mises à jour logicielles</span><span class="sxs-lookup"><span data-stu-id="eb57a-199">Software updates</span></span>
<span data-ttu-id="eb57a-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-200"></span></span>

<span data-ttu-id="eb57a-201">Par défaut, salles d’équipes Microsoft essaie de se connecter à la banque de Windows pour obtenir la dernière version du logiciel Microsoft équipes salles, afin que le périphérique devra être régulière accès à internet.</span><span class="sxs-lookup"><span data-stu-id="eb57a-201">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="eb57a-202">Avant de contacter Microsoft ayant des problèmes de prise en charge, assurez-vous que le périphérique Microsoft équipes salles est chargé avec la dernière version de l’application.</span><span class="sxs-lookup"><span data-stu-id="eb57a-202">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="eb57a-203">Par défaut, les salles d’équipes Microsoft se connecte à Windows Update pour récupérer le système d’exploitation et les mises à jour de microprogramme de périphérique USB et les installe en dehors des heures ouvrées configurés.</span><span class="sxs-lookup"><span data-stu-id="eb57a-203">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="eb57a-204">Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="eb57a-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="eb57a-205">Si vous souhaitez gérer manuellement les mises à jour et que vous ne parvenez pas à la procédure normale pour le [Magasin de Microsoft pour les entreprises](https://businessstore.microsoft.com/store) à [distribuer des applications en mode hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), vous pouvez vous procurer le fichier APPX approprié et les dépendances dans le [kit de déploiement](https://go.microsoft.com/fwlink/?linkid=851168) (à partir de les instructions pour [configurer une console Microsoft équipes salles](console.md)) qui peut être utilisé avec SCCM.</span><span class="sxs-lookup"><span data-stu-id="eb57a-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="eb57a-206">La version de kit de déploiement retard sur la version de la banque, afin qu’il correspondent ne peut-être pas toujours à la dernière version disponible.</span><span class="sxs-lookup"><span data-stu-id="eb57a-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="eb57a-207">Pour mettre à jour à l’aide de Powershell</span><span class="sxs-lookup"><span data-stu-id="eb57a-207">To update using Powershell</span></span>

1. <span data-ttu-id="eb57a-208">Extraire le package de l’installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) sur un partage de l’appareil peut accéder.</span><span class="sxs-lookup"><span data-stu-id="eb57a-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="eb57a-209">Exécutez le script suivant ciblant les périphériques salles des équipes Microsoft, la modification \<partager\> au périphérique partager le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="eb57a-209">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="eb57a-210">Mode Administrateur et gestion des appareils</span><span class="sxs-lookup"><span data-stu-id="eb57a-210">Admin mode and device management</span></span>
<span data-ttu-id="eb57a-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-211"></span></span>

<span data-ttu-id="eb57a-212">Certaines fonctions de gestion, comme l’installation manuelle d’un certificat d’autorité de certification privé, nécessitent plaçant le périphérique Surface Pro en mode Admin.</span><span class="sxs-lookup"><span data-stu-id="eb57a-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="eb57a-213">Passer en Admin Mode et lorsque l’application Microsoft équipes salles est en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="eb57a-213">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="eb57a-214">Raccrocher tous les appels en cours et revenir à l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="eb57a-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="eb57a-215">Sélectionnez l’icône d’engrenage et afficher le menu (options sont **les paramètres**, **accessibilité**et **Redémarrez le dispositif** ).</span><span class="sxs-lookup"><span data-stu-id="eb57a-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="eb57a-216">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="eb57a-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="eb57a-217">Entrez le mot de passe de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="eb57a-217">Enter the Administrator Password.</span></span> <span data-ttu-id="eb57a-218">L’écran d’installation s’affiche.</span><span class="sxs-lookup"><span data-stu-id="eb57a-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb57a-219">Si le périphérique n’est pas joint au domaine, le compte d’administrateur local (nom d’utilisateur « Admin ») sera utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="eb57a-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="eb57a-220">Le mot de passe par défaut de ce compte est "sfb", mais il est recommandé que votre organisation le change dès que possible pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="eb57a-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="eb57a-221">Si l’ordinateur est joint au domaine, vous pouvez vous connecter avec un compte de domaine correctement privilégié.</span><span class="sxs-lookup"><span data-stu-id="eb57a-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="eb57a-222">Dans la colonne de gauche, sélectionnez **Paramètres Windows** .</span><span class="sxs-lookup"><span data-stu-id="eb57a-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="eb57a-223">Sélectionnez **Atteindre connexion d’administration**.</span><span class="sxs-lookup"><span data-stu-id="eb57a-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="eb57a-224">Entrez le mot de passe de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="eb57a-224">Enter the Administrator Password.</span></span> <span data-ttu-id="eb57a-225">Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows.</span><span class="sxs-lookup"><span data-stu-id="eb57a-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="eb57a-226">Connectez-vous au bureau avec vos informations d’identification administrateur.</span><span class="sxs-lookup"><span data-stu-id="eb57a-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="eb57a-227">Vous devez les privilèges nécessaires pour gérer le périphérique.</span><span class="sxs-lookup"><span data-stu-id="eb57a-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="eb57a-228">Exécutez les tâches administratives requises.</span><span class="sxs-lookup"><span data-stu-id="eb57a-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="eb57a-229">Déconnectez-vous du compte Administrateur.</span><span class="sxs-lookup"><span data-stu-id="eb57a-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="eb57a-230">Revenez à Microsoft équipes salles en sélectionnant l’icône de compte d’utilisateur sur le côté gauche de l’écran, puis **Skype**.</span><span class="sxs-lookup"><span data-stu-id="eb57a-230">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="eb57a-231">Si l’utilisateur **Skype** n’est pas répertorié, vous devrez peut-être sélectionnez **autre utilisateur** , puis entrez **. \skype** comme nom d’utilisateur et de connexion.</span><span class="sxs-lookup"><span data-stu-id="eb57a-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="eb57a-232">La console est désormais dans son mode de fonctionnement normal. La procédure suivante nécessite que vous attacher un clavier à l’appareil si une n’est pas déjà attachée.</span><span class="sxs-lookup"><span data-stu-id="eb57a-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="eb57a-233">Passer en Admin Mode et lorsque l’application Microsoft équipes salles se bloque</span><span class="sxs-lookup"><span data-stu-id="eb57a-233">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="eb57a-234">Appuyez rapidement cinq fois sur la touche Windows.</span><span class="sxs-lookup"><span data-stu-id="eb57a-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="eb57a-235">L’écran de connexion de Windows apparaît.</span><span class="sxs-lookup"><span data-stu-id="eb57a-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="eb57a-236">Connectez-vous au bureau avec vos informations d’identification administrateur.</span><span class="sxs-lookup"><span data-stu-id="eb57a-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb57a-237">Cette méthode ne déconnecter l’utilisateur Skype ou terminer correctement l’application, mais vous pouvez l’utiliser si l’application n’a pas été répond et l’autre méthode n’était pas disponible.</span><span class="sxs-lookup"><span data-stu-id="eb57a-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="eb57a-238">Exécutez les tâches administratives requises.</span><span class="sxs-lookup"><span data-stu-id="eb57a-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="eb57a-239">Redémarrez l’ordinateur lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="eb57a-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="eb57a-240">Redémarrage de la console dans son mode de fonctionnement normal, l’application de salles d’équipes Microsoft en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="eb57a-240">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="eb57a-241">Vous pouvez supprimer le clavier, si elle a été attachée afin que vous puissiez effectuer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="eb57a-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="eb57a-242">Astuces de dépannage</span><span class="sxs-lookup"><span data-stu-id="eb57a-242">Troubleshooting tips</span></span>
   <span data-ttu-id="eb57a-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="eb57a-243"></span></span>

- <span data-ttu-id="eb57a-244">Les invitations aux réunions peut ne pas apparaîtront lors de l’envoi au-delà des frontières du domaine (par exemple, entre les deux sociétés).</span><span class="sxs-lookup"><span data-stu-id="eb57a-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="eb57a-245">Dans ce cas, les administrateurs informatiques doivent décider s’il faut autoriser les utilisateurs externes organiser une réunion.</span><span class="sxs-lookup"><span data-stu-id="eb57a-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="eb57a-246">Salles d’équipes Microsoft ne prend pas en charge la découverte automatique Exchange redirige via Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="eb57a-246">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="eb57a-247">En règle générale, il est recommandé pour les administrateurs informatiques désactiver les points de terminaison audio que n’envisagez pas d’utiliser.</span><span class="sxs-lookup"><span data-stu-id="eb57a-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="eb57a-248">Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.</span><span class="sxs-lookup"><span data-stu-id="eb57a-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="eb57a-249">La perte de l’accès à l’écran tactile de la console est connue.</span><span class="sxs-lookup"><span data-stu-id="eb57a-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="eb57a-250">Dans ce cas, le problème est parfois résolu en redémarrant le système de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb57a-250">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="eb57a-251">La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue.</span><span class="sxs-lookup"><span data-stu-id="eb57a-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="eb57a-252">Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.</span><span class="sxs-lookup"><span data-stu-id="eb57a-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
