---
title: Configurer une console de salle Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit la configuration de la console salles de Microsoft teams et de ses périphériques.
ms.openlocfilehash: 1bb1e45eca95628222b799d94c953bb49da1ea17
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243475"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="814a0-103">Configurer une console de salle Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="814a0-104">Cet article décrit la configuration de la console salles de Microsoft teams et de ses périphériques.</span><span class="sxs-lookup"><span data-stu-id="814a0-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="814a0-105">Vous devez effectuer cette procédure uniquement si les comptes Microsoft teams ou Skype entreprise et Exchange requis ont déjà été créés et testés comme décrit dans la rubrique [déploiement de salles de Microsoft teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="814a0-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="814a0-106">Vous aurez besoin du matériel et du logiciel décrits dans la [Configuration requise dans Microsoft teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="814a0-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="814a0-107">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="814a0-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="814a0-108">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="814a0-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="814a0-109">Installer un certificat d’autorité de certification privée sur la console</span><span class="sxs-lookup"><span data-stu-id="814a0-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="814a0-110">Installation de Windows 10 et de l’application de console Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="814a0-111">Configuration initiale de la console</span><span class="sxs-lookup"><span data-stu-id="814a0-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="814a0-112">Liste de vérification de déploiement de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="814a0-113">Les salles de Microsoft teams fonctionneront uniquement dans un environnement Microsoft teams ou Skype entreprise correctement configuré pour lequel les comptes de périphériques sont correctement configurés comme décrit dans la rubrique [déploiement de salles Microsoft teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="814a0-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="814a0-114">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="814a0-114">Prepare the installation media</span></span>
<span data-ttu-id="814a0-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-115"></span></span>

<span data-ttu-id="814a0-116">L’installation de l’application Microsoft teams salle console nécessite un périphérique de stockage USB doté d’au moins 32 Go de capacité.</span><span class="sxs-lookup"><span data-stu-id="814a0-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="814a0-117">Il n’y a pas d’autres fichiers sur l’appareil; tout fichier existant sur le stockage USB sera perdu.</span><span class="sxs-lookup"><span data-stu-id="814a0-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="814a0-118">L’impossibilité de créer votre support d’installation de Microsoft Teams (en vertu de ces instructions) peut entraîner un comportement inattendu.</span><span class="sxs-lookup"><span data-stu-id="814a0-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="814a0-119">Le processus ci-dessous consiste à créer un support d’installation pour l’image des nouveaux appareils Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="814a0-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="814a0-120">Par défaut, les appareils existants sont automatiquement mis à jour à partir de Windows Update et du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="814a0-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="814a0-121">Téléchargez le [script CreateSrsMedia. ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="814a0-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="814a0-122">Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="814a0-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="814a0-123">Suivez les instructions du script pour créer un disque de configuration USB Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="814a0-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="814a0-124">Chaque fois que le script CreateSrsMedia. ps1 démarre, la sortie écran inclut le nom d’un fichier journal ou d’une transcription de la session.</span><span class="sxs-lookup"><span data-stu-id="814a0-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="814a0-125">Si vous rencontrez des problèmes lors de l’exécution du script, assurez-vous qu’une copie de cette transcription est disponible lors de la demande d’assistance.</span><span class="sxs-lookup"><span data-stu-id="814a0-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="814a0-126">Le script CreateSrsMedia. ps1 automatise les tâches suivantes:</span><span class="sxs-lookup"><span data-stu-id="814a0-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="814a0-127">Téléchargez la dernière version du programme d’installation MSI pour les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="814a0-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="814a0-128">Déterminez la version de Windows que l’utilisateur doit fournir.</span><span class="sxs-lookup"><span data-stu-id="814a0-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="814a0-129">Les versions les plus récentes sont susceptibles de ne pas être testées et prises en charge pour une utilisation avec des appareils Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="814a0-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="814a0-130">Téléchargez les composants d’assistance nécessaires.</span><span class="sxs-lookup"><span data-stu-id="814a0-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="814a0-131">Assemblez les composants nécessaires sur le support d’installation.</span><span class="sxs-lookup"><span data-stu-id="814a0-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="814a0-132">Une version spécifique de Windows 10 est requise, et cette version n’est disponible que pour les clients du programme de licence en volume.</span><span class="sxs-lookup"><span data-stu-id="814a0-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="814a0-133">Vous pouvez obtenir une copie via le [Centre](https://www.microsoft.com/Licensing/servicecenter/)de gestion des licences en volume.</span><span class="sxs-lookup"><span data-stu-id="814a0-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="814a0-134">Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur, puis procédez à [l’installation de Windows 10 et de l’application console de Microsoft teams](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="814a0-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="814a0-135">Installation de Windows 10 et de l’application de console Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="814a0-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-136"></span></span>

<span data-ttu-id="814a0-137">Vous devez maintenant appliquer le média de configuration que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="814a0-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="814a0-138">L’appareil cible sera exécuté en tant que matériel et l’utilisateur par défaut sera configuré pour exécuter l’application console Microsoft teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="814a0-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="814a0-139">Si l’appareil cible doit être installé dans un dock (par exemple, surface Pro), débranchez-le du Dock.</span><span class="sxs-lookup"><span data-stu-id="814a0-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="814a0-140">Assurez-vous que l’appareil cible n’est pas connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="814a0-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="814a0-141">Assurez-vous que l’appareil cible est connecté à une alimentation ca.</span><span class="sxs-lookup"><span data-stu-id="814a0-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="814a0-142">Branchez le disque de configuration USB dans l’appareil cible.</span><span class="sxs-lookup"><span data-stu-id="814a0-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="814a0-143">Démarrez sur le disque de configuration USB.</span><span class="sxs-lookup"><span data-stu-id="814a0-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="814a0-144">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="814a0-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="814a0-145">S’il s’agit d’un appareil cible, utilisez les étapes suivantes pour démarrer l’installation sur le disque de configuration USB:</span><span class="sxs-lookup"><span data-stu-id="814a0-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="814a0-146">a.</span><span class="sxs-lookup"><span data-stu-id="814a0-146">a.</span></span> <span data-ttu-id="814a0-147">Appuyez de façon prolongée sur le bouton du volume (-).</span><span class="sxs-lookup"><span data-stu-id="814a0-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="814a0-148">b.</span><span class="sxs-lookup"><span data-stu-id="814a0-148">b.</span></span> <span data-ttu-id="814a0-149">Appuyez et relâchez le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="814a0-149">Press and release the power button.</span></span>

    <span data-ttu-id="814a0-150">c.</span><span class="sxs-lookup"><span data-stu-id="814a0-150">c.</span></span> <span data-ttu-id="814a0-151">Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).</span><span class="sxs-lookup"><span data-stu-id="814a0-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="814a0-152">Le système s’arrêtera une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="814a0-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="814a0-153">Une fois le système arrêté, il est sûr de supprimer le disque de configuration USB.</span><span class="sxs-lookup"><span data-stu-id="814a0-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="814a0-154">À ce stade, vous pouvez placer l’appareil cible dans sa station d’accueil (si vous utilisez un produit d’une station d’accueil), joindre les périphériques nécessaires à votre salle de réunion et vous connecter au réseau.</span><span class="sxs-lookup"><span data-stu-id="814a0-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="814a0-155">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="814a0-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="814a0-156">Sélectionner une langue</span><span class="sxs-lookup"><span data-stu-id="814a0-156">Selecting a language</span></span> 

<span data-ttu-id="814a0-157">Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage. ps1 dans les scénarios dans lesquels la sélection de la langue implicite ne fournit pas à l’utilisateur la langue réelle de l’application (par exemple, l’application de la console peut se trouver en français, mais ce service est disponible en anglais).</span><span class="sxs-lookup"><span data-stu-id="814a0-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="814a0-158">Les instructions suivantes ne fonctionnent pas pour les consoles créées à l’aide de la mise à jour du créateur Windows.</span><span class="sxs-lookup"><span data-stu-id="814a0-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="814a0-159">Les systèmes traditionnels/inactifs qui n’ont pas été configurés à l’aide du système multimédia avec le nouveau système de mise en service ne seront pas en mesure d’utiliser ces instructions, mais ne peuvent pas en souffrir du problème initial qui nécessite cette intervention manuelle (édition anniversaire vous permet de choisir langue de l’application explicitement dans le cadre de la configuration).</span><span class="sxs-lookup"><span data-stu-id="814a0-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="814a0-160">Pour appliquer la langue de votre choix</span><span class="sxs-lookup"><span data-stu-id="814a0-160">To apply your desired language</span></span>

1. <span data-ttu-id="814a0-161">Passez en mode Administrateur.</span><span class="sxs-lookup"><span data-stu-id="814a0-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="814a0-162">Sélectionnez le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="814a0-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="814a0-163">Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="814a0-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="814a0-164">Sélectionnez **Time &amp; Language**.</span><span class="sxs-lookup"><span data-stu-id="814a0-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="814a0-165">Sélectionner **la &amp; langue de région**.</span><span class="sxs-lookup"><span data-stu-id="814a0-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="814a0-166">Sélectionnez **Ajouter une langue**.</span><span class="sxs-lookup"><span data-stu-id="814a0-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="814a0-167">Sélectionnez la langue que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="814a0-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="814a0-168">Sélectionnez la langue que vous venez d’ajouter à la liste «langues».</span><span class="sxs-lookup"><span data-stu-id="814a0-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="814a0-169">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="814a0-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="814a0-170">Pour supprimer une langue :</span><span class="sxs-lookup"><span data-stu-id="814a0-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="814a0-p114">a. Sélectionnez la langue que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="814a0-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="814a0-p115">b. Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="814a0-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="814a0-175">Lancez une invite de commande avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="814a0-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="814a0-176">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="814a0-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="814a0-177">Redémarrez le système.</span><span class="sxs-lookup"><span data-stu-id="814a0-177">Restart the system.</span></span>
    
<span data-ttu-id="814a0-178">La langue souhaitée est désormais appliquée à la console Microsoft teams salles.</span><span class="sxs-lookup"><span data-stu-id="814a0-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="814a0-179">Configuration initiale de la console</span><span class="sxs-lookup"><span data-stu-id="814a0-179">Initial set up of the console</span></span>
<span data-ttu-id="814a0-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-180"></span></span>

<span data-ttu-id="814a0-181">Après l’installation de Windows, l’application console de Microsoft teams se trouve dans le processus de configuration initial lors du démarrage suivant ou si l’option/reboot a été choisie.</span><span class="sxs-lookup"><span data-stu-id="814a0-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="814a0-182">L’écran Compte d’utilisateur apparaît.</span><span class="sxs-lookup"><span data-stu-id="814a0-182">The User Account screen appears.</span></span> <span data-ttu-id="814a0-183">Entrez l’adresse de connexion de Skype (au format user @ domain) du compte de la salle à utiliser avec la console.</span><span class="sxs-lookup"><span data-stu-id="814a0-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="814a0-184">Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="814a0-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="814a0-185">Sous «configurer le domaine», définissez le FQDN du serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="814a0-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="814a0-186">Si le domaine SIP de Skype entreprise est différent de celui du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="814a0-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="814a0-187">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="814a0-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="814a0-188">Sélectionnez les périphériques indiqués sur l’écran fonctionnalités, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="814a0-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="814a0-189">Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="814a0-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="814a0-190">Les appareils à sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="814a0-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="814a0-191">Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="814a0-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="814a0-192">Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences. </span><span class="sxs-lookup"><span data-stu-id="814a0-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="814a0-193">Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.</span><span class="sxs-lookup"><span data-stu-id="814a0-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="814a0-p119">Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="814a0-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="814a0-196">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="814a0-196">Click **Finish**.</span></span>
    
<span data-ttu-id="814a0-197">Dans l’application Microsoft teams de Microsoft Teams, l’application doit commencer immédiatement à se connecter à Skype entreprise Server avec les informations d’identification entrées ci-dessus, et doit également commencer à synchroniser son calendrier avec Exchange en utilisant ces mêmes informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="814a0-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="814a0-198">Pour plus d’informations sur l’utilisation de l’application console, voir l' [aide de Microsoft teams](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="814a0-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="814a0-199">Les salles de Microsoft teams sont basées sur la présence de matériel de console certifié.</span><span class="sxs-lookup"><span data-stu-id="814a0-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="814a0-200">Même une image correctement créée contenant l’application console de Microsoft Teams ne démarre pas après la procédure de configuration initiale, sauf si le matériel de la console est détecté.</span><span class="sxs-lookup"><span data-stu-id="814a0-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="814a0-201">Pour les solutions basées sur les périphériques de surface, l’apparence de surface Pro doit être connectée au matériel d’accueil associé pour réussir ce contrôle.</span><span class="sxs-lookup"><span data-stu-id="814a0-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="814a0-202">Certains utilisateurs de langues autres que l’anglais peuvent avoir besoin d’un clavier physique connecté à la console lors de la configuration initiale dans le cas où ces symboles ne sont pas pris en charge sur le clavier visuel.</span><span class="sxs-lookup"><span data-stu-id="814a0-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="814a0-203">Installer un certificat d’autorité de certification privée sur la console</span><span class="sxs-lookup"><span data-stu-id="814a0-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="814a0-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-204"></span></span>

<span data-ttu-id="814a0-205">La console Microsoft teams salles doit faire confiance aux certificats utilisés par les serveurs auxquels elle est connectée.</span><span class="sxs-lookup"><span data-stu-id="814a0-205">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="814a0-206">Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10.</span><span class="sxs-lookup"><span data-stu-id="814a0-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="814a0-207">Dans le cas où l’autorité de certification est privée, par exemple un déploiement local avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat à la console de Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="814a0-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="814a0-208">Vous pouvez joindre la console à Active Directory et ajoutera automatiquement les certificats requis pour les autorités de certification publiées dans Active Directory (option de déploiement normale).</span><span class="sxs-lookup"><span data-stu-id="814a0-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="814a0-209">Vous pouvez installer le certificat manuellement après le processus de création d’image.</span><span class="sxs-lookup"><span data-stu-id="814a0-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="814a0-210">Avant cela, vous devez terminer [la configuration initiale de la console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="814a0-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="814a0-211">Pour installer manuellement le certificat </span><span class="sxs-lookup"><span data-stu-id="814a0-211">To manually install the certificate</span></span>

1. <span data-ttu-id="814a0-212">Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="814a0-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="814a0-213">Placez la console en mode administrateur (voir [mode administrateur et gestion des appareils](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="814a0-213">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="814a0-214">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="814a0-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="814a0-215">Rejoindre un domaine Active Directory (facultatif)</span><span class="sxs-lookup"><span data-stu-id="814a0-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="814a0-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-216"></span></span>

<span data-ttu-id="814a0-217">Vous pouvez joindre des consoles de Microsoft teams à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="814a0-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="814a0-218">Les consoles de salle Microsoft teams doivent être placées dans une unité d’organisation distincte de celle de votre ordinateur, car de nombreuses stratégies de station de travail ne sont pas compatibles avec les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="814a0-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="814a0-219">Un exemple courant est une stratégie de mise en application de mot de passe qui empêche le démarrage automatique de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="814a0-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="814a0-220">Pour plus d’informations sur la gestion des paramètres d’objets de stratégie de groupe, voir [gérer les salles de Microsoft teams](room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="814a0-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="814a0-221">Pour joindre des salles de Microsoft teams à un domaine</span><span class="sxs-lookup"><span data-stu-id="814a0-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="814a0-222">Connectez-vous à la console à partir du compte d’administrateur (voir [mode administrateur et gestion des appareils](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="814a0-222">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="814a0-223">Lancez l’invite de commande Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="814a0-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="814a0-224">Saisissez la commande suivante dans Powershell :</span><span class="sxs-lookup"><span data-stu-id="814a0-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="814a0-225">Par exemple, si votre domaine complet est redmond.corp.microsoft.com et que vous voulez que les consoles de Microsoft teams se trouvent dans une UO «Microsoft teams» qui est un enfant d’une unité d’organisation «Resources», la commande sera:</span><span class="sxs-lookup"><span data-stu-id="814a0-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="814a0-226">Si vous souhaitez renommer l’ordinateur lorsque vous le Rejoignez à un domaine, utilisez l’indicateur-NewName suivi du nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="814a0-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="814a0-227">Liste de vérification de déploiement de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="814a0-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-228"></span></span>

<span data-ttu-id="814a0-229">Utilisez la liste de vérification suivante tout en effectuant une vérification finale, la console et tous ses périphériques sont entièrement configurés:</span><span class="sxs-lookup"><span data-stu-id="814a0-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="814a0-230">**Paramètres de l’application**</span><span class="sxs-lookup"><span data-stu-id="814a0-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="814a0-231">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-231">☐</span></span>  <br/> |<span data-ttu-id="814a0-232">Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.</span><span class="sxs-lookup"><span data-stu-id="814a0-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="814a0-233">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-233">☐</span></span>  <br/> |<span data-ttu-id="814a0-234">Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).</span><span class="sxs-lookup"><span data-stu-id="814a0-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="814a0-235">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-235">☐</span></span>  <br/> |<span data-ttu-id="814a0-236">Le mot de passe du compte de l’administrateur est défini et vérifié.</span><span class="sxs-lookup"><span data-stu-id="814a0-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="814a0-237">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-237">☐</span></span>  <br/> |<span data-ttu-id="814a0-238">Toutes les mises à jour de microprogrammes ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="814a0-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="814a0-239">**Périphériques audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="814a0-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="814a0-240">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-240">☐</span></span>  <br/> |<span data-ttu-id="814a0-241">La version du microprogramme de la caméra est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="814a0-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="814a0-242">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-242">☐</span></span>  <br/> |<span data-ttu-id="814a0-243">Fonctionnement de la caméra et positionnement optimal</span><span class="sxs-lookup"><span data-stu-id="814a0-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="814a0-244">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-244">☐</span></span>  <br/> |<span data-ttu-id="814a0-245">Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.</span><span class="sxs-lookup"><span data-stu-id="814a0-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="814a0-246">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-246">☐</span></span>  <br/> |<span data-ttu-id="814a0-247">Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.</span><span class="sxs-lookup"><span data-stu-id="814a0-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="814a0-248">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-248">☐</span></span>  <br/> |<span data-ttu-id="814a0-249">La version du microprogramme du périphérique audio est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="814a0-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="814a0-250">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-250">☐</span></span>  <br/> |<span data-ttu-id="814a0-251">Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="814a0-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="814a0-252">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-252">☐</span></span>  <br/> |<span data-ttu-id="814a0-253">Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="814a0-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="814a0-254">**Dock**</span><span class="sxs-lookup"><span data-stu-id="814a0-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="814a0-255">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-255">☐</span></span>  <br/> |<span data-ttu-id="814a0-256">Les câbles sont sécurisés et ne sont pas pincés.</span><span class="sxs-lookup"><span data-stu-id="814a0-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="814a0-257">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-257">☐</span></span>  <br/> |<span data-ttu-id="814a0-258">La réception audio via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="814a0-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="814a0-259">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-259">☐</span></span>  <br/> |<span data-ttu-id="814a0-260">La réception vidéo via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="814a0-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="814a0-261">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-261">☐</span></span>  <br/> |<span data-ttu-id="814a0-262">Le dock peut pivoter librement.</span><span class="sxs-lookup"><span data-stu-id="814a0-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="814a0-263">☐</span><span class="sxs-lookup"><span data-stu-id="814a0-263">☐</span></span>  <br/> |<span data-ttu-id="814a0-264">La luminosité de l’affichage est acceptable pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="814a0-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="814a0-265">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="814a0-265">See also</span></span>
<span data-ttu-id="814a0-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="814a0-266"></span></span>

[<span data-ttu-id="814a0-267">Plan pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-267">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="814a0-268">Déploiement de salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="814a0-269">Configurer une console de salle Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="814a0-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="814a0-270">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="814a0-270">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
