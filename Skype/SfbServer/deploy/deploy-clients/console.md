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
ms.openlocfilehash: 00203c8aa781c489d8a1cc8c2bf91a364bea057f
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694719"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="39a52-103">Configuration d’une console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="39a52-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="39a52-104">Cet article explique comment configurer la console v2 Skype salle systèmes et périphériques.</span><span class="sxs-lookup"><span data-stu-id="39a52-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="39a52-105">Vous devez uniquement effectuer ces étapes si la Skype nécessaire pour les comptes d’entreprise et Exchange ont déjà créé et testé comme décrit dans [déployer Skype salle systèmes v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="39a52-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="39a52-106">Vous devez le matériel et les logiciels décrits dans [v2 Skype salle requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a52-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="39a52-107">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="39a52-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="39a52-108">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="39a52-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="39a52-109">Installer un certificat d’autorité de certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="39a52-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="39a52-110">Installation de Windows 10 et de l’application de console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="39a52-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="39a52-111">Configurer initiale de la console</span><span class="sxs-lookup"><span data-stu-id="39a52-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="39a52-112">Liste de vérification de déploiement de systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="39a52-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="39a52-113">Systèmes de salle Skype v2 fonctionne uniquement dans un Skype correctement configurée pour un environnement d’entreprise où les comptes de périphériques sont correctement configurés comme décrit dans [déployer Skype salle systèmes v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="39a52-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="39a52-114">Préparer le support d’installation</span><span class="sxs-lookup"><span data-stu-id="39a52-114">Prepare the installation media</span></span>
<span data-ttu-id="39a52-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-115"></span></span>

<span data-ttu-id="39a52-116">Installation de l’application de console Skype salle systèmes v2 requiert un périphérique de stockage USB avec au moins 32 Go de la capacité.</span><span class="sxs-lookup"><span data-stu-id="39a52-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="39a52-117">Il ne doit y avoir aucun autre fichier sur le périphérique ; les fichiers existants sur le stockage USB seront perdues.</span><span class="sxs-lookup"><span data-stu-id="39a52-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39a52-118">Impossible de créer votre support d’installation v2 Skype salle systèmes en fonction de ces instructions aura un comportement inattendu.</span><span class="sxs-lookup"><span data-stu-id="39a52-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="39a52-119">La procédure ci-dessous est pour la création du support d’installation vers de nouveaux périphériques de v2 Skype salle System image.</span><span class="sxs-lookup"><span data-stu-id="39a52-119">The process below is for creating installation media to image new Skype Room System v2 devices.</span></span> <span data-ttu-id="39a52-120">Périphériques existants, par défaut, mettre à jour automatiquement à partir de Windows Update et Windows Store.</span><span class="sxs-lookup"><span data-stu-id="39a52-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="39a52-121">Télécharger le script [CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842). </span><span class="sxs-lookup"><span data-stu-id="39a52-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="39a52-122">Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="39a52-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="39a52-123">Suivez les instructions du script pour créer un disque d’installation de systèmes de salle Skype v2 USB.</span><span class="sxs-lookup"><span data-stu-id="39a52-123">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="39a52-124">Le nom du dossier dans lequel vous exécutez le support de script de création de ne peut pas contenir un espace.</span><span class="sxs-lookup"><span data-stu-id="39a52-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="39a52-125">S’il existe un espace de nom de dossier, le script échouera.</span><span class="sxs-lookup"><span data-stu-id="39a52-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="39a52-126">Le script CreateSrsMedia.ps1 automatise les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="39a52-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="39a52-127">Téléchargez le programme d’installation MSI le plus récent pour les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="39a52-127">Download the latest MSI installer for Skype Room Systems v2.</span></span>
2. <span data-ttu-id="39a52-128">Déterminer la version de Windows que l’utilisateur doit fournir.</span><span class="sxs-lookup"><span data-stu-id="39a52-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="39a52-129">Les versions la plus récentes peuvent ou ne peut pas être testées et pris en charge pour une utilisation avec des périphériques v2 Skype salle système.</span><span class="sxs-lookup"><span data-stu-id="39a52-129">The most recently released versions may or may not be tested and supported for use with Skype Room System v2 devices.</span></span>
3. <span data-ttu-id="39a52-130">Télécharger les composants de prise en charge nécessaires.</span><span class="sxs-lookup"><span data-stu-id="39a52-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="39a52-131">Assembler les composants nécessaires sur le support d’installation.</span><span class="sxs-lookup"><span data-stu-id="39a52-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="39a52-132">Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [10 de Windows Installer et de l’application de console Skype salle systèmes v2](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="39a52-132">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="39a52-133">Installation de Windows 10 et de l’application de console Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="39a52-133">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="39a52-134"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-134"></span></span>

<span data-ttu-id="39a52-135">Vous devez maintenant appliquer le support d’installation que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="39a52-135">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="39a52-136">Le périphérique cible s’exécute en tant qu’un matériel et l’utilisateur par défaut sera définie ne s’exécute l’application de console Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="39a52-136">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="39a52-137">Si l’équipement est installé dans une station d’accueil (par exemple, une Surface Pro), le déconnecter de la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="39a52-137">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="39a52-138">Vérifiez que le périphérique cible n’est pas connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="39a52-138">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="39a52-139">Vérifiez que l’équipement est connecté au secteur.</span><span class="sxs-lookup"><span data-stu-id="39a52-139">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="39a52-140">Branchez votre disque d’installation USB sur le périphérique cible.</span><span class="sxs-lookup"><span data-stu-id="39a52-140">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="39a52-141">Démarrez le disque d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="39a52-141">Boot to the USB setup disk.</span></span> <span data-ttu-id="39a52-142">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="39a52-142">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="39a52-143">Si votre périphérique cible est une Surface Pro, procédez comme suit pour démarrer sur le disque d’installation USB :</span><span class="sxs-lookup"><span data-stu-id="39a52-143">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="39a52-144">a.</span><span class="sxs-lookup"><span data-stu-id="39a52-144">a.</span></span> <span data-ttu-id="39a52-145">Appuyez sur et maintenez le volume vers le bas du bouton (-).</span><span class="sxs-lookup"><span data-stu-id="39a52-145">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="39a52-146">b.</span><span class="sxs-lookup"><span data-stu-id="39a52-146">b.</span></span> <span data-ttu-id="39a52-147">Appuyez puis relâchez le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="39a52-147">Press and release the power button.</span></span>

    <span data-ttu-id="39a52-148">c.</span><span class="sxs-lookup"><span data-stu-id="39a52-148">c.</span></span> <span data-ttu-id="39a52-149">Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).</span><span class="sxs-lookup"><span data-stu-id="39a52-149">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="39a52-150">Le système s’arrêtera une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="39a52-150">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="39a52-151">Une fois que le système est arrêté, il est recommandé supprimer le disque du programme d’installation USB.</span><span class="sxs-lookup"><span data-stu-id="39a52-151">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="39a52-152">À ce stade, vous pourrez placer le périphérique cible dans sa station d’accueil (si vous utilisez un produit basé sur une station d’accueil), attacher les périphériques nécessaires pour votre salle de réunion et connexion au réseau.</span><span class="sxs-lookup"><span data-stu-id="39a52-152">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="39a52-153">Reportez-vous aux instructions de fabricant.</span><span class="sxs-lookup"><span data-stu-id="39a52-153">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="39a52-154">Sélection d’une langue</span><span class="sxs-lookup"><span data-stu-id="39a52-154">Selecting a language</span></span> 

<span data-ttu-id="39a52-155">Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de la langue implicite ne fournit pas l’utilisateur dont la langue de l’application réelle qu’ils souhaitent (par exemple, qu’ils souhaitent l’application de console pour élaborer en Français, mais elle suit en anglais).</span><span class="sxs-lookup"><span data-stu-id="39a52-155">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="39a52-156">Les instructions suivantes s’appliquent uniquement pour les consoles créées à l’aide de la mise à jour du créateur de Windows.</span><span class="sxs-lookup"><span data-stu-id="39a52-156">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="39a52-157">Systèmes hérité/dans-marché qui n’ont pas été définies à l’aide des supports avec le nouveau système de mise en service ne sera pas en mesure d’utiliser ces instructions, mais doit également préférable de l’émission initiale qui nécessite une intervention manuelle cette (Édition anniversaire vous permettent de choisir votre langue de l’application explicitement dans le cadre du programme d’installation).</span><span class="sxs-lookup"><span data-stu-id="39a52-157">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="39a52-158">Pour appliquer la langue de votre choix</span><span class="sxs-lookup"><span data-stu-id="39a52-158">To apply your desired language</span></span>

1. <span data-ttu-id="39a52-159">Passez en mode Administrateur.</span><span class="sxs-lookup"><span data-stu-id="39a52-159">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="39a52-160">Sélectionnez le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="39a52-160">Select the Start menu.</span></span>
    
3. <span data-ttu-id="39a52-161">Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="39a52-161">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="39a52-162">Sélectionnez **temps &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="39a52-162">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="39a52-163">Sélectionnez **région &amp; langue**.</span><span class="sxs-lookup"><span data-stu-id="39a52-163">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="39a52-164">Sélectionnez **Ajouter une langue**.</span><span class="sxs-lookup"><span data-stu-id="39a52-164">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="39a52-165">Sélectionnez la langue que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="39a52-165">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="39a52-166">Sélectionnez la langue que vous venez d’ajouter à la liste « Langues ».</span><span class="sxs-lookup"><span data-stu-id="39a52-166">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="39a52-167">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="39a52-167">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="39a52-168">Pour supprimer une langue :</span><span class="sxs-lookup"><span data-stu-id="39a52-168">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="39a52-p113">a. Sélectionnez la langue que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="39a52-p113">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="39a52-p114">b. Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="39a52-p114">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="39a52-173">Lancez une invite de commande avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="39a52-173">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="39a52-174">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="39a52-174">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="39a52-175">Redémarrez le système.</span><span class="sxs-lookup"><span data-stu-id="39a52-175">Restart the system.</span></span>
    
<span data-ttu-id="39a52-176">Langage de votre choix est désormais appliqué à la console de v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="39a52-176">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="39a52-177">Configurer initiale de la console</span><span class="sxs-lookup"><span data-stu-id="39a52-177">Initial set up of the console</span></span>
<span data-ttu-id="39a52-178"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-178"></span></span>

<span data-ttu-id="39a52-179">Une fois que Windows est installé, l’application de console v2 Skype salle systèmes passe en son processus d’installation initial lors du démarrage suivant ou si l’option /reboot a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="39a52-179">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="39a52-180">L’écran Compte d’utilisateur apparaît.</span><span class="sxs-lookup"><span data-stu-id="39a52-180">The User Account screen appears.</span></span> <span data-ttu-id="39a52-181">Entrez le Skype adresse de connexion (au format user@domain) du compte à utiliser avec la console de salle.</span><span class="sxs-lookup"><span data-stu-id="39a52-181">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="39a52-182">Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="39a52-182">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="39a52-183">Sous « Configurer le domaine », définir le nom de domaine complet de le Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="39a52-183">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="39a52-184">Si le Skype pour le domaine SIP de l’entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="39a52-184">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="39a52-185">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="39a52-185">Click **Next**.</span></span>
    
5. <span data-ttu-id="39a52-186">Sélectionnez les périphériques indiqués dans l’écran de fonctionnalités, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="39a52-186">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="39a52-187">Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="39a52-187">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="39a52-188">Les appareils à sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="39a52-188">The devices to select are:</span></span>
    
   - <span data-ttu-id="39a52-189">Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="39a52-189">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="39a52-190">Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences. </span><span class="sxs-lookup"><span data-stu-id="39a52-190">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="39a52-191">Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.</span><span class="sxs-lookup"><span data-stu-id="39a52-191">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="39a52-p118">Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="39a52-p118">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="39a52-194">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="39a52-194">Click **Finish**.</span></span>
    
<span data-ttu-id="39a52-195">L’application de console v2 Skype salle systèmes doit démarrer immédiatement la connexion à Skype pour Business Server avec les informations d’identification ci-dessus et doit également synchroniseront son calendrier avec Exchange à l’aide de ces mêmes informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="39a52-195">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="39a52-196">Pour plus d’informations sur l’utilisation de l’application de console, reportez-vous à l' [aide de systèmes de salle Skype version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="39a52-196">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39a52-197">Systèmes de salle Skype v2 s’appuie sur la présence de matériel certifié console.</span><span class="sxs-lookup"><span data-stu-id="39a52-197">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="39a52-198">Même une image correctement créée contenant l’application de console Skype salle systèmes v2 ne démarre pas au-delà de la procédure d’installation initiale, sauf si le matériel de console est détecté.</span><span class="sxs-lookup"><span data-stu-id="39a52-198">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="39a52-199">Pour des solutions Surface Pro en fonction de la Surface Pro doit être connecté à son matériel ancrer accompagnement pour passer cette vérification.</span><span class="sxs-lookup"><span data-stu-id="39a52-199">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39a52-200">Certains utilisateurs non anglaises peut-être un clavier physique connecté à la console pendant l’installation initiale, dans le cas où les symboles ne sont pas pris en charge sur le clavier tactile.</span><span class="sxs-lookup"><span data-stu-id="39a52-200">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="39a52-201">Installer un certificat d’autorité de certification privé sur la console</span><span class="sxs-lookup"><span data-stu-id="39a52-201">Install a private CA certificate on the console</span></span>
<span data-ttu-id="39a52-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-202"></span></span>

<span data-ttu-id="39a52-203">La console de v2 Skype salle systèmes doit approuver les certificats utilisés par le Skype pour professionnels et les serveurs Exchange à que se connecte.</span><span class="sxs-lookup"><span data-stu-id="39a52-203">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="39a52-204">Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10.</span><span class="sxs-lookup"><span data-stu-id="39a52-204">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="39a52-205">Dans un cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat dans la console de v2 Skype salle systèmes de deux façons :</span><span class="sxs-lookup"><span data-stu-id="39a52-205">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="39a52-206">Vous pouvez participer à la console à Active Directory et qui ajoute automatiquement les certificats requis donnés de l’autorité de certification est publié dans Active Directory (option de déploiement normal).</span><span class="sxs-lookup"><span data-stu-id="39a52-206">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="39a52-207">Vous pouvez installer le certificat manuellement après le processus de création d’image.</span><span class="sxs-lookup"><span data-stu-id="39a52-207">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="39a52-208">Avant de le faire, vous devez effectuer le [paramétrage Initial de la console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="39a52-208">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="39a52-209">Pour installer manuellement le certificat </span><span class="sxs-lookup"><span data-stu-id="39a52-209">To manually install the certificate</span></span>

1. <span data-ttu-id="39a52-210">Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="39a52-210">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="39a52-211">Placez la console en mode admin (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="39a52-211">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="39a52-212">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="39a52-212">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="39a52-213">Participer à un domaine Active Directory (facultatif)</span><span class="sxs-lookup"><span data-stu-id="39a52-213">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="39a52-214"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-214"></span></span>

<span data-ttu-id="39a52-215">Vous pouvez joindre les consoles v2 de systèmes de salle Skype à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="39a52-215">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="39a52-216">Consoles v2 de systèmes de salle Skype doivent être placés dans une unité d’organisation distincte à partir de stations de travail de votre PC, car le nombre de stratégies de station de travail n’est pas compatible avec les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="39a52-216">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="39a52-217">Un exemple courant sont les stratégies de mot de passe qui empêchent Skype salle systèmes v2 de démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="39a52-217">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="39a52-218">Pour plus d’informations sur la gestion des paramètres de stratégie de groupe, reportez-vous à [Gérer les systèmes de salle Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="39a52-218">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="39a52-219">Pour joindre Skype Room Systems v2 à un domaine</span><span class="sxs-lookup"><span data-stu-id="39a52-219">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="39a52-220">Connexion à la console de l’administrateur de compte (voir [gestion de mode et appareil d’administration](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="39a52-220">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="39a52-221">Lancez l’invite de commande Powershell avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="39a52-221">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="39a52-222">Saisissez la commande suivante dans Powershell :</span><span class="sxs-lookup"><span data-stu-id="39a52-222">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="39a52-223">Par exemple, si votre nom de domaine complet est Redmond.corp.Microsoft.com et vous souhaitez que vos consoles v2 de Skype salle systèmes dans une « salle Skype systèmes v2 » unité d’organisation qui est un enfant d’une unité d’organisation « ressources », la commande sera :</span><span class="sxs-lookup"><span data-stu-id="39a52-223">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="39a52-224">Si vous souhaitez renommer l’ordinateur lors de l’intégration à un domaine, utilisez l’indicateur - NewName suivi d’un nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="39a52-224">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="39a52-225">Liste de vérification de déploiement de systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="39a52-225">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="39a52-226"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-226"></span></span>

<span data-ttu-id="39a52-227">Utilisez la liste de vérification suivante tout en effectuant une vérification finale que la console et tous les périphériques sont configurées :</span><span class="sxs-lookup"><span data-stu-id="39a52-227">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="39a52-228">**Paramètres de l’application**</span><span class="sxs-lookup"><span data-stu-id="39a52-228">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="39a52-229">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-229">☐</span></span>  <br/> |<span data-ttu-id="39a52-230">Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.</span><span class="sxs-lookup"><span data-stu-id="39a52-230">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="39a52-231">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-231">☐</span></span>  <br/> |<span data-ttu-id="39a52-232">Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).</span><span class="sxs-lookup"><span data-stu-id="39a52-232">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="39a52-233">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-233">☐</span></span>  <br/> |<span data-ttu-id="39a52-234">Le mot de passe du compte de l’administrateur est défini et vérifié.</span><span class="sxs-lookup"><span data-stu-id="39a52-234">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="39a52-235">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-235">☐</span></span>  <br/> |<span data-ttu-id="39a52-236">Toutes les mises à jour ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="39a52-236">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="39a52-237">**Périphériques audio/vidéo**</span><span class="sxs-lookup"><span data-stu-id="39a52-237">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="39a52-238">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-238">☐</span></span>  <br/> |<span data-ttu-id="39a52-239">La version du microprogramme de la caméra est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="39a52-239">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="39a52-240">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-240">☐</span></span>  <br/> |<span data-ttu-id="39a52-241">Caméra fonctionnel et positionné de manière optimale</span><span class="sxs-lookup"><span data-stu-id="39a52-241">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="39a52-242">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-242">☐</span></span>  <br/> |<span data-ttu-id="39a52-243">Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.</span><span class="sxs-lookup"><span data-stu-id="39a52-243">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="39a52-244">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-244">☐</span></span>  <br/> |<span data-ttu-id="39a52-245">Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.</span><span class="sxs-lookup"><span data-stu-id="39a52-245">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="39a52-246">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-246">☐</span></span>  <br/> |<span data-ttu-id="39a52-247">La version du microprogramme du périphérique audio est correcte (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="39a52-247">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="39a52-248">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-248">☐</span></span>  <br/> |<span data-ttu-id="39a52-249">Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="39a52-249">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="39a52-250">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-250">☐</span></span>  <br/> |<span data-ttu-id="39a52-251">Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="39a52-251">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="39a52-252">**Dock**</span><span class="sxs-lookup"><span data-stu-id="39a52-252">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="39a52-253">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-253">☐</span></span>  <br/> |<span data-ttu-id="39a52-254">Les câbles sont sécurisés et ne sont pas pincés.</span><span class="sxs-lookup"><span data-stu-id="39a52-254">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="39a52-255">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-255">☐</span></span>  <br/> |<span data-ttu-id="39a52-256">La réception audio via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="39a52-256">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="39a52-257">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-257">☐</span></span>  <br/> |<span data-ttu-id="39a52-258">La réception vidéo via HDMI est fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="39a52-258">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="39a52-259">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-259">☐</span></span>  <br/> |<span data-ttu-id="39a52-260">Le dock peut pivoter librement.</span><span class="sxs-lookup"><span data-stu-id="39a52-260">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="39a52-261">☐</span><span class="sxs-lookup"><span data-stu-id="39a52-261">☐</span></span>  <br/> |<span data-ttu-id="39a52-262">La luminosité de l’affichage est acceptable pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="39a52-262">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="39a52-263">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39a52-263">See also</span></span>
<span data-ttu-id="39a52-264"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="39a52-264"></span></span>

[<span data-ttu-id="39a52-265">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="39a52-265">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="39a52-266">Déploiement des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="39a52-266">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="39a52-267">Configuration d’une console pour les systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="39a52-267">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="39a52-268">Gestion des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="39a52-268">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)