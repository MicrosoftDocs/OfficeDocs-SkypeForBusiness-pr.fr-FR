---
title: Configuration d’une console Skype Room Systems v2
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article explique comment configurer la console v2 Skype salle systèmes et périphériques.
ms.openlocfilehash: 4218365e7cb4b396d3e93d3fa969546138ace33d
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716373"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="11961-103">Configuration d’une console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="11961-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="11961-104">Cet article explique comment configurer la console v2 Skype salle systèmes et périphériques.</span><span class="sxs-lookup"><span data-stu-id="11961-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="11961-105">Vous devez uniquement effectuer ces étapes si la Skype nécessaire pour les comptes d’entreprise et Exchange ont déjà créé et testé comme décrit dans [déployer Skype salle systèmes v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="11961-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="11961-106">Vous devez le matériel et les logiciels décrits dans [v2 Skype salle requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11961-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="11961-107">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="11961-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="11961-108">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="11961-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="11961-109">Installer un certificat d’autorité de certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="11961-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="11961-110">Installation de Windows 10 et de l’application de console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="11961-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="11961-111">Configurer initiale de la console</span><span class="sxs-lookup"><span data-stu-id="11961-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="11961-112">Liste de vérification de déploiement de systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="11961-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="11961-113">Systèmes de salle Skype v2 fonctionne uniquement dans un Skype correctement configurée pour un environnement d’entreprise où les comptes de périphériques sont correctement configurés comme décrit dans [déployer Skype salle systèmes v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="11961-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="11961-114">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="11961-114">Prepare the installation media</span></span>
<span data-ttu-id="11961-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-115"></span></span>

<span data-ttu-id="11961-116">Installation de l’application de console Skype salle systèmes v2 requiert un périphérique de stockage USB avec au moins 32 Go de mémoire en un disque FAT32.</span><span class="sxs-lookup"><span data-stu-id="11961-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="11961-117">Il ne doit y avoir aucun fichier sur le dispositif de stockage USB, car ceux-ci seraient perdus.</span><span class="sxs-lookup"><span data-stu-id="11961-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11961-118">Impossible de créer votre support d’installation v2 Skype salle systèmes en fonction de ces instructions aura un comportement inattendu.</span><span class="sxs-lookup"><span data-stu-id="11961-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="11961-119">Mise à jour Windows 10 entreprise anniversaire (Version 1607) est plus pris en charge pour la création de systèmes de salle Skype v2 installation multimédia.</span><span class="sxs-lookup"><span data-stu-id="11961-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>

> [!NOTE]
> <span data-ttu-id="11961-120">Un v2 Skype salle systèmes existants avec Windows 10 entreprise déplacement vers les systèmes de salle Skype v2 mise à jour 3 par l’entremise du Windows Store fonctionnera, mais une nouvelle installation doit être effectuée comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="11961-120">An existing Skype Room Systems v2 with Windows 10 Enterprise moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span>
  
1. <span data-ttu-id="11961-121">Télécharger le script [CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842). </span><span class="sxs-lookup"><span data-stu-id="11961-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="11961-122">(Facultatif) Téléchargez et placer les fichiers CAB du pack langue de votre choix dans le même répertoire que le script.</span><span class="sxs-lookup"><span data-stu-id="11961-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="11961-123">Le script indique où vous pouvez télécharger les fichiers de pack de langue appropriés pour le type de média que vous créez, si vous ne savez pas où se procurer les modules linguistiques de.</span><span class="sxs-lookup"><span data-stu-id="11961-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="11961-124">Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="11961-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>

<span data-ttu-id="11961-125">Suivez les instructions du script pour créer un disque d’installation de systèmes de salle Skype v2 USB.</span><span class="sxs-lookup"><span data-stu-id="11961-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="11961-126">Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [10 de Windows Installer et de l’application de console Skype salle systèmes v2](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="11961-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

> [!TIP]
> <span data-ttu-id="11961-127">Vous avez sans doute remarqué que nous n’appelons plus des versions spécifiques de pilotes, les systèmes de salle Skype v2 client ou Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="11961-127">You might have noticed that we no longer call out specific versions of the drivers, Skype Room Systems v2 client, or Windows 10 Enterprise.</span></span> <span data-ttu-id="11961-128">Il s’agit intentionnelle, nous voulons le script pour associer et de vérifier la compatibilité pour tous les programmes d’installation.</span><span class="sxs-lookup"><span data-stu-id="11961-128">This is deliberate, we want the script to match and verify compatibility for all installers.</span></span> <span data-ttu-id="11961-129">Le script et automatiquement obtenir les outils nécessaires pour une configuration prises en charge.</span><span class="sxs-lookup"><span data-stu-id="11961-129">The script will automatically find and get what it needs for a supported configuration.</span></span>  
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="11961-130">Installation de Windows 10 et de l’application de console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="11961-130">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="11961-131"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-131"></span></span>

<span data-ttu-id="11961-132">Vous devez maintenant appliquer le support d’installation que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="11961-132">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="11961-133">Le périphérique cible s’exécute en tant qu’un matériel et l’utilisateur par défaut sera définie ne s’exécute l’application de console Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="11961-133">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="11961-134">Si l’équipement est installé dans une station d’accueil (par exemple, une Surface Pro), le déconnecter de la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="11961-134">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="11961-135">Vérifiez que le périphérique cible n’est pas connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="11961-135">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="11961-136">Vérifiez que l’équipement est connecté au secteur.</span><span class="sxs-lookup"><span data-stu-id="11961-136">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="11961-137">Branchez votre disque d’installation USB sur le périphérique cible.</span><span class="sxs-lookup"><span data-stu-id="11961-137">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="11961-138">Démarrez le disque d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="11961-138">Boot to the USB setup disk.</span></span> <span data-ttu-id="11961-139">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="11961-139">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="11961-140">Si votre périphérique cible est une Surface Pro, procédez comme suit pour démarrer sur le disque d’installation USB :</span><span class="sxs-lookup"><span data-stu-id="11961-140">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="11961-141">Appuyez sur et maintenez le volume vers le bas du bouton (-).</span><span class="sxs-lookup"><span data-stu-id="11961-141">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="11961-142">Appuyez puis relâchez le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="11961-142">Press and release the power button.</span></span>

    3. <span data-ttu-id="11961-143">Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).</span><span class="sxs-lookup"><span data-stu-id="11961-143">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="11961-144">Le système s’arrêtera une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="11961-144">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="11961-145">Une fois que le système est arrêté, il est recommandé supprimer le disque du programme d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="11961-145">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="11961-146">À ce stade, vous pourrez placer le périphérique cible dans sa station d’accueil (si vous utilisez un produit basé sur une station d’accueil), attacher les périphériques nécessaires pour votre salle de réunion et connexion au réseau.</span><span class="sxs-lookup"><span data-stu-id="11961-146">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="11961-147">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="11961-147">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="11961-148">Sélection d’une langue</span><span class="sxs-lookup"><span data-stu-id="11961-148">Selecting a language</span></span> 

<span data-ttu-id="11961-149">Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de la langue implicite ne fournit pas l’utilisateur dont la langue de l’application réelle qu’ils souhaitent (par exemple, qu’ils souhaitent l’application de console pour élaborer en Français, mais elle suit en anglais).</span><span class="sxs-lookup"><span data-stu-id="11961-149">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="11961-150">Les instructions suivantes s’appliquent uniquement pour les consoles créées à l’aide de la mise à jour du créateur de Windows.</span><span class="sxs-lookup"><span data-stu-id="11961-150">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="11961-151">Systèmes hérité/dans-marché qui n’ont pas été définies à l’aide des supports avec le nouveau système de mise en service ne sera pas en mesure d’utiliser ces instructions, mais doit également préférable de l’émission initiale qui nécessite une intervention manuelle cette (Édition anniversaire vous permettent de choisir votre langue de l’application explicitement dans le cadre du programme d’installation).</span><span class="sxs-lookup"><span data-stu-id="11961-151">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="11961-152">Pour appliquer la langue de votre choix</span><span class="sxs-lookup"><span data-stu-id="11961-152">To apply your desired language</span></span>

1. <span data-ttu-id="11961-153">Passez en mode Administrateur.</span><span class="sxs-lookup"><span data-stu-id="11961-153">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="11961-154">Sélectionnez le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="11961-154">Select the Start menu.</span></span>
    
3. <span data-ttu-id="11961-155">Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="11961-155">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="11961-156">Sélectionnez **temps &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="11961-156">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="11961-157">Sélectionnez **région &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="11961-157">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="11961-158">Sélectionnez **Ajouter une langue**.</span><span class="sxs-lookup"><span data-stu-id="11961-158">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="11961-159">Sélectionnez la langue que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="11961-159">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="11961-160">Sélectionnez la langue que vous venez d’ajouter à la liste « Langues ».</span><span class="sxs-lookup"><span data-stu-id="11961-160">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="11961-161">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="11961-161">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="11961-162">Pour supprimer une langue :</span><span class="sxs-lookup"><span data-stu-id="11961-162">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="11961-p111">a. Sélectionnez la langue que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="11961-p111">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="11961-p112">b. Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="11961-p112">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="11961-167">Lancez une invite de commande avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="11961-167">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="11961-168">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="11961-168">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="11961-169">Redémarrez le système.</span><span class="sxs-lookup"><span data-stu-id="11961-169">Restart the system.</span></span>
    
<span data-ttu-id="11961-170">Langage de votre choix est désormais appliqué à la console de v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="11961-170">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="11961-171">Configurer initiale de la console</span><span class="sxs-lookup"><span data-stu-id="11961-171">Initial set up of the console</span></span>
<span data-ttu-id="11961-172"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-172"></span></span>

<span data-ttu-id="11961-173">Une fois que Windows est installé, l’application de console v2 Skype salle systèmes passe en son processus d’installation initial lors du démarrage suivant ou si l’option /reboot a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="11961-173">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="11961-174">L’écran Compte d’utilisateur apparaît.</span><span class="sxs-lookup"><span data-stu-id="11961-174">The User Account screen appears.</span></span> <span data-ttu-id="11961-175">Entrez le Skype adresse de connexion (au format user@domain) du compte à utiliser avec la console de salle.</span><span class="sxs-lookup"><span data-stu-id="11961-175">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="11961-176">Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="11961-176">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="11961-177">Sous « Configurer le domaine », définir le nom de domaine complet de le Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="11961-177">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="11961-178">Si le Skype pour le domaine SIP de l’entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="11961-178">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="11961-179">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="11961-179">Click **Next**.</span></span>
    
5. <span data-ttu-id="11961-180">Sélectionnez les périphériques indiqués dans l’écran de fonctionnalités, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="11961-180">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="11961-181">Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="11961-181">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="11961-182">Les appareils à sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="11961-182">The devices to select are:</span></span>
    
   - <span data-ttu-id="11961-183">Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="11961-183">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="11961-184">Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences. </span><span class="sxs-lookup"><span data-stu-id="11961-184">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="11961-185">Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.</span><span class="sxs-lookup"><span data-stu-id="11961-185">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="11961-p116">Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="11961-p116">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="11961-188">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="11961-188">Click **Finish**.</span></span>
    
<span data-ttu-id="11961-189">L’application de console v2 Skype salle systèmes doit démarrer immédiatement la connexion à Skype pour Business Server avec les informations d’identification ci-dessus et doit également synchroniseront son calendrier avec Exchange à l’aide de ces mêmes informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="11961-189">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="11961-190">Pour plus d’informations sur l’utilisation de l’application de console, reportez-vous à l' [aide de systèmes de salle Skype version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="11961-190">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="11961-191">Systèmes de salle Skype v2 s’appuie sur la présence de matériel certifié console.</span><span class="sxs-lookup"><span data-stu-id="11961-191">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="11961-192">Même une image correctement créée contenant l’application de console Skype salle systèmes v2 ne démarre pas au-delà de la procédure d’installation initiale, sauf si le matériel de console est détecté.</span><span class="sxs-lookup"><span data-stu-id="11961-192">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="11961-193">Pour des solutions Surface Pro en fonction de la Surface Pro doit être connecté à son matériel ancrer accompagnement pour passer cette vérification.</span><span class="sxs-lookup"><span data-stu-id="11961-193">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11961-194">Certains utilisateurs non anglaises peut-être un clavier physique connecté à la console pendant l’installation initiale, dans le cas où les symboles ne sont pas pris en charge sur le clavier tactile.</span><span class="sxs-lookup"><span data-stu-id="11961-194">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="11961-195">Installer un certificat d’autorité de certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="11961-195">Install a private CA certificate on the console</span></span>
<span data-ttu-id="11961-196"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-196"></span></span>

<span data-ttu-id="11961-197">La console de v2 Skype salle systèmes doit approuver les certificats utilisés par le Skype pour professionnels et les serveurs Exchange à que se connecte.</span><span class="sxs-lookup"><span data-stu-id="11961-197">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="11961-198">Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10.</span><span class="sxs-lookup"><span data-stu-id="11961-198">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="11961-199">Dans un cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat dans la console de v2 Skype salle systèmes de deux façons :</span><span class="sxs-lookup"><span data-stu-id="11961-199">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="11961-200">Vous pouvez participer à la console à Active Directory et qui ajoute automatiquement les certificats requis donnés de l’autorité de certification est publié dans Active Directory (option de déploiement normal).</span><span class="sxs-lookup"><span data-stu-id="11961-200">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="11961-201">Vous pouvez installer le certificat manuellement après le processus de création d’image.</span><span class="sxs-lookup"><span data-stu-id="11961-201">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="11961-202">Avant de le faire, vous devez effectuer le [paramétrage Initial de la console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="11961-202">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="11961-203">Pour installer manuellement le certificat </span><span class="sxs-lookup"><span data-stu-id="11961-203">To manually install the certificate</span></span>

1. <span data-ttu-id="11961-204">Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="11961-204">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="11961-205">Placez la console en mode admin (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="11961-205">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="11961-206">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="11961-206">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="11961-207">Participer à un domaine Active Directory (facultatif)</span><span class="sxs-lookup"><span data-stu-id="11961-207">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="11961-208"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-208"></span></span>

<span data-ttu-id="11961-209">Vous pouvez joindre les consoles v2 de systèmes de salle Skype à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="11961-209">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="11961-210">Consoles v2 de systèmes de salle Skype doivent être placés dans une unité d’organisation distincte à partir de stations de travail de votre PC, car le nombre de stratégies de station de travail n’est pas compatible avec les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="11961-210">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="11961-211">Un exemple courant sont les stratégies de mot de passe qui empêchent Skype salle systèmes v2 de démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="11961-211">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="11961-212">Pour plus d’informations sur la gestion des paramètres de stratégie de groupe, reportez-vous à [Gérer les systèmes de salle Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="11961-212">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="11961-213">Pour joindre Skype Room Systems v2 à un domaine</span><span class="sxs-lookup"><span data-stu-id="11961-213">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="11961-214">Connexion à la console de l’administrateur de compte (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="11961-214">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="11961-215">Lancez l’invite de commande Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="11961-215">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="11961-216">Saisissez la commande suivante dans Powershell :</span><span class="sxs-lookup"><span data-stu-id="11961-216">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="11961-217">Par exemple, si votre nom de domaine complet est Redmond.corp.Microsoft.com et vous souhaitez que vos consoles v2 de Skype salle systèmes dans une « salle Skype systèmes v2 » unité d’organisation qui est un enfant d’une unité d’organisation « ressources », la commande sera :</span><span class="sxs-lookup"><span data-stu-id="11961-217">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="11961-218">Si vous souhaitez renommer l’ordinateur lors de l’intégration à un domaine, utilisez l’indicateur - NewName suivi d’un nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="11961-218">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="11961-219">Liste de vérification de déploiement de systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="11961-219">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="11961-220"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-220"></span></span>

<span data-ttu-id="11961-221">Utilisez la liste de vérification suivante tout en effectuant une vérification finale que la console et tous les périphériques sont configurées :</span><span class="sxs-lookup"><span data-stu-id="11961-221">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="11961-222">**Paramètres de l’application**</span><span class="sxs-lookup"><span data-stu-id="11961-222">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11961-223">☐</span><span class="sxs-lookup"><span data-stu-id="11961-223">☐</span></span>  <br/> |<span data-ttu-id="11961-224">Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.</span><span class="sxs-lookup"><span data-stu-id="11961-224">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="11961-225">☐</span><span class="sxs-lookup"><span data-stu-id="11961-225">☐</span></span>  <br/> |<span data-ttu-id="11961-226">Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).</span><span class="sxs-lookup"><span data-stu-id="11961-226">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="11961-227">☐</span><span class="sxs-lookup"><span data-stu-id="11961-227">☐</span></span>  <br/> |<span data-ttu-id="11961-228">Le mot de passe du compte de l’administrateur est défini et vérifié.</span><span class="sxs-lookup"><span data-stu-id="11961-228">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="11961-229">☐</span><span class="sxs-lookup"><span data-stu-id="11961-229">☐</span></span>  <br/> |<span data-ttu-id="11961-230">Toutes les mises à jour ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="11961-230">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="11961-231">**Périphériques audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="11961-231">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11961-232">☐</span><span class="sxs-lookup"><span data-stu-id="11961-232">☐</span></span>  <br/> |<span data-ttu-id="11961-233">La version du microprogramme de la caméra est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="11961-233">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="11961-234">☐</span><span class="sxs-lookup"><span data-stu-id="11961-234">☐</span></span>  <br/> |<span data-ttu-id="11961-235">Caméra fonctionnel et positionné de manière optimale</span><span class="sxs-lookup"><span data-stu-id="11961-235">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="11961-236">☐</span><span class="sxs-lookup"><span data-stu-id="11961-236">☐</span></span>  <br/> |<span data-ttu-id="11961-237">Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.</span><span class="sxs-lookup"><span data-stu-id="11961-237">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="11961-238">☐</span><span class="sxs-lookup"><span data-stu-id="11961-238">☐</span></span>  <br/> |<span data-ttu-id="11961-239">Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.</span><span class="sxs-lookup"><span data-stu-id="11961-239">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="11961-240">☐</span><span class="sxs-lookup"><span data-stu-id="11961-240">☐</span></span>  <br/> |<span data-ttu-id="11961-241">La version du microprogramme du périphérique audio est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="11961-241">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="11961-242">☐</span><span class="sxs-lookup"><span data-stu-id="11961-242">☐</span></span>  <br/> |<span data-ttu-id="11961-243">Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="11961-243">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="11961-244">☐</span><span class="sxs-lookup"><span data-stu-id="11961-244">☐</span></span>  <br/> |<span data-ttu-id="11961-245">Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="11961-245">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="11961-246">**Dock**</span><span class="sxs-lookup"><span data-stu-id="11961-246">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11961-247">☐</span><span class="sxs-lookup"><span data-stu-id="11961-247">☐</span></span>  <br/> |<span data-ttu-id="11961-248">Les câbles sont sécurisés et ne sont pas pincés.</span><span class="sxs-lookup"><span data-stu-id="11961-248">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="11961-249">☐</span><span class="sxs-lookup"><span data-stu-id="11961-249">☐</span></span>  <br/> |<span data-ttu-id="11961-250">La réception audio via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="11961-250">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="11961-251">☐</span><span class="sxs-lookup"><span data-stu-id="11961-251">☐</span></span>  <br/> |<span data-ttu-id="11961-252">La réception vidéo via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="11961-252">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="11961-253">☐</span><span class="sxs-lookup"><span data-stu-id="11961-253">☐</span></span>  <br/> |<span data-ttu-id="11961-254">Le dock peut pivoter librement.</span><span class="sxs-lookup"><span data-stu-id="11961-254">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="11961-255">☐</span><span class="sxs-lookup"><span data-stu-id="11961-255">☐</span></span>  <br/> |<span data-ttu-id="11961-256">La luminosité de l’affichage est acceptable pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="11961-256">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="11961-257">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11961-257">See also</span></span>
<span data-ttu-id="11961-258"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="11961-258"></span></span>

[<span data-ttu-id="11961-259">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="11961-259">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="11961-260">Déploiement des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="11961-260">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="11961-261">Configuration d’une console pour les systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="11961-261">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="11961-262">Gestion des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="11961-262">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)