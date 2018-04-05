---
title: Gestion de Skype Room System v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Lisez cette rubrique pour en savoir plus sur la gestion des systèmes de salle Skype v2, la nouvelle génération de systèmes de salle de Skype.
ms.openlocfilehash: 562dbeea19fb732caf9348e2bfd632da3579e71a
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="manage-skype-room-systems-v2"></a><span data-ttu-id="4ea14-103">Gestion de Skype Room System v2</span><span class="sxs-lookup"><span data-stu-id="4ea14-103">Manage Skype Room Systems v2</span></span>
 
<span data-ttu-id="4ea14-104">Lisez cette rubrique pour en savoir plus sur la gestion des systèmes de salle Skype v2, la nouvelle génération de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ea14-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="4ea14-105">Systèmes de salle Skype v2 est la dernière solution de conférence de Microsoft conçue pour transformer votre salle de réunion un Skype riche et de collaboration pour une expérience.</span><span class="sxs-lookup"><span data-stu-id="4ea14-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="4ea14-106">Les utilisateurs apprécieront son interface Skype Entreprise familière, et les administrateurs informatiques approuveront la facilité de déploiement et de gestion de l’application de réunion Skype sous Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4ea14-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="4ea14-107">Systèmes de salle Skype v2 est conçu pour tirer parti des équipements existants tels que des panneaux LCD pour faciliter d’installation pour mettre Skype pour entreprise dans votre salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="4ea14-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="4ea14-108">Une configuration supplémentaire, l’administration à distance est possible à l’aide de Microsoft Operations Management Suite (OMS) comme décrit dans le [Plan Skype salle v2 SMS avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [déployer Skype salle v2 SMS avec OMS](../../deploy/deploy-clients/with-oms.md)et [gérer Les périphériques systèmes de salle Skype v2 avec OMS](oms.md).</span><span class="sxs-lookup"><span data-stu-id="4ea14-108">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](oms.md).</span></span> <span data-ttu-id="4ea14-109">Vous pouvez également [un v2 Skype salle de systèmes de gérer les paramètres de console à distance avec un fichier de configuration XML](xml-config-file.md), qui inclut l’application d’un thème d’affichage personnalisé.</span><span class="sxs-lookup"><span data-stu-id="4ea14-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="4ea14-110">Collecte de journaux sur Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="4ea14-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="4ea14-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-111"></span></span>

<span data-ttu-id="4ea14-112">Pour collecter des journaux, vous devez appeler le script de collection de journal qui est fourni avec l’application v2 de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ea14-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="4ea14-113">En mode administrateur, démarrez une invite de commandes avec élévation de privilèges et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4ea14-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="4ea14-114">Les journaux seront générés sous la forme d’un fichier ZIP dans c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="4ea14-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="4ea14-115">Paramètres de l’écran d’affichage</span><span class="sxs-lookup"><span data-stu-id="4ea14-115">Front of Room Display Settings</span></span>
<span data-ttu-id="4ea14-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-116"></span></span>

<span data-ttu-id="4ea14-117">Configurez l’écran d’affichage en mode étendu.</span><span class="sxs-lookup"><span data-stu-id="4ea14-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="4ea14-118">Vous vous assurez ainsi que l’interface utilisateur de la console n’est pas dupliquée sur cet affichage lors de la mise sous tension de l’affichage.</span><span class="sxs-lookup"><span data-stu-id="4ea14-118">Doing so will ensure that the console UI is not duplicated on that display when power cycling the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ea14-119">Un poste de télévision utilisé comme frontal de salle d’affichage pour la prise en charge/activer la fonctionnalité de contrôle des appareils électroniques grand public (CEC) de HDMI afin qu’il peut basculer automatiquement vers une source vidéo active du mode veille.</span><span class="sxs-lookup"><span data-stu-id="4ea14-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="4ea14-120">Cette fonctionnalité n’est pas pris en charge sur tous les téléviseurs.</span><span class="sxs-lookup"><span data-stu-id="4ea14-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="4ea14-121">Réinitialisation de Skype Room Systems v2 (Restaurer les paramètres d’usine)</span><span class="sxs-lookup"><span data-stu-id="4ea14-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="4ea14-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-122"></span></span>

