---
title: Configurer une console des salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit comment configurer et configurer la console Salles Microsoft Teams et ses périphériques.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662059"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="00b56-103">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="00b56-104">Cet article décrit comment configurer la console Salles Microsoft Teams et ses périphériques.</span><span class="sxs-lookup"><span data-stu-id="00b56-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="00b56-105">Vous ne devez effectuer cette procédure que si les comptes Microsoft Teams ou Skype Entreprise et Exchange nécessaires ont déjà été créés et testés comme décrit dans Déployer des salles [Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="00b56-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="00b56-106">Vous aurez besoin du matériel et du logiciel décrits dans la configuration [requise pour les salles Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="00b56-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="00b56-107">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="00b56-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="00b56-108">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="00b56-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="00b56-109">Installer un certificat d’autorisation d’certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="00b56-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="00b56-110">Installer Windows 10 et l’application Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="00b56-111">Configurer initialement la console</span><span class="sxs-lookup"><span data-stu-id="00b56-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="00b56-112">Liste de contrôle du déploiement de salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="00b56-113">Salles Microsoft Teams ne fonctionne que dans un environnement Microsoft Teams ou Skype Entreprise correctement configuré où les comptes d’appareil sont correctement configurés, comme décrit dans Déployer les salles [Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="00b56-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="00b56-114">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="00b56-114">Prepare the installation media</span></span>
<span data-ttu-id="00b56-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="00b56-116">L’installation de l’application Salles Microsoft Teams nécessite un dispositif de stockage USB dont la capacité est d’au moins 32 Go.</span><span class="sxs-lookup"><span data-stu-id="00b56-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="00b56-117">L’appareil ne doit pas avoir d’autres fichiers. Tous les fichiers existants sur le stockage USB seront perdus.</span><span class="sxs-lookup"><span data-stu-id="00b56-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00b56-118">L’échec de la création du support d’installation de salles Microsoft Teams en fonction de ces instructions peut entraîner un comportement inattendu.</span><span class="sxs-lookup"><span data-stu-id="00b56-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="00b56-119">Le processus ci-dessous a pour objectif de créer un support d’installation pour image de nouveaux appareils Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="00b56-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="00b56-120">Par défaut, les appareils existants sont mis à jour automatiquement à partir de Windows Update et du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="00b56-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00b56-121">L’ordinateur Windows 10 utilisé pour créer le support d’installation de Salles Microsoft Teams doit être dans la même version ou ultérieure de Windows que le support d’installation cible.</span><span class="sxs-lookup"><span data-stu-id="00b56-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="00b56-122">Téléchargez le [scriptCreateSrsMedia.ps1'application.](https://go.microsoft.com/fwlink/?linkid=867842)</span><span class="sxs-lookup"><span data-stu-id="00b56-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="00b56-123">Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="00b56-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="00b56-124">Suivez les instructions du script pour créer un disque de configuration USB de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="00b56-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="00b56-125">Chaque fois que CreateSrsMedia.ps1 script principal démarre, la sortie à l’écran inclut le nom d’un fichier journal ou d’une transcription de la session.</span><span class="sxs-lookup"><span data-stu-id="00b56-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="00b56-126">Si vous avez des problèmes lors de l’exécution du script, assurez-vous qu’une copie de cette transcription est disponible lorsque vous demandez de l’aide.</span><span class="sxs-lookup"><span data-stu-id="00b56-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="00b56-127">Le CreateSrsMedia.ps1 script automatise les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="00b56-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="00b56-128">Téléchargez le dernier programme d’installation MSI pour les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="00b56-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="00b56-129">Déterminez la build de Windows que l’utilisateur doit fournir.</span><span class="sxs-lookup"><span data-stu-id="00b56-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="00b56-130">Il est possible que les versions les plus récentes ne soient pas testées et qu’elles soient prise en charge pour une utilisation avec les appareils Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="00b56-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="00b56-131">Téléchargez les composants de prise en charge nécessaires.</span><span class="sxs-lookup"><span data-stu-id="00b56-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="00b56-132">Assemblez les composants nécessaires sur le support d’installation.</span><span class="sxs-lookup"><span data-stu-id="00b56-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="00b56-133">Une version spécifique de Windows 10 est requise, et cette version est uniquement disponible pour les clients de licence en volume.</span><span class="sxs-lookup"><span data-stu-id="00b56-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="00b56-134">Vous pouvez en obtenir une copie à partir du Centre [de gestion des licences en volume.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="00b56-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="00b56-135">Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et continuez à installer Windows 10 et l’application de [console Salles Microsoft Teams.](console.md#Reimage)</span><span class="sxs-lookup"><span data-stu-id="00b56-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="00b56-136">Installer Windows 10 et l’application Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="00b56-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="00b56-138">Vous devez à présent appliquer le support de configuration que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="00b56-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="00b56-139">Le périphérique cible s’exécute sous la mesure d’une appliance et l’utilisateur par défaut est réglé pour exécuter uniquement l’application de console Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="00b56-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="00b56-140">Si l’appareil cible est installé dans une station d’accueil (par exemple, une Surface Pro), déconnectez-le de la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="00b56-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="00b56-141">Assurez-vous que l’appareil cible n’est pas connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="00b56-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="00b56-142">Assurez-vous que l’appareil cible est connecté à la puissance AC.</span><span class="sxs-lookup"><span data-stu-id="00b56-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="00b56-143">Branchez votre disque de configuration USB sur le périphérique cible.</span><span class="sxs-lookup"><span data-stu-id="00b56-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="00b56-144">Démarrez le disque d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="00b56-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="00b56-145">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="00b56-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="00b56-146">Si votre appareil cible est une Surface Pro, utilisez les étapes suivantes pour démarrer sur le disque de configuration USB :</span><span class="sxs-lookup"><span data-stu-id="00b56-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="00b56-147">a.</span><span class="sxs-lookup"><span data-stu-id="00b56-147">a.</span></span> <span data-ttu-id="00b56-148">Appuyez sur le bouton de baisse du volume (-) et maintenez-le enfoncé.</span><span class="sxs-lookup"><span data-stu-id="00b56-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="00b56-149">b.</span><span class="sxs-lookup"><span data-stu-id="00b56-149">b.</span></span> <span data-ttu-id="00b56-150">Appuyez sur le bouton d’alimentation et relâchez-le.</span><span class="sxs-lookup"><span data-stu-id="00b56-150">Press and release the power button.</span></span>

    <span data-ttu-id="00b56-151">c.</span><span class="sxs-lookup"><span data-stu-id="00b56-151">c.</span></span> <span data-ttu-id="00b56-152">Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).</span><span class="sxs-lookup"><span data-stu-id="00b56-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="00b56-153">Le système se ferme une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="00b56-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="00b56-154">Une fois le système arrêté, vous risquez de supprimer le disque d’installation USB en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="00b56-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="00b56-155">À ce stade, vous pouvez placer l’appareil cible dans sa station d’accueil (si vous utilisez un produit basé sur une station d’accueil), connecter les périphériques nécessaires à votre salle de réunion et vous connecter au réseau.</span><span class="sxs-lookup"><span data-stu-id="00b56-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="00b56-156">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="00b56-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="00b56-157">Les mises à jour logicielles des salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="00b56-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="00b56-158">Consultez [les conditions préalables pour que Microsoft Store](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) pour Entreprises et Éducation vérifie que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="00b56-158">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="00b56-159">Sélection d’une langue</span><span class="sxs-lookup"><span data-stu-id="00b56-159">Selecting a language</span></span> 

<span data-ttu-id="00b56-160">Dans la Mise à jour de l’application de créateur, vous devrez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de langue implicite ne fournit pas à l’utilisateur la langue réelle de l’application qu’il souhaite (par exemple, il souhaite que l’application de console soit fournie en français, mais qu’elle soit en anglais).</span><span class="sxs-lookup"><span data-stu-id="00b56-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00b56-161">Les instructions suivantes fonctionnent uniquement pour les consoles créées à l’aide de la mise à jour de créateur de Windows.</span><span class="sxs-lookup"><span data-stu-id="00b56-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="00b56-162">Les systèmes hérités/sur le marché qui n’ont pas été configurés à l’aide du média avec le nouveau système de mise en service ne pourront pas utiliser ces instructions, mais ne doivent pas non plus être en raison du problème initial nécessitant cette intervention manuelle (l’édition anniversaire vous permet de sélectionner la langue de votre application explicitement dans le cadre de la configuration).</span><span class="sxs-lookup"><span data-stu-id="00b56-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="00b56-163">Pour appliquer la langue de votre choix</span><span class="sxs-lookup"><span data-stu-id="00b56-163">To apply your desired language</span></span>

1. <span data-ttu-id="00b56-164">Passez en mode Administrateur.</span><span class="sxs-lookup"><span data-stu-id="00b56-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="00b56-165">Sélectionnez le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="00b56-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="00b56-166">Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="00b56-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="00b56-167">Sélectionnez **la langue &amp; de l’heure.**</span><span class="sxs-lookup"><span data-stu-id="00b56-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="00b56-168">Sélectionnez **la langue de la &amp; région.**</span><span class="sxs-lookup"><span data-stu-id="00b56-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="00b56-169">Sélectionnez **Ajouter une langue**.</span><span class="sxs-lookup"><span data-stu-id="00b56-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="00b56-170">Sélectionnez la langue que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="00b56-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="00b56-171">Sélectionnez la langue que vous vient d’ajouter à la liste « Langues ».</span><span class="sxs-lookup"><span data-stu-id="00b56-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="00b56-172">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="00b56-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="00b56-173">Pour supprimer une langue :</span><span class="sxs-lookup"><span data-stu-id="00b56-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="00b56-p115">a. Sélectionnez la langue que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="00b56-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="00b56-p116">b. Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="00b56-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="00b56-178">Lancez une invite de commande avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="00b56-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="00b56-179">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="00b56-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="00b56-180">Redémarrez le système.</span><span class="sxs-lookup"><span data-stu-id="00b56-180">Restart the system.</span></span>
    
<span data-ttu-id="00b56-181">La langue souhaitée est désormais appliquée à la console Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="00b56-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="00b56-182">Configurer initialement la console</span><span class="sxs-lookup"><span data-stu-id="00b56-182">Initial set up of the console</span></span>
<span data-ttu-id="00b56-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="00b56-184">Une fois Windows installé, l’application de console Salles Microsoft Teams se lancera dans le processus de configuration initial au moment de la prochaine mise en place ou si l’option /redémarrage a été choisie.</span><span class="sxs-lookup"><span data-stu-id="00b56-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="00b56-185">L’écran Compte d’utilisateur apparaît.</span><span class="sxs-lookup"><span data-stu-id="00b56-185">The User Account screen appears.</span></span> <span data-ttu-id="00b56-186">Entrez l’adresse de sign-in Skype (au format user@domain) du compte de salle à utiliser avec la console.</span><span class="sxs-lookup"><span data-stu-id="00b56-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="00b56-187">Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="00b56-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="00b56-188">Sous « Configurer le domaine », définissez le nom de domaine (FQDN) pour le serveur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="00b56-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="00b56-189">Si le domaine SIP Skype Entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="00b56-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="00b56-190">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="00b56-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="00b56-191">Sélectionnez les appareils indiqués dans l’écran Fonctionnalités, puis cliquez **sur Suivant.**</span><span class="sxs-lookup"><span data-stu-id="00b56-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="00b56-192">Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="00b56-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="00b56-193">Les appareils à sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="00b56-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="00b56-194">Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="00b56-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="00b56-195">Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences. </span><span class="sxs-lookup"><span data-stu-id="00b56-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="00b56-196">Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.</span><span class="sxs-lookup"><span data-stu-id="00b56-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="00b56-p120">Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="00b56-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="00b56-199">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="00b56-199">Click **Finish**.</span></span>
    
<span data-ttu-id="00b56-200">L’application Salles Microsoft Teams doit commencer immédiatement à se connexion à Skype Entreprise Server avec les informations d’identification entrées ci-dessus, et doit également commencer à synchroniser son calendrier avec Exchange à l’aide des mêmes informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="00b56-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="00b56-201">Pour plus d’informations sur l’utilisation de l’application de console, consultez [l’aide de Salles Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="00b56-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="00b56-202">Salles Microsoft Teams s’appuie sur la présence de matériel de console certifié.</span><span class="sxs-lookup"><span data-stu-id="00b56-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="00b56-203">Même une image correctement créée contenant l’application de console Salles Microsoft Teams ne démarre pas au-delà de la procédure de configuration initiale, sauf si le matériel de la console est détecté.</span><span class="sxs-lookup"><span data-stu-id="00b56-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="00b56-204">Pour les solutions Surface Pro, la Surface Pro doit être connectée à son matériel de la station d’accueil pour que cette vérification soit établie.</span><span class="sxs-lookup"><span data-stu-id="00b56-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00b56-205">Certains utilisateurs non anglophones auront besoin d’un clavier physique connecté à la console lors de la configuration initiale si les symboles ne sont pas pris en charge sur le clavier tactile.</span><span class="sxs-lookup"><span data-stu-id="00b56-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="00b56-206">Installer un certificat d’autorisation d’certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="00b56-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="00b56-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="00b56-208">La console Salles Microsoft Teams doit faire confiance aux certificats utilisés par les serveurs avec qui elle se connecte.</span><span class="sxs-lookup"><span data-stu-id="00b56-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="00b56-209">Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10.</span><span class="sxs-lookup"><span data-stu-id="00b56-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="00b56-210">Dans le cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat à la console Salles Microsoft Teams de deux façons :</span><span class="sxs-lookup"><span data-stu-id="00b56-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="00b56-211">Vous pouvez rejoindre la console d’Active Directory et cela ajoutera automatiquement les certificats requis à la publication de l’autorité de certification dans Active Directory (option de déploiement normal).</span><span class="sxs-lookup"><span data-stu-id="00b56-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="00b56-212">Vous pouvez installer le certificat manuellement après le processus de création d’image.</span><span class="sxs-lookup"><span data-stu-id="00b56-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="00b56-213">Avant cela, vous devez effectuer la mise en place initiale [de la console.](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="00b56-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="00b56-214">Pour installer manuellement le certificat </span><span class="sxs-lookup"><span data-stu-id="00b56-214">To manually install the certificate</span></span>

1. <span data-ttu-id="00b56-215">Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="00b56-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="00b56-216">Placez la console en mode d’administration (voir [Mode d’administration et gestion des appareils).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="00b56-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="00b56-217">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="00b56-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="00b56-218">Joindre un domaine Active Directory (facultatif)</span><span class="sxs-lookup"><span data-stu-id="00b56-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="00b56-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="00b56-220">Vous pouvez joindre des consoles salles Microsoft Teams à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="00b56-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="00b56-221">Les consoles Salles Microsoft Teams doivent être placées dans une station d’exploitation distincte de vos stations de travail PC, car de nombreuses stratégies de station de travail ne sont pas compatibles avec les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="00b56-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="00b56-222">Les stratégies d’application de mot de passe qui empêchent microsoft Teams Rooms de démarrer automatiquement en sont un exemple courant.</span><span class="sxs-lookup"><span data-stu-id="00b56-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="00b56-223">Pour plus d’informations sur la gestion des paramètres des GPO, voir [Gérer des salles Microsoft Teams.](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="00b56-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="00b56-224">Pour joindre salles Microsoft Teams à un domaine</span><span class="sxs-lookup"><span data-stu-id="00b56-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="00b56-225">Connectez-vous à la console à partir du compte d’administrateur (voir [mode Administrateur et gestion des appareils).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="00b56-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="00b56-226">Lancez l’invite de commande Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="00b56-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="00b56-227">Saisissez la commande suivante dans Powershell :</span><span class="sxs-lookup"><span data-stu-id="00b56-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="00b56-228">Par exemple, si votre domaine complet est redmond.corp.microsoft.com et que vous souhaitez que vos consoles Salles Microsoft Teams se trouveront dans une « Salles Microsoft Teams » enfant d’une ou des « Ressources », la commande sera :</span><span class="sxs-lookup"><span data-stu-id="00b56-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="00b56-229">Si vous voulez renommer l’ordinateur lorsque vous l’associez à un domaine, utilisez l’indicateur -NewName suivi du nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="00b56-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="00b56-230">Liste de contrôle du déploiement de salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="00b56-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="00b56-232">Utilisez la liste de vérification suivante lors d’une vérification finale que la console et tous ses périphériques sont entièrement configurés :</span><span class="sxs-lookup"><span data-stu-id="00b56-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="00b56-233">**Paramètres de l’application**</span><span class="sxs-lookup"><span data-stu-id="00b56-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="00b56-234">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-234">☐</span></span>  <br/> |<span data-ttu-id="00b56-235">Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.</span><span class="sxs-lookup"><span data-stu-id="00b56-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="00b56-236">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-236">☐</span></span>  <br/> |<span data-ttu-id="00b56-237">Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).</span><span class="sxs-lookup"><span data-stu-id="00b56-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="00b56-238">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-238">☐</span></span>  <br/> |<span data-ttu-id="00b56-239">Le mot de passe du compte de l’administrateur est défini et vérifié.</span><span class="sxs-lookup"><span data-stu-id="00b56-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="00b56-240">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-240">☐</span></span>  <br/> |<span data-ttu-id="00b56-241">Toutes les mises à jour du microprogramme ont été appliquées</span><span class="sxs-lookup"><span data-stu-id="00b56-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="00b56-242">**Périphériques audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="00b56-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="00b56-243">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-243">☐</span></span>  <br/> |<span data-ttu-id="00b56-244">La version du microprogramme de la caméra est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="00b56-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="00b56-245">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-245">☐</span></span>  <br/> |<span data-ttu-id="00b56-246">Appareil photo fonctionnel et positionné de manière optimale</span><span class="sxs-lookup"><span data-stu-id="00b56-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="00b56-247">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-247">☐</span></span>  <br/> |<span data-ttu-id="00b56-248">Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.</span><span class="sxs-lookup"><span data-stu-id="00b56-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="00b56-249">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-249">☐</span></span>  <br/> |<span data-ttu-id="00b56-250">Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.</span><span class="sxs-lookup"><span data-stu-id="00b56-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="00b56-251">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-251">☐</span></span>  <br/> |<span data-ttu-id="00b56-252">La version du microprogramme du périphérique audio est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="00b56-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="00b56-253">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-253">☐</span></span>  <br/> |<span data-ttu-id="00b56-254">Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="00b56-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="00b56-255">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-255">☐</span></span>  <br/> |<span data-ttu-id="00b56-256">Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="00b56-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="00b56-257">**Dock**</span><span class="sxs-lookup"><span data-stu-id="00b56-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="00b56-258">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-258">☐</span></span>  <br/> |<span data-ttu-id="00b56-259">Les câbles sont sécurisés et ne sont pas pincés.</span><span class="sxs-lookup"><span data-stu-id="00b56-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="00b56-260">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-260">☐</span></span>  <br/> |<span data-ttu-id="00b56-261">La réception audio via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="00b56-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="00b56-262">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-262">☐</span></span>  <br/> |<span data-ttu-id="00b56-263">La réception vidéo via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="00b56-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="00b56-264">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-264">☐</span></span>  <br/> |<span data-ttu-id="00b56-265">Le dock peut pivoter librement.</span><span class="sxs-lookup"><span data-stu-id="00b56-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="00b56-266">☐</span><span class="sxs-lookup"><span data-stu-id="00b56-266">☐</span></span>  <br/> |<span data-ttu-id="00b56-267">La luminosité de l’affichage est acceptable pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="00b56-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="00b56-268">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00b56-268">See also</span></span>
<span data-ttu-id="00b56-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="00b56-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="00b56-270">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="00b56-271">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="00b56-272">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="00b56-273">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b56-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
