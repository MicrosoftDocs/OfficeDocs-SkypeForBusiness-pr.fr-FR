---
title: Configurer une console Microsoft équipes salles
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit comment configurer la console de salles d’équipes Microsoft et des périphériques.
ms.openlocfilehash: 2d3d9acdc3c72754232304364812fd2af9f3f6cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212753"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="a43c6-103">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="a43c6-104">Cet article décrit comment configurer la console de salles d’équipes Microsoft et des périphériques.</span><span class="sxs-lookup"><span data-stu-id="a43c6-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="a43c6-105">Vous devez uniquement effectuer ces étapes si la Skype nécessaire pour les comptes d’entreprise et Exchange ont déjà créé et testé comme décrit dans les [Salles d’équipes Microsoft de déployer](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="a43c6-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="a43c6-106">Vous devez le matériel et les logiciels décrits dans les [salles d’équipes Microsoft requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a43c6-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="a43c6-107">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="a43c6-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="a43c6-108">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="a43c6-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="a43c6-109">Installer un certificat d’autorité de certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="a43c6-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="a43c6-110">Installer Windows 10 et l’application de console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="a43c6-111">Configurer initiale de la console</span><span class="sxs-lookup"><span data-stu-id="a43c6-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="a43c6-112">Liste de vérification du déploiement Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="a43c6-113">Salles d’équipes Microsoft fonctionne uniquement dans un Skype pour un environnement d’entreprise où les comptes de périphériques sont correctement configurés comme décrit dans les [Salles d’équipes Microsoft déployer](room-systems-v2.md)correctement configurée.</span><span class="sxs-lookup"><span data-stu-id="a43c6-113">Microsoft Teams Rooms will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="a43c6-114">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="a43c6-114">Prepare the installation media</span></span>
<span data-ttu-id="a43c6-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-115"></span></span>

<span data-ttu-id="a43c6-116">Installation de l’application de console Microsoft équipes salles requiert un périphérique de stockage USB avec au moins 32 Go de la capacité.</span><span class="sxs-lookup"><span data-stu-id="a43c6-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="a43c6-117">Il ne doit y avoir aucun autre fichier sur le périphérique ; les fichiers existants sur le stockage USB seront perdues.</span><span class="sxs-lookup"><span data-stu-id="a43c6-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a43c6-118">Impossible de créer votre support d’installation Microsoft équipes salles en fonction de ces instructions aura un comportement inattendu.</span><span class="sxs-lookup"><span data-stu-id="a43c6-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="a43c6-119">La procédure ci-dessous est pour la création du support d’installation vers de nouveaux périphériques de salles d’équipes Microsoft image.</span><span class="sxs-lookup"><span data-stu-id="a43c6-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="a43c6-120">Périphériques existants, par défaut, mettre à jour automatiquement à partir de Windows Update et Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a43c6-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="a43c6-121">Télécharger le [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="a43c6-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="a43c6-122">Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a43c6-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="a43c6-123">Suivez les instructions du script pour créer un disque d’installation de Microsoft équipes salles USB.</span><span class="sxs-lookup"><span data-stu-id="a43c6-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="a43c6-124">Chaque fois que le script CreateSrsMedia.ps1 démarre, la sortie écran inclut le nom d’un fichier journal ou d’une transcription de la session.</span><span class="sxs-lookup"><span data-stu-id="a43c6-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="a43c6-125">S’il existe des problèmes liés à l’exécution du script, assurez-vous que vous disposez d’une copie de cette transcription disponible lors de la demande de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a43c6-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="a43c6-126">Le script CreateSrsMedia.ps1 automatise les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="a43c6-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="a43c6-127">Téléchargez le programme d’installation MSI le plus récent pour les salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a43c6-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="a43c6-128">Déterminer la version de Windows que l’utilisateur doit fournir.</span><span class="sxs-lookup"><span data-stu-id="a43c6-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="a43c6-129">Les versions la plus récentes peuvent ou ne peut pas être testées et pris en charge pour une utilisation avec des périphériques Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="a43c6-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="a43c6-130">Télécharger les composants de prise en charge nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a43c6-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="a43c6-131">Assembler les composants nécessaires sur le support d’installation.</span><span class="sxs-lookup"><span data-stu-id="a43c6-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="a43c6-132">Une version spécifique de Windows 10 est requise, et cette version est uniquement disponible pour les clients de licence en volume.</span><span class="sxs-lookup"><span data-stu-id="a43c6-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="a43c6-133">Vous pouvez obtenir une copie à partir du [Centre de gestion des licences en Volume](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="a43c6-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="a43c6-134">Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [10 de Windows Installer et les salles d’équipes Microsoft console application](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="a43c6-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="a43c6-135">Installer Windows 10 et l’application de console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="a43c6-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-136"></span></span>

<span data-ttu-id="a43c6-137">Vous devez maintenant appliquer le support d’installation que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="a43c6-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="a43c6-138">Le périphérique cible s’exécute en tant qu’un matériel et l’utilisateur par défaut sera définie ne s’exécute l’application de console Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="a43c6-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="a43c6-139">Si l’équipement est installé dans une station d’accueil (par exemple, une Surface Pro), le déconnecter de la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="a43c6-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="a43c6-140">Vérifiez que le périphérique cible n’est pas connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="a43c6-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="a43c6-141">Vérifiez que l’équipement est connecté au secteur.</span><span class="sxs-lookup"><span data-stu-id="a43c6-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="a43c6-142">Branchez votre disque d’installation USB sur le périphérique cible.</span><span class="sxs-lookup"><span data-stu-id="a43c6-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="a43c6-143">Démarrez le disque d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="a43c6-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="a43c6-144">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="a43c6-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="a43c6-145">Si votre périphérique cible est une Surface Pro, procédez comme suit pour démarrer sur le disque d’installation USB :</span><span class="sxs-lookup"><span data-stu-id="a43c6-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="a43c6-146">a.</span><span class="sxs-lookup"><span data-stu-id="a43c6-146">a.</span></span> <span data-ttu-id="a43c6-147">Appuyez sur et maintenez le volume vers le bas du bouton (-).</span><span class="sxs-lookup"><span data-stu-id="a43c6-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="a43c6-148">b.</span><span class="sxs-lookup"><span data-stu-id="a43c6-148">b.</span></span> <span data-ttu-id="a43c6-149">Appuyez puis relâchez le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="a43c6-149">Press and release the power button.</span></span>

    <span data-ttu-id="a43c6-150">c.</span><span class="sxs-lookup"><span data-stu-id="a43c6-150">c.</span></span> <span data-ttu-id="a43c6-151">Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).</span><span class="sxs-lookup"><span data-stu-id="a43c6-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="a43c6-152">Le système s’arrêtera une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="a43c6-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="a43c6-153">Une fois que le système est arrêté, il est recommandé supprimer le disque du programme d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="a43c6-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="a43c6-154">À ce stade, vous pourrez placer le périphérique cible dans sa station d’accueil (si vous utilisez un produit basé sur une station d’accueil), attacher les périphériques nécessaires pour votre salle de réunion et connexion au réseau.</span><span class="sxs-lookup"><span data-stu-id="a43c6-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="a43c6-155">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="a43c6-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="a43c6-156">Sélection d’une langue</span><span class="sxs-lookup"><span data-stu-id="a43c6-156">Selecting a language</span></span> 

<span data-ttu-id="a43c6-157">Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de la langue implicite ne fournit pas l’utilisateur dont la langue de l’application réelle qu’ils souhaitent (par exemple, qu’ils souhaitent l’application de console pour élaborer en Français, mais elle suit en anglais).</span><span class="sxs-lookup"><span data-stu-id="a43c6-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a43c6-158">Les instructions suivantes s’appliquent uniquement pour les consoles créées à l’aide de la mise à jour du créateur de Windows.</span><span class="sxs-lookup"><span data-stu-id="a43c6-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="a43c6-159">Systèmes hérité/dans-marché qui n’ont pas été définies à l’aide des supports avec le nouveau système de mise en service ne sera pas en mesure d’utiliser ces instructions, mais doit également préférable de l’émission initiale qui nécessite une intervention manuelle cette (Édition anniversaire vous permettent de choisir votre langue de l’application explicitement dans le cadre du programme d’installation).</span><span class="sxs-lookup"><span data-stu-id="a43c6-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="a43c6-160">Pour appliquer la langue de votre choix</span><span class="sxs-lookup"><span data-stu-id="a43c6-160">To apply your desired language</span></span>

1. <span data-ttu-id="a43c6-161">Passez en mode Administrateur.</span><span class="sxs-lookup"><span data-stu-id="a43c6-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="a43c6-162">Sélectionnez le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="a43c6-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="a43c6-163">Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="a43c6-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="a43c6-164">Sélectionnez **temps &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="a43c6-165">Sélectionnez **région &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="a43c6-166">Sélectionnez **Ajouter une langue**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="a43c6-167">Sélectionnez la langue que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="a43c6-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="a43c6-168">Sélectionnez la langue que vous venez d’ajouter à la liste « Langues ».</span><span class="sxs-lookup"><span data-stu-id="a43c6-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="a43c6-169">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="a43c6-170">Pour supprimer une langue :</span><span class="sxs-lookup"><span data-stu-id="a43c6-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="a43c6-p114">a. Sélectionnez la langue que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="a43c6-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="a43c6-p115">b. Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="a43c6-175">Lancez une invite de commande avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="a43c6-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="a43c6-176">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a43c6-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="a43c6-177">Redémarrez le système.</span><span class="sxs-lookup"><span data-stu-id="a43c6-177">Restart the system.</span></span>
    
<span data-ttu-id="a43c6-178">Langage de votre choix est désormais appliqué à la console de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a43c6-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="a43c6-179">Configurer initiale de la console</span><span class="sxs-lookup"><span data-stu-id="a43c6-179">Initial set up of the console</span></span>
<span data-ttu-id="a43c6-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-180"></span></span>

<span data-ttu-id="a43c6-181">Une fois que Windows est installé, l’application de console Microsoft équipes salles prendra son processus d’installation initial lors du démarrage suivant ou si l’option /reboot a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a43c6-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="a43c6-182">L’écran Compte d’utilisateur apparaît.</span><span class="sxs-lookup"><span data-stu-id="a43c6-182">The User Account screen appears.</span></span> <span data-ttu-id="a43c6-183">Entrez le Skype adresse de connexion (au format user@domain) du compte à utiliser avec la console de salle.</span><span class="sxs-lookup"><span data-stu-id="a43c6-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="a43c6-184">Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="a43c6-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="a43c6-185">Sous « Configurer le domaine », définir le nom de domaine complet de le Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="a43c6-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="a43c6-186">Si le Skype pour le domaine SIP de l’entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="a43c6-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="a43c6-187">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="a43c6-188">Sélectionnez les périphériques indiqués dans l’écran de fonctionnalités, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="a43c6-189">Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="a43c6-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="a43c6-190">Les appareils à sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="a43c6-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="a43c6-191">Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="a43c6-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="a43c6-192">Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences. </span><span class="sxs-lookup"><span data-stu-id="a43c6-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="a43c6-193">Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.</span><span class="sxs-lookup"><span data-stu-id="a43c6-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="a43c6-p119">Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="a43c6-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="a43c6-196">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a43c6-196">Click **Finish**.</span></span>
    
<span data-ttu-id="a43c6-197">L’application de console Microsoft équipes salles doit démarrer immédiatement la connexion à Skype pour Business Server avec les informations d’identification ci-dessus et doit également synchroniseront son calendrier avec Exchange à l’aide de ces mêmes informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="a43c6-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="a43c6-198">Pour plus d’informations sur l’utilisation de l’application de console, reportez-vous à l' [aide de salles d’équipes Microsoft](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="a43c6-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a43c6-199">Salles d’équipes Microsoft s’appuie sur la présence de matériel certifié console.</span><span class="sxs-lookup"><span data-stu-id="a43c6-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="a43c6-200">Même une image correctement créée contenant l’application de console Microsoft équipes salles ne démarre pas au-delà de la procédure d’installation initiale, sauf si le matériel de console est détecté.</span><span class="sxs-lookup"><span data-stu-id="a43c6-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="a43c6-201">Pour des solutions Surface Pro en fonction de la Surface Pro doit être connecté à son matériel ancrer accompagnement pour passer cette vérification.</span><span class="sxs-lookup"><span data-stu-id="a43c6-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a43c6-202">Certains utilisateurs non anglaises peut-être un clavier physique connecté à la console pendant l’installation initiale, dans le cas où les symboles ne sont pas pris en charge sur le clavier tactile.</span><span class="sxs-lookup"><span data-stu-id="a43c6-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="a43c6-203">Installer un certificat d’autorité de certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="a43c6-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="a43c6-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-204"></span></span>

<span data-ttu-id="a43c6-205">La console Microsoft équipes salles doit approuver les certificats utilisés par le Skype pour professionnels et les serveurs Exchange à que se connecte.</span><span class="sxs-lookup"><span data-stu-id="a43c6-205">The Microsoft Teams Rooms console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="a43c6-206">Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a43c6-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="a43c6-207">Dans un cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat dans la console Microsoft équipes salles de deux manières :</span><span class="sxs-lookup"><span data-stu-id="a43c6-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="a43c6-208">Vous pouvez participer à la console à Active Directory et qui ajoute automatiquement les certificats requis donnés de l’autorité de certification est publié dans Active Directory (option de déploiement normal).</span><span class="sxs-lookup"><span data-stu-id="a43c6-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="a43c6-209">Vous pouvez installer le certificat manuellement après le processus de création d’image.</span><span class="sxs-lookup"><span data-stu-id="a43c6-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="a43c6-210">Avant de le faire, vous devez effectuer le [paramétrage Initial de la console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="a43c6-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="a43c6-211">Pour installer manuellement le certificat </span><span class="sxs-lookup"><span data-stu-id="a43c6-211">To manually install the certificate</span></span>

1. <span data-ttu-id="a43c6-212">Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="a43c6-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="a43c6-213">Placez la console en mode admin (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="a43c6-213">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="a43c6-214">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a43c6-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="a43c6-215">Participer à un domaine Active Directory (facultatif)</span><span class="sxs-lookup"><span data-stu-id="a43c6-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="a43c6-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-216"></span></span>

<span data-ttu-id="a43c6-217">Vous pouvez joindre les consoles de salles d’équipes Microsoft pour votre domaine.</span><span class="sxs-lookup"><span data-stu-id="a43c6-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="a43c6-218">Consoles salles d’équipes Microsoft doivent être placés dans une unité d’organisation distincte à partir de stations de travail de votre PC, car le nombre de stratégies de station de travail n’est pas compatible avec Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="a43c6-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="a43c6-219">Un exemple courant sont les stratégies de mot de passe qui empêchent Microsoft équipes salles de démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a43c6-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="a43c6-220">Pour plus d’informations sur la gestion des paramètres de stratégie de groupe, reportez-vous à [Gérer les salles d’équipes Microsoft](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a43c6-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="a43c6-221">Pour participer à des salles d’équipes Microsoft à un domaine</span><span class="sxs-lookup"><span data-stu-id="a43c6-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="a43c6-222">Connexion à la console de l’administrateur de compte (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="a43c6-222">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="a43c6-223">Lancez l’invite de commande Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="a43c6-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="a43c6-224">Saisissez la commande suivante dans Powershell :</span><span class="sxs-lookup"><span data-stu-id="a43c6-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="a43c6-225">Par exemple, si votre nom de domaine complet est Redmond.corp.Microsoft.com et que vous souhaitez que vos consoles salles d’équipes Microsoft dans une unité d’organisation « Salles d’équipes Microsoft » qui est un enfant d’une unité d’organisation « ressources », la commande sera :</span><span class="sxs-lookup"><span data-stu-id="a43c6-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="a43c6-226">Si vous souhaitez renommer l’ordinateur lors de l’intégration à un domaine, utilisez l’indicateur - NewName suivi d’un nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a43c6-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="a43c6-227">Liste de vérification du déploiement Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="a43c6-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-228"></span></span>

<span data-ttu-id="a43c6-229">Utilisez la liste de vérification suivante tout en effectuant une vérification finale que la console et tous les périphériques sont configurées :</span><span class="sxs-lookup"><span data-stu-id="a43c6-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="a43c6-230">**Paramètres de l’application**</span><span class="sxs-lookup"><span data-stu-id="a43c6-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a43c6-231">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-231">☐</span></span>  <br/> |<span data-ttu-id="a43c6-232">Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.</span><span class="sxs-lookup"><span data-stu-id="a43c6-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="a43c6-233">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-233">☐</span></span>  <br/> |<span data-ttu-id="a43c6-234">Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).</span><span class="sxs-lookup"><span data-stu-id="a43c6-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="a43c6-235">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-235">☐</span></span>  <br/> |<span data-ttu-id="a43c6-236">Le mot de passe du compte de l’administrateur est défini et vérifié.</span><span class="sxs-lookup"><span data-stu-id="a43c6-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="a43c6-237">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-237">☐</span></span>  <br/> |<span data-ttu-id="a43c6-238">Toutes les mises à jour ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="a43c6-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="a43c6-239">**Périphériques audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="a43c6-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a43c6-240">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-240">☐</span></span>  <br/> |<span data-ttu-id="a43c6-241">La version du microprogramme de la caméra est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="a43c6-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="a43c6-242">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-242">☐</span></span>  <br/> |<span data-ttu-id="a43c6-243">Caméra fonctionnel et positionné de manière optimale</span><span class="sxs-lookup"><span data-stu-id="a43c6-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="a43c6-244">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-244">☐</span></span>  <br/> |<span data-ttu-id="a43c6-245">Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.</span><span class="sxs-lookup"><span data-stu-id="a43c6-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="a43c6-246">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-246">☐</span></span>  <br/> |<span data-ttu-id="a43c6-247">Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.</span><span class="sxs-lookup"><span data-stu-id="a43c6-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="a43c6-248">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-248">☐</span></span>  <br/> |<span data-ttu-id="a43c6-249">La version du microprogramme du périphérique audio est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="a43c6-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="a43c6-250">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-250">☐</span></span>  <br/> |<span data-ttu-id="a43c6-251">Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="a43c6-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="a43c6-252">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-252">☐</span></span>  <br/> |<span data-ttu-id="a43c6-253">Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="a43c6-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="a43c6-254">**Dock**</span><span class="sxs-lookup"><span data-stu-id="a43c6-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a43c6-255">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-255">☐</span></span>  <br/> |<span data-ttu-id="a43c6-256">Les câbles sont sécurisés et ne sont pas pincés.</span><span class="sxs-lookup"><span data-stu-id="a43c6-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="a43c6-257">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-257">☐</span></span>  <br/> |<span data-ttu-id="a43c6-258">La réception audio via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="a43c6-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="a43c6-259">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-259">☐</span></span>  <br/> |<span data-ttu-id="a43c6-260">La réception vidéo via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="a43c6-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="a43c6-261">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-261">☐</span></span>  <br/> |<span data-ttu-id="a43c6-262">Le dock peut pivoter librement.</span><span class="sxs-lookup"><span data-stu-id="a43c6-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="a43c6-263">☐</span><span class="sxs-lookup"><span data-stu-id="a43c6-263">☐</span></span>  <br/> |<span data-ttu-id="a43c6-264">La luminosité de l’affichage est acceptable pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="a43c6-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a43c6-265">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a43c6-265">See also</span></span>
<span data-ttu-id="a43c6-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c6-266"></span></span>

[<span data-ttu-id="a43c6-267">Planifier des équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-267">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="a43c6-268">Déployer les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="a43c6-269">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="a43c6-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="a43c6-270">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a43c6-270">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