<span data-ttu-id="4ea14-123">Si v2 de systèmes de salle Skype ne fonctionne pas bien, peut aider à effectuer une réinitialisation de l’usine.</span><span class="sxs-lookup"><span data-stu-id="4ea14-123">If Skype Room Systems v2 isn't running well, performing a factory reset may help.</span></span> <span data-ttu-id="4ea14-124">Pour ce faire dans l’application à partir de l’onglet « Récupération » sous l’en-tête « Réinitialiser ce PC », sélectionnez « Démarrer » suivi de « Supprimer tout ».</span><span class="sxs-lookup"><span data-stu-id="4ea14-124">This can be done in the Settings app from the "Recovery" tab. Beneath the "Reset this PC" header, select "Get started" followed by "Remove everything."</span></span> <span data-ttu-id="4ea14-125">Suivez les autres invites selon votre choix pour réinitialiser le périphérique.</span><span class="sxs-lookup"><span data-stu-id="4ea14-125">Follow the remaining prompts as desired to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ea14-126">Il existe un problème connu où le v2 Skype salle systèmes peuvent devenir inutilisables si l’option « Conserver mes fichiers - supprime les applications et les paramètres, mais conserve vos fichiers personnels » est sélectionnée au cours du processus de réinitialisation de Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea14-126">There is a known issue where the Skype Room Systems v2 can become unusable if the "Keep my files - Removes Apps and settings, but keeps your personal files" option is selected during the Windows Reset process.</span></span> <span data-ttu-id="4ea14-127">**N';utilisez pas** cette option.</span><span class="sxs-lookup"><span data-stu-id="4ea14-127">**Do not** use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="4ea14-128">Options distantes prises en charge</span><span class="sxs-lookup"><span data-stu-id="4ea14-128">Supported Remote Options</span></span>
<span data-ttu-id="4ea14-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-129"></span></span>

<span data-ttu-id="4ea14-130">Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.</span><span class="sxs-lookup"><span data-stu-id="4ea14-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="4ea14-131">**Groupe de travail**</span><span class="sxs-lookup"><span data-stu-id="4ea14-131">**Workgroup**</span></span>|<span data-ttu-id="4ea14-132">**Joint pas au domaine**</span><span class="sxs-lookup"><span data-stu-id="4ea14-132">**Not domain joined**</span></span>|<span data-ttu-id="4ea14-133">**Joint au domaine**</span><span class="sxs-lookup"><span data-stu-id="4ea14-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ea14-134">Redémarrer</span><span class="sxs-lookup"><span data-stu-id="4ea14-134">Restart</span></span>  <br/> |<span data-ttu-id="4ea14-135">Bureau distant</span><span class="sxs-lookup"><span data-stu-id="4ea14-135">Remote desktop</span></span>  <br/> <span data-ttu-id="4ea14-136">Powershell distant</span><span class="sxs-lookup"><span data-stu-id="4ea14-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="4ea14-137">Bureau à distance (nécessite une configuration supplémentaire)</span><span class="sxs-lookup"><span data-stu-id="4ea14-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="4ea14-138">Powershell distant (nécessite une configuration supplémentaire)</span><span class="sxs-lookup"><span data-stu-id="4ea14-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="4ea14-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="4ea14-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="4ea14-140">Mise à jour du SE</span><span class="sxs-lookup"><span data-stu-id="4ea14-140">Update OS</span></span>  <br/> |<span data-ttu-id="4ea14-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4ea14-141">Windows Update</span></span>  <br/> |<span data-ttu-id="4ea14-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4ea14-142">Windows Update</span></span>  <br/> <span data-ttu-id="4ea14-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="4ea14-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="4ea14-144">Mise à jour de l';application</span><span class="sxs-lookup"><span data-stu-id="4ea14-144">App update</span></span>  <br/> |<span data-ttu-id="4ea14-145">	Windows Store</span><span class="sxs-lookup"><span data-stu-id="4ea14-145">Windows Store</span></span>  <br/> |<span data-ttu-id="4ea14-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="4ea14-146">Windows Store</span></span>  <br/> <span data-ttu-id="4ea14-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="4ea14-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="4ea14-148">Configuration du compte Skype</span><span class="sxs-lookup"><span data-stu-id="4ea14-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="4ea14-149">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="4ea14-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="4ea14-150">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="4ea14-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="4ea14-151">Accès aux journaux</span><span class="sxs-lookup"><span data-stu-id="4ea14-151">Access logs</span></span>  <br/> |<span data-ttu-id="4ea14-152">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="4ea14-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="4ea14-153">	Actuellement pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="4ea14-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="4ea14-154">Configuration de la stratégie de groupe pour Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="4ea14-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="4ea14-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-155"></span></span>

