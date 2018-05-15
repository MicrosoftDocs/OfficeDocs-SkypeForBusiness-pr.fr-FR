---
title: Configuration d’une console Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit l’installation de la console Skype Room Systems v2 et de ses périphériques.
ms.openlocfilehash: b82343f98304b0607bb3525b508aecf81e80a031
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="baa2f-103">Configuration d’une console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="baa2f-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="baa2f-104">Cet article décrit l’installation de la console Skype Room Systems v2 et de ses périphériques.</span><span class="sxs-lookup"><span data-stu-id="baa2f-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="baa2f-105">Vous devez uniquement effectuer ces étapes si la Skype nécessaire pour les comptes d’entreprise et Exchange ont déjà créé et testé comme décrit dans [déployer Skype salle systèmes v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="baa2f-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="baa2f-106">Vous devez le matériel et les logiciels décrits dans [v2 Skype salle requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baa2f-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="baa2f-107">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="baa2f-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="baa2f-108">Préparation de l’image d’installation</span><span class="sxs-lookup"><span data-stu-id="baa2f-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="baa2f-109">Installer un certificat d’autorité de certification privé sur le périphérique tablette</span><span class="sxs-lookup"><span data-stu-id="baa2f-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="baa2f-110">Installer Windows 10 et l’application de console Skype salle systèmes v2</span><span class="sxs-lookup"><span data-stu-id="baa2f-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="baa2f-111">Configurer initiale de la Console</span><span class="sxs-lookup"><span data-stu-id="baa2f-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="baa2f-112">Salle Skype systèmes v2 de pré-déploiement</span><span class="sxs-lookup"><span data-stu-id="baa2f-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="baa2f-113">Systèmes de salle Skype v2 fonctionne uniquement dans un Skype correctement configurée pour un environnement d’entreprise où les comptes de périphériques sont correctement configurés comme décrit dans [déployer Skype salle systèmes v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="baa2f-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="baa2f-114">Préparation de l’image d’installation</span><span class="sxs-lookup"><span data-stu-id="baa2f-114">Prepare the installation image</span></span>
<span data-ttu-id="baa2f-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-115"></span></span>

<span data-ttu-id="baa2f-116">Installation de l’application de v2 de systèmes de salle Skype sur une Surface Pro 4 ou Surface Pro requiert un périphérique de stockage USB avec au moins 32 Go de mémoire en un disque FAT32.</span><span class="sxs-lookup"><span data-stu-id="baa2f-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="baa2f-117">Il ne doit y avoir aucun autre fichier sur l’appareil, les fichiers existants sur le stockage USB seront perdues.</span><span class="sxs-lookup"><span data-stu-id="baa2f-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="baa2f-118">Si vous ne créez pas l’image de votre console conformément à ces instructions, cela entraînera probablement un comportement inattendu.</span><span class="sxs-lookup"><span data-stu-id="baa2f-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="baa2f-119">Mise à jour Windows 10 entreprise anniversaire (Version 1607) n’est plus pris en charge pour la création de systèmes de salle Skype v2 image.</span><span class="sxs-lookup"><span data-stu-id="baa2f-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="baa2f-120">Un v2 Skype salle systèmes existants avec 10 entreprise anniversaire mise à jour Windows déplacement vers les systèmes de salle Skype v2 mise à jour 3 par l’entremise du Windows Store fonctionnera, mais une nouvelle installation doit être effectuée comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="baa2f-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="baa2f-121">Télécharger le [package MSU pour KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span><span class="sxs-lookup"><span data-stu-id="baa2f-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="baa2f-122">Télécharger le [script CreateSrsMedia.ps1](room-systems-v2-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="baa2f-122">Download the [CreateSrsMedia.ps1 script](room-systems-v2-scripts.md).</span></span>
3. <span data-ttu-id="baa2f-123">Placez la MSU pour KB4056892 dans le même répertoire que le script CreateSrsMedia.ps1.</span><span class="sxs-lookup"><span data-stu-id="baa2f-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="baa2f-124">Exécutez le script CreateSrsMedia.ps1 à partir d’une invite de commandes avec élévation de privilèges sur un ordinateur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="baa2f-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="baa2f-125">Suivez les instructions du script pour créer un disque d’installation de systèmes de salle Skype v2 USB.</span><span class="sxs-lookup"><span data-stu-id="baa2f-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="baa2f-126">Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [10 de Windows Installer et de l’application de console Skype salle systèmes v2 ](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="baa2f-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="baa2f-127">Installation de Windows 10 et de l’application de console Skype Room Systems v2 </span><span class="sxs-lookup"><span data-stu-id="baa2f-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="baa2f-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-128"></span></span>

<span data-ttu-id="baa2f-129">Vous devrez désormais appliquer l’image que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="baa2f-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="baa2f-130">La tablette s’exécute en tant qu’un matériel et l’utilisateur par défaut sera définie ne s’exécute l’application v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="baa2f-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="baa2f-131">La tablette doit être connectée à une source d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="baa2f-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="baa2f-132">Commencez par l’arrêter complètement.</span><span class="sxs-lookup"><span data-stu-id="baa2f-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="baa2f-133">Si nécessaire, appuyez sur le bouton d’alimentation et maintenez-le enfoncé jusqu’à ce que la tablette s’éteigne.</span><span class="sxs-lookup"><span data-stu-id="baa2f-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="baa2f-134">Connectez votre disque USB d’installation à la tablette.</span><span class="sxs-lookup"><span data-stu-id="baa2f-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="baa2f-135">Appuyez sur le bouton de diminution du volume (-) de la tablette et maintenez-le enfoncé.</span><span class="sxs-lookup"><span data-stu-id="baa2f-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="baa2f-136">Appuyez sur le bouton d’alimentation de la tablette, puis relâchez-le.</span><span class="sxs-lookup"><span data-stu-id="baa2f-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="baa2f-137">Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).</span><span class="sxs-lookup"><span data-stu-id="baa2f-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="baa2f-138">Le système s’arrêtera une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="baa2f-138">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="baa2f-139">Une fois que le système est arrêté, il est recommandé supprimer le disque du programme d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="baa2f-139">After the system has shut down, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="baa2f-140">À ce stade, vous pouvez placer la tablette dans le dock et connecter les périphériques requis pour votre salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="baa2f-140">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="baa2f-141">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="baa2f-141">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="baa2f-142">Sélection de la langue pour la mise à jour de Creator</span><span class="sxs-lookup"><span data-stu-id="baa2f-142">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="baa2f-143">Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de la langue implicite ne fournit pas l’utilisateur dont la langue de l’application réelle qu’ils souhaitent (par exemple, ils que l’application doit s’afficher dans le Français, mais il est élaboration en anglais).</span><span class="sxs-lookup"><span data-stu-id="baa2f-143">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="baa2f-144">Les instructions suivantes s'appliquent aux périphériques créés à l'aide de la mise à jour de Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="baa2f-144">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="baa2f-145">Les systèmes hérités/commercialisés qui n'ont pas fait correctement l'objet d'une nouvelle image pour leur nouveau système de provisionnement ne pourront pas utiliser ces instructions, mais ne requièrent pas une intervention manuelle (La version anniversaire vous permet de sélectionner la langue de l'application lors de la configuration.).</span><span class="sxs-lookup"><span data-stu-id="baa2f-145">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="baa2f-146">Pour appliquer la langue de votre choix</span><span class="sxs-lookup"><span data-stu-id="baa2f-146">To apply your desired language</span></span>

1. <span data-ttu-id="baa2f-147">Passez en mode Administrateur.</span><span class="sxs-lookup"><span data-stu-id="baa2f-147">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="baa2f-148">Sélectionnez le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="baa2f-148">Select the Start menu.</span></span>
    
3. <span data-ttu-id="baa2f-149">Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="baa2f-149">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="baa2f-150">Sélectionnez **temps &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-150">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="baa2f-151">Sélectionnez **région &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-151">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="baa2f-152">Sélectionnez **Ajouter une langue**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-152">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="baa2f-153">Sélectionnez la langue que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="baa2f-153">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="baa2f-154">Sélectionnez la langue que vous venez d’ajouter à la liste « Langues ».</span><span class="sxs-lookup"><span data-stu-id="baa2f-154">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="baa2f-155">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-155">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="baa2f-156">Pour supprimer une langue :</span><span class="sxs-lookup"><span data-stu-id="baa2f-156">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="baa2f-157">a.</span><span class="sxs-lookup"><span data-stu-id="baa2f-157">a.</span></span> <span data-ttu-id="baa2f-158">Sélectionnez la langue que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="baa2f-158">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="baa2f-159">b.</span><span class="sxs-lookup"><span data-stu-id="baa2f-159">b.</span></span> <span data-ttu-id="baa2f-160">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-160">Select **Remove**.</span></span>
    
11. <span data-ttu-id="baa2f-161">Lancez une invite de commande avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="baa2f-161">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="baa2f-162">Exécutez la commande suivante : </span><span class="sxs-lookup"><span data-stu-id="baa2f-162">Run the following command:</span></span> 
    
    <span data-ttu-id="baa2f-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="baa2f-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="baa2f-164">Redémarrez le système.</span><span class="sxs-lookup"><span data-stu-id="baa2f-164">Restart the system.</span></span>
    
<span data-ttu-id="baa2f-165">Langage de votre choix est désormais appliqué au périphérique v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="baa2f-165">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="baa2f-166">Configuration initiale de la console </span><span class="sxs-lookup"><span data-stu-id="baa2f-166">Initial set up of the Console</span></span>
<span data-ttu-id="baa2f-167"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-167"></span></span>

<span data-ttu-id="baa2f-168">Une fois que Windows est installé, l’application v2 de systèmes de salle Skype prendra son processus d’installation initial lors du démarrage suivant ou si l’option /reboot a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="baa2f-168">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="baa2f-p111">L’écran Compte d’utilisateur apparaît. Saisissez l’adresse de connexion Skype (au format utilisateur@domaine) du compte de la salle qui sera utilisé avec l’appareil.</span><span class="sxs-lookup"><span data-stu-id="baa2f-p111">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="baa2f-171">Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="baa2f-171">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="baa2f-172">Sous « Configurer le domaine », définir le nom de domaine complet de le Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="baa2f-172">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="baa2f-173">Si le Skype pour le domaine SIP de l’entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="baa2f-173">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="baa2f-174">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-174">Click **Next**.</span></span>
    
5. <span data-ttu-id="baa2f-175">Sélectionnez les périphériques indiqués dans l’écran de fonctionnalités, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-175">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="baa2f-176">Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="baa2f-176">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="baa2f-177">Les appareils à sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="baa2f-177">The devices to select are:</span></span>
    
   - <span data-ttu-id="baa2f-178">Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="baa2f-178">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="baa2f-179">Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences. </span><span class="sxs-lookup"><span data-stu-id="baa2f-179">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="baa2f-180">Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.</span><span class="sxs-lookup"><span data-stu-id="baa2f-180">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="baa2f-p114">Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="baa2f-p114">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="baa2f-183">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="baa2f-183">Click **Finish**.</span></span>
    
<span data-ttu-id="baa2f-184">L’application doit démarrer immédiatement la connexion à Skype pour Business Server 2015 avec les informations d’identification ci-dessus et doit également synchroniseront son calendrier avec Exchange à l’aide de ces mêmes informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="baa2f-184">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="baa2f-185">Pour plus d’informations sur l’utilisation de l’application, reportez-vous à l' [aide de systèmes de salle Skype version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="baa2f-185">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="baa2f-186">Systèmes de salle Skype v2 s’appuie sur la présence de matériel de console certifié (la Logitech SmartDock).</span><span class="sxs-lookup"><span data-stu-id="baa2f-186">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="baa2f-187">Même une image correctement créé qui contient l’application v2 de systèmes de salle Skype chargée sur une Surface Pro 4 ou Surface Pro ne démarre pas au-delà de la procédure d’installation initiale, sauf si le matériel de console est détecté.</span><span class="sxs-lookup"><span data-stu-id="baa2f-187">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="baa2f-188">Certains utilisateurs non anglophones auront peut-être besoin d’un clavier physique connecté à la console lors de l’installation initiale.</span><span class="sxs-lookup"><span data-stu-id="baa2f-188">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="baa2f-189">Installation d’un certificat d’une autorité de certification privée sur la tablette</span><span class="sxs-lookup"><span data-stu-id="baa2f-189">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="baa2f-190"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-190"></span></span>

<span data-ttu-id="baa2f-191">L’appareil de v2 Skype salle systèmes doit approuver les certificats utilisés par le Skype pour professionnels et les serveurs Exchange à que se connecte.</span><span class="sxs-lookup"><span data-stu-id="baa2f-191">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="baa2f-192">Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10.</span><span class="sxs-lookup"><span data-stu-id="baa2f-192">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="baa2f-193">Dans un cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat au périphérique v2 Skype salle systèmes de deux façons :</span><span class="sxs-lookup"><span data-stu-id="baa2f-193">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="baa2f-194">Vous pouvez connecter l’appareil à Active Directory qui ajoutera automatiquement les certificats requis, car l’autorité de certification est publiée dans Active Directory (option de déploiement ordinaire).</span><span class="sxs-lookup"><span data-stu-id="baa2f-194">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="baa2f-p118">Vous pouvez installer le certificat manuellement après le processus de création d’image. Avant cela, vous devez terminer la [configuration initiale de la console ](console.md#Initial). </span><span class="sxs-lookup"><span data-stu-id="baa2f-p118">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="baa2f-197">Pour installer manuellement le certificat </span><span class="sxs-lookup"><span data-stu-id="baa2f-197">To manually install the certificate</span></span>

1. <span data-ttu-id="baa2f-198">Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="baa2f-198">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="baa2f-199">Placez la surface d’exposition de 4 en mode admin (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="baa2f-199">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="baa2f-200">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="baa2f-200">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="baa2f-201">Joindre un domaine Active Directory (facultatif)</span><span class="sxs-lookup"><span data-stu-id="baa2f-201">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="baa2f-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-202"></span></span>

<span data-ttu-id="baa2f-203">Vous pouvez participer à des périphériques v2 de systèmes de salle Skype à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="baa2f-203">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="baa2f-204">Les appareils v2 Skype salle systèmes doivent être placés dans une unité d’organisation distincte à partir de stations de travail de votre PC, car le nombre de stratégies de station de travail n’est pas compatible avec les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="baa2f-204">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="baa2f-205">Un exemple courant sont les stratégies de mot de passe qui empêchent Skype salle systèmes v2 de démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="baa2f-205">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="baa2f-206">Pour plus d’informations sur la gestion des paramètres de stratégie de groupe, reportez-vous à [Gérer les systèmes de salle Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="baa2f-206">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="baa2f-207">Pour joindre Skype Room Systems v2 à un domaine</span><span class="sxs-lookup"><span data-stu-id="baa2f-207">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="baa2f-208">Connexion à la console de l’administrateur de compte (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="baa2f-208">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="baa2f-209">Lancez l’invite de commande Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="baa2f-209">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="baa2f-210">Saisissez la commande suivante dans Powershell :</span><span class="sxs-lookup"><span data-stu-id="baa2f-210">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="baa2f-211">Par exemple, si votre nom de domaine complet est Redmond.corp.Microsoft.com et vous souhaitez que vos périphériques v2 de systèmes de salle Skype dans une « salle Skype systèmes v2 » unité d’organisation qui est un enfant d’une unité d’organisation « ressources », la commande sera :</span><span class="sxs-lookup"><span data-stu-id="baa2f-211">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="baa2f-212">Si vous souhaitez renommer l’ordinateur lors de l’intégration à un domaine, utilisez l’indicateur - NewName suivi d’un nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="baa2f-212">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="baa2f-213">Liste de vérification du déploiement de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="baa2f-213">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="baa2f-214"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-214"></span></span>

<span data-ttu-id="baa2f-215">Utilisez la liste de vérification suivante lors de la vérification finale de la configuration complète de la console et de ses périphériques :</span><span class="sxs-lookup"><span data-stu-id="baa2f-215">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="baa2f-216">**Paramètres de l’application**</span><span class="sxs-lookup"><span data-stu-id="baa2f-216">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="baa2f-217">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-217">☐</span></span>  <br/> |<span data-ttu-id="baa2f-218">Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.</span><span class="sxs-lookup"><span data-stu-id="baa2f-218">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="baa2f-219">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-219">☐</span></span>  <br/> |<span data-ttu-id="baa2f-220">Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).</span><span class="sxs-lookup"><span data-stu-id="baa2f-220">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="baa2f-221">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-221">☐</span></span>  <br/> |<span data-ttu-id="baa2f-222">Le mot de passe du compte de l’administrateur est défini et vérifié.</span><span class="sxs-lookup"><span data-stu-id="baa2f-222">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="baa2f-223">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-223">☐</span></span>  <br/> |<span data-ttu-id="baa2f-224">Toutes les mises à jour de Surface Pro 4 ou Surface Pro Systems ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="baa2f-224">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="baa2f-225">**Périphériques audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="baa2f-225">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="baa2f-226">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-226">☐</span></span>  <br/> |<span data-ttu-id="baa2f-227">La version du microprogramme de la caméra est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="baa2f-227">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="baa2f-228">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-228">☐</span></span>  <br/> |<span data-ttu-id="baa2f-229">Caméra fonctionnel et positionné de manière optimale</span><span class="sxs-lookup"><span data-stu-id="baa2f-229">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="baa2f-230">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-230">☐</span></span>  <br/> |<span data-ttu-id="baa2f-231">Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.</span><span class="sxs-lookup"><span data-stu-id="baa2f-231">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="baa2f-232">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-232">☐</span></span>  <br/> |<span data-ttu-id="baa2f-233">Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.</span><span class="sxs-lookup"><span data-stu-id="baa2f-233">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="baa2f-234">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-234">☐</span></span>  <br/> |<span data-ttu-id="baa2f-235">La version du microprogramme du périphérique audio est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="baa2f-235">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="baa2f-236">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-236">☐</span></span>  <br/> |<span data-ttu-id="baa2f-237">Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="baa2f-237">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="baa2f-238">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-238">☐</span></span>  <br/> |<span data-ttu-id="baa2f-239">Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="baa2f-239">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="baa2f-240">**Station d’accueil**</span><span class="sxs-lookup"><span data-stu-id="baa2f-240">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="baa2f-241">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-241">☐</span></span>  <br/> |<span data-ttu-id="baa2f-242">Les câbles sont sécurisés et ne sont pas pincés.</span><span class="sxs-lookup"><span data-stu-id="baa2f-242">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="baa2f-243">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-243">☐</span></span>  <br/> |<span data-ttu-id="baa2f-244">La réception audio via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="baa2f-244">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="baa2f-245">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-245">☐</span></span>  <br/> |<span data-ttu-id="baa2f-246">La réception vidéo via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="baa2f-246">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="baa2f-247">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-247">☐</span></span>  <br/> |<span data-ttu-id="baa2f-248">Le dock peut pivoter librement.</span><span class="sxs-lookup"><span data-stu-id="baa2f-248">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="baa2f-249">☐</span><span class="sxs-lookup"><span data-stu-id="baa2f-249">☐</span></span>  <br/> |<span data-ttu-id="baa2f-250">La luminosité de l’affichage est acceptable pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="baa2f-250">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="baa2f-251">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="baa2f-251">See also</span></span>
<span data-ttu-id="baa2f-252"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="baa2f-252"></span></span>

#### 

[<span data-ttu-id="baa2f-253">Planifier la salle Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="baa2f-253">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="baa2f-254">Déployer la salle Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="baa2f-254">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="baa2f-255">Configurer une console v2 de systèmes de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="baa2f-255">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="baa2f-256">Gérer les salles Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="baa2f-256">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