<span data-ttu-id="4ea14-156">Cette section traite des paramètres système qui dépend des systèmes de salle Skype v2 pour fonctionner correctement.</span><span class="sxs-lookup"><span data-stu-id="4ea14-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="4ea14-157">Lorsque vous intégrez des systèmes de salle Skype v2 à un domaine, veuillez vous assurer que votre stratégie de groupe ne remplace pas les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="4ea14-157">When joining Skype Room Systems v2 to a domain, please ensure that your group policy does not override the following settings:</span></span>
  

|<span data-ttu-id="4ea14-158">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="4ea14-158">**Setting**</span></span>|<span data-ttu-id="4ea14-159">**Permet de**</span><span class="sxs-lookup"><span data-stu-id="4ea14-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ea14-160">	HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="4ea14-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="4ea14-161">V2 de systèmes de salle Skype permet de démarrer</span><span class="sxs-lookup"><span data-stu-id="4ea14-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="4ea14-162">Gestion - de l’alimentation\> sur CA, désactiver écran après 10 minutes</span><span class="sxs-lookup"><span data-stu-id="4ea14-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="4ea14-163">Gestion - de l’alimentation\> sur CA, ne placez jamais de mise en veille du système</span><span class="sxs-lookup"><span data-stu-id="4ea14-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="4ea14-164">Permet de v2 de systèmes de salle Skype activer joint affiche et mode veille automatiquement</span><span class="sxs-lookup"><span data-stu-id="4ea14-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="4ea14-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="4ea14-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="4ea14-166">Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local.</span><span class="sxs-lookup"><span data-stu-id="4ea14-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="4ea14-167">Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="4ea14-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="4ea14-168">Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.</span><span class="sxs-lookup"><span data-stu-id="4ea14-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="4ea14-169">Active le compte Skype avec lequel toujours se connecter</span><span class="sxs-lookup"><span data-stu-id="4ea14-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="4ea14-170">Transfert de fichiers à l’aide de stratégies de groupe est traité dans [un élément de fichier de configuration](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4ea14-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="4ea14-171">Gestion distante à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea14-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="4ea14-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-172"></span></span>

<span data-ttu-id="4ea14-173">Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (consultez le tableau ci-dessous pour des exemples de script) :</span><span class="sxs-lookup"><span data-stu-id="4ea14-173">You can perform the following management operations remotely using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="4ea14-174">Obtenir les périphériques raccordés</span><span class="sxs-lookup"><span data-stu-id="4ea14-174">Get attached devices</span></span>
    
- <span data-ttu-id="4ea14-175">Obtenir l';état de l';application</span><span class="sxs-lookup"><span data-stu-id="4ea14-175">Get app status</span></span>
    
- <span data-ttu-id="4ea14-176">Obtenir les informations système</span><span class="sxs-lookup"><span data-stu-id="4ea14-176">Get system info</span></span>
    
- <span data-ttu-id="4ea14-177">Redémarrer le système</span><span class="sxs-lookup"><span data-stu-id="4ea14-177">Reboot system</span></span>
    
- <span data-ttu-id="4ea14-178">Récupérer les journaux</span><span class="sxs-lookup"><span data-stu-id="4ea14-178">Retrieve logs</span></span>
    
- <span data-ttu-id="4ea14-179">Transfert de fichiers (nécessite un domaine rejoint Skype salle systèmes v2)</span><span class="sxs-lookup"><span data-stu-id="4ea14-179">Transfer files (requires a domain joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ea14-180">Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4ea14-180">This functionality is off by default.</span></span> <span data-ttu-id="4ea14-181">Vous devez activer PowerShell distant pour votre environnement sur le système v2 de systèmes de salle Skype effectuer les opérations ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4ea14-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="4ea14-182">Reportez-vous à la documentation sur **[Activer-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** pour plus d’informations sur l’activation du PowerShell distant.</span><span class="sxs-lookup"><span data-stu-id="4ea14-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** for information on how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="4ea14-183">Par exemple, vous pouvez activer PowerShell à distance comme suit :</span><span class="sxs-lookup"><span data-stu-id="4ea14-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="4ea14-184">Ouvrez une session en tant qu’administrateur sur un périphérique de v2 de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ea14-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="4ea14-185">Lancez une invite de commande PowerShell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="4ea14-185">Launch an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="4ea14-186">Entrez la commande suivante : Enable-PSRemoting - force</span><span class="sxs-lookup"><span data-stu-id="4ea14-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="4ea14-187">Pour effectuer une opération de gestion :</span><span class="sxs-lookup"><span data-stu-id="4ea14-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="4ea14-188">Vous connecter à un ordinateur avec des informations d’identification de compte qui ont l’autorisation d’exécuter des commandes PowerShell sur un périphérique de v2 de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ea14-188">Sign into a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="4ea14-189">Lancez une invite de commande PowerShell régulière sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4ea14-189">Launch a regular PowerShell command prompt on your PC.</span></span>
    
3. <span data-ttu-id="4ea14-190">Copiez le texte de commande du tableau ci-dessous et collez-le dans l’invite.</span><span class="sxs-lookup"><span data-stu-id="4ea14-190">Copy the command text from the table below and paste it into the prompt.</span></span>
    
4. <span data-ttu-id="4ea14-191">Remplacer `<Device fqdn>` champs avec les valeurs de nom de domaine complet approprié à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="4ea14-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="4ea14-192">Remplacer * \<chemin d’accès\> * avec le nom de fichier et le chemin d’accès local du fichier de configuration maître SkypeSettings.xml (ou image de thème).</span><span class="sxs-lookup"><span data-stu-id="4ea14-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="4ea14-193">Pour obtenir des équipements reliés</span><span class="sxs-lookup"><span data-stu-id="4ea14-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea14-194">Obtenir l’état de l’application</span><span class="sxs-lookup"><span data-stu-id="4ea14-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea14-195">Obtenir les informations système</span><span class="sxs-lookup"><span data-stu-id="4ea14-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea14-196">Redémarrer le système</span><span class="sxs-lookup"><span data-stu-id="4ea14-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea14-197">Récupérer les journaux</span><span class="sxs-lookup"><span data-stu-id="4ea14-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="4ea14-198">Pousser une configuration XML ou un graphique de thème)</span><span class="sxs-lookup"><span data-stu-id="4ea14-198">Push an XML configuration file or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="4ea14-199">Mises à jour logicielles</span><span class="sxs-lookup"><span data-stu-id="4ea14-199">Software updates</span></span>
<span data-ttu-id="4ea14-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-200"></span></span>

<span data-ttu-id="4ea14-201">Par défaut, systèmes de salle Skype v2 tentent de se connecter au magasin de Windows pour obtenir la dernière version de Skype salle v2 de logiciels de systèmes, afin que le périphérique nécessite un accès régulier à internet.</span><span class="sxs-lookup"><span data-stu-id="4ea14-201">By default, Skype Room Systems v2 will attempt to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="4ea14-202">Assurez-vous que le périphérique de v2 de systèmes de salle de Skype est chargé avec la version la plus récente de l’application, avant de contacter Microsoft avec les problèmes de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4ea14-202">Be sure the Skype Room Systems v2 device is loaded with the latest version of the app, before contacting Microsoft with support issues.</span></span>
  
<span data-ttu-id="4ea14-203">Par défaut, systèmes de salle Skype v2 se connectera mise à jour de Windows pour extraire du système d’exploitation, ainsi que du microprogramme de périphérique USB mises à jour et les installer en dehors des heures d’activité configurés.</span><span class="sxs-lookup"><span data-stu-id="4ea14-203">By default, Skype Room Systems v2 will connect to Windows Update to retrieve OS as well as USB peripheral firmware updates and install them outside of configured business hours.</span></span> <span data-ttu-id="4ea14-204">Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="4ea14-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="4ea14-205">Si vous souhaitez gérer manuellement les mises à jour et ne peuvent pas suivre la procédure normale pour la [Banque d’informations Microsoft pour les entreprises](https://businessstore.microsoft.com/en-us/store) à [distribuer des applications en mode hors connexion](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), vous pouvez acquérir les fichiers APPX et les dépendances à partir du [kit de déploiement](https://go.microsoft.com/fwlink/?linkid=851168) (à partir de les instructions pour [configurer une console v2 de systèmes de salle Skype](../../deploy/deploy-clients/console.md)) qui peut être utilisé avec SCCM.</span><span class="sxs-lookup"><span data-stu-id="4ea14-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) to [Distribute offline apps](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="4ea14-206">La version de kit de déploiement retard sur la version de la banque, donc il peut ne pas toujours correspond à la dernière version disponible.</span><span class="sxs-lookup"><span data-stu-id="4ea14-206">The deployment kit release lags behind the store release, so it may not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="4ea14-207">Mise à jour à l’aide de Powershell</span><span class="sxs-lookup"><span data-stu-id="4ea14-207">To update using Powershell</span></span>

1. <span data-ttu-id="4ea14-208">Extrayez le package de l’installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) sur un partage accessible du périphérique.</span><span class="sxs-lookup"><span data-stu-id="4ea14-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a device accessible share.</span></span>
    
2. <span data-ttu-id="4ea14-209">Exécutez le script suivant qui ciblent les périphériques systèmes de salle Skype v2, la modification \<partager\> sur le périphérique de partage le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="4ea14-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="4ea14-210">Mode Administrateur et gestion des appareils</span><span class="sxs-lookup"><span data-stu-id="4ea14-210">Admin mode and device management</span></span>
<span data-ttu-id="4ea14-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-211"></span></span>

<span data-ttu-id="4ea14-212">Certaines fonctions de gestion, comme l’installation manuelle d’un certificat privé de l’AC, nécessitent de basculer l’appareil Surface 4 en mode Administrateur. </span><span class="sxs-lookup"><span data-stu-id="4ea14-212">Some management functions, like manually installing a private CA certificate, require placing the Surface 4 device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="4ea14-213">Commutation en Admin Mode et lors de l’exécution de l’application v2 de systèmes de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="4ea14-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="4ea14-214">Raccrochez les appels en cours et revenez à l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="4ea14-214">Hang up any ongoing calls and return to the home screen.</span></span>
    
2. <span data-ttu-id="4ea14-215">Cliquez sur l’icône d’engrenage et afficher le menu (options sont des **paramètres**, **l’accessibilité**et **Redémarrer le périphérique** ).</span><span class="sxs-lookup"><span data-stu-id="4ea14-215">Click on the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="4ea14-216">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="4ea14-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="4ea14-217">Entrez le mot de passe de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4ea14-217">Enter the Administrator Password.</span></span> <span data-ttu-id="4ea14-218">L’écran d’installation s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4ea14-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ea14-p115">Si l’appareil ne possède pas de domaine joint, le compte administratif local (nom d’utilisateur "Admin") sera utilisé par défaut. Le mot de passe par défaut de ce compte est "sfb", mais il est recommandé que votre organisation le change dès que possible pour des raisons de sécurité. Si l’appareil possède un domaine joint, vous pouvez vous connecter avec un compte de domaine disposant des privilèges appropriés.</span><span class="sxs-lookup"><span data-stu-id="4ea14-p115">If the device is not domain joined, the local administrative account (username "Admin") will be used by default. The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible. If the machine is domain joined, you can sign in with an appropriately-privileged domain account.</span></span> 
  
5. <span data-ttu-id="4ea14-222">Cliquez sur **Paramètres Windows** dans la colonne de gauche.</span><span class="sxs-lookup"><span data-stu-id="4ea14-222">Click on **Windows Settings** on the left column.</span></span>
    
6. <span data-ttu-id="4ea14-223">Sélectionnez **Atteindre connexion d’administration**.</span><span class="sxs-lookup"><span data-stu-id="4ea14-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="4ea14-224">Entrez le mot de passe de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="4ea14-224">Enter the Administrator Password.</span></span> <span data-ttu-id="4ea14-225">Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea14-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="4ea14-p117">Connectez-vous au bureau avec vos informations d’identification administrateur. Vous disposez des privilèges requis pour gérer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="4ea14-p117">Log in to the desktop with your administrative credentials. You will have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="4ea14-228">Exécutez les tâches administratives requises.</span><span class="sxs-lookup"><span data-stu-id="4ea14-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="4ea14-229">Déconnectez-vous du compte Administrateur.</span><span class="sxs-lookup"><span data-stu-id="4ea14-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="4ea14-230">Revenir à v2 de systèmes de salle de Skype en cliquant sur l’icône de compte d’utilisateur à l’extrême gauche de l’écran et sélectionnez **Skype**.</span><span class="sxs-lookup"><span data-stu-id="4ea14-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left of the screen and select **Skype**.</span></span>
    
    <span data-ttu-id="4ea14-231">Si l’utilisateur **Skype** n’est pas répertorié, vous devrez sélectionner **l’autre utilisateur** , puis entrez **. \skype** comme nom d’utilisateur et de connexion.</span><span class="sxs-lookup"><span data-stu-id="4ea14-231">If the **Skype** user is not listed, you may have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
 <span data-ttu-id="4ea14-232">La console est maintenant dans son mode de fonctionnement normal. La procédure suivante nécessite que vous permet de connecter un clavier à l’appareil si une n’est pas déjà attachée.</span><span class="sxs-lookup"><span data-stu-id="4ea14-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="4ea14-233">Commutation en Admin Mode et lorsque l’application v2 Skype salle systèmes se bloque.</span><span class="sxs-lookup"><span data-stu-id="4ea14-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="4ea14-p118">Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît. </span><span class="sxs-lookup"><span data-stu-id="4ea14-p118">Press the Windows key five times in rapid succession. This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="4ea14-236">Connectez-vous au bureau avec vos informations d’identification administrateur.</span><span class="sxs-lookup"><span data-stu-id="4ea14-236">Log into the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ea14-237">Cette méthode ne déconnecte pas l’utilisateur de Skype ou ne ferme pas l’application. Vous ne devez toutefois l’utiliser que si l’application ne répond pas et que l’autre méthode n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="4ea14-237">This method does not log the Skype user off or gracefully terminate the app, but you would only use it if the app was not responding and the other method was not available.</span></span> 
  
3. <span data-ttu-id="4ea14-238">Exécutez les tâches administratives requises.</span><span class="sxs-lookup"><span data-stu-id="4ea14-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="4ea14-239">Redémarrez l’appareil lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="4ea14-239">Restart the machine when you are finished.</span></span>
    
 <span data-ttu-id="4ea14-240">Redémarrage de la console dans son mode de fonctionnement normal, l’application v2 de systèmes de salle de Skype en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="4ea14-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="4ea14-241">Vous pouvez retirer le clavier raccordé pour exécuter cette procédure, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4ea14-241">You may remove the keyboard if it was attached to allow you to perform this procedure.</span></span>
## <a name="troubleshooting-tips"></a><span data-ttu-id="4ea14-242">Astuces de dépannage</span><span class="sxs-lookup"><span data-stu-id="4ea14-242">Troubleshooting tips</span></span>
<span data-ttu-id="4ea14-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-243"></span></span>

- <span data-ttu-id="4ea14-244">Les invitations aux réunions peuvent ne pas apparaître lorsqu’elles sont envoyées sur plusieurs domaines (par exemple, entre deux entreprises).</span><span class="sxs-lookup"><span data-stu-id="4ea14-244">Meeting invitations may not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="4ea14-245">Dans de tels cas, les administrateurs informatiques devraient décidés de permettre ou non aux utilisateurs externes de planifier une réunion.</span><span class="sxs-lookup"><span data-stu-id="4ea14-245">In such cases, IT admins should decide whether or not to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="4ea14-246">Systèmes de salle Skype v2 ne supporte pas les redirections d’AutoDiscover d’Exchange via Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="4ea14-246">Skype Room Systems v2 does not support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="4ea14-247">En général, il est recommandé aux administrateurs informatiques de désactiver les terminaux audio non destinés à être utilisés</span><span class="sxs-lookup"><span data-stu-id="4ea14-247">In general, it is a good practice for IT admins to disable any audio endpoints not intended for use.</span></span>
    
- <span data-ttu-id="4ea14-248">Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.</span><span class="sxs-lookup"><span data-stu-id="4ea14-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="4ea14-249">La perte de l’accès à l’écran tactile de la console est connue.</span><span class="sxs-lookup"><span data-stu-id="4ea14-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="4ea14-250">Dans ce cas, le problème est parfois résolu en redémarrant le système v2 de systèmes de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4ea14-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="4ea14-251">La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue.</span><span class="sxs-lookup"><span data-stu-id="4ea14-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="4ea14-252">Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.</span><span class="sxs-lookup"><span data-stu-id="4ea14-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ea14-253">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ea14-253">See also</span></span>
<span data-ttu-id="4ea14-254"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea14-254"></span></span>

#### 

[<span data-ttu-id="4ea14-255">Plan de salle de Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="4ea14-255">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="4ea14-256">Déployer Skype salle systèmes v2</span><span class="sxs-lookup"><span data-stu-id="4ea14-256">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="4ea14-257">Configurer une console v2 de systèmes de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="4ea14-257">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="4ea14-258">Gérer les paramètres de console de systèmes de salle Skype v2 à distance avec un fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="4ea14-258">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

