---
title: Déployer le plug-in Lync VDI avec Skype Entreprise Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype Entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805934"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="f2a08-103">Déployer le plug-in Lync VDI avec Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f2a08-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="f2a08-104">Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype Entreprise lors de la connexion à un bureau virtuel distant.</span><span class="sxs-lookup"><span data-stu-id="f2a08-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="f2a08-105">Les considérations de planification sont à prendre en compte dans La planification de Skype Entreprise dans les [environnements VDI.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)</span><span class="sxs-lookup"><span data-stu-id="f2a08-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="f2a08-106">Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines organisations où les problèmes de sécurité et de conformité sont particulièrement sensibles.</span><span class="sxs-lookup"><span data-stu-id="f2a08-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="f2a08-107">Leurs utilisateurs sont sur des ordinateurs Windows locaux et utilisent des clients sur un bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="f2a08-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="f2a08-108">L’utilisation de Skype Entreprise sur une connexion de ce genre nécessite un logiciel de plug-in VDI supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="f2a08-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="f2a08-109">Deux solutions sont disponibles pour le composant de plug-in VDI : une proposée par Microsoft et l’autre proposée par Citrix.</span><span class="sxs-lookup"><span data-stu-id="f2a08-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="f2a08-110">Microsoft recommande d’utiliser la nouvelle solution HDX RealTime Optimization Pack dans les nouveaux déploiements, mais continuera à prendre en charge le plug-in Lync VDI d’origine pour le restant de son cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="f2a08-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="f2a08-111">Cette rubrique fournit des détails sur le déploiement du plug-in Microsoft Lync VDI, qui est uniquement pris en charge sur Windows 7 et Windows 8 ou Windows Server 2008, et prend uniquement en charge les clients Lync 2013 ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2a08-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="f2a08-112">Il n’est pas prévu de mettre à jour ce plug-in, mais le pack d’optimisation [Citrix HDX RealTime](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype Entreprise sera mis à jour selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="f2a08-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="f2a08-113">Préparer votre environnement pour le plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f2a08-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="f2a08-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f2a08-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="f2a08-115">Dans Skype Entreprise Server, assurez-vous que EnableMediaRedirection est définie sur TRUE pour tous les utilisateurs du plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f2a08-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="f2a08-116">Pour plus d’informations, voir les rubriques d’aide pour l';cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) et la cmdlet [Set-CsClientPolicy.)](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f2a08-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="f2a08-117">Sur le serveur du centre de données, installez le client Skype Entreprise sur tous les ordinateurs de bureau virtuels.</span><span class="sxs-lookup"><span data-stu-id="f2a08-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="f2a08-118">Sur les ordinateurs locaux, installez le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f2a08-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="f2a08-119">Les utilisateurs doivent maintenant connecter un appareil tel qu’un casque ou une webcam à leur ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f2a08-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="f2a08-120">Configurer les paramètres de connexion Bureau à distance</span><span class="sxs-lookup"><span data-stu-id="f2a08-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="f2a08-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f2a08-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="f2a08-122">Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, suivez les étapes suivantes sur l’ordinateur local :</span><span class="sxs-lookup"><span data-stu-id="f2a08-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="f2a08-123">Si l’ordinateur local exécute Windows 8, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="f2a08-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f2a08-124">Si l’ordinateur local exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du client des services Bureau à [distance.](https://go.microsoft.com/fwlink/p/?LinkId=268032)</span><span class="sxs-lookup"><span data-stu-id="f2a08-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="f2a08-125">Démarrez le client Services Bureau à distance en cliquant sur **Démarrer,** puis sur **Connexion Bureau à distance.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="f2a08-126">Cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="f2a08-127">Cliquez sur **l’onglet Ressources** locales. Sous **Audio distant,** cliquez **sur Paramètres,** puis faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2a08-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="f2a08-128">Sous **Lecture audio à distance,** **sélectionnez Lire sur cet ordinateur.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="f2a08-129">Sous **Enregistrement audio distant,** **sélectionnez Ne pas enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="f2a08-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="f2a08-131">Cliquez sur **l’onglet** Expérience. Sous **Performances,** cochez la case De **mise en cache de bitmap** persistante.</span><span class="sxs-lookup"><span data-stu-id="f2a08-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="f2a08-132">Cliquez sur **l’onglet** Général. Dans **Ordinateur,** tapez le nom du bureau virtuel, puis cliquez sur **Se connecter.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="f2a08-133">Connectez-vous et utilisez Skype Entreprise sur le bureau virtuel</span><span class="sxs-lookup"><span data-stu-id="f2a08-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="f2a08-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="f2a08-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="f2a08-135">Une fois le plug-in Lync VDI activé, l’utilisateur suit ces étapes lors de la signature de Skype Entreprise sur le bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="f2a08-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="f2a08-136">L’utilisateur tape ses informations d’identification dans le client Skype Entreprise qui s’exécute sur le bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="f2a08-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="f2a08-137">Une fois que Skype Entreprise a détecté le plug-in Lync VDI, Skype Entreprise invite l’utilisateur à entrer de nouveau les informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="f2a08-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="f2a08-138">Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f2a08-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="f2a08-139">Skype Entreprise commence le jumelage avec le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f2a08-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="f2a08-140">Pendant ce temps, le client affiche deux icônes dans la barre d’état Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2a08-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="f2a08-141">L’icône en bas à gauche indique qu’aucun périphérique audio n’est disponible et que l’icône clignotante en bas à droite indique que le jumelage VDI est en cours : a.</span><span class="sxs-lookup"><span data-stu-id="f2a08-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="f2a08-142">Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et le jumelage VDI réussi : b.</span><span class="sxs-lookup"><span data-stu-id="f2a08-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="f2a08-143">L’utilisateur peut désormais voir sa présence sur des appareils compatibles avec Skype Entreprise connectés à l’ordinateur local, et passe des appels et répond comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="f2a08-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="f2a08-144">Résoudre les problèmes du plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f2a08-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="f2a08-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f2a08-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="f2a08-146">Reportez-vous aux sections suivantes si vous rencontrez des problèmes après avoir installé le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f2a08-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="f2a08-147">Problèmes d’installation du plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f2a08-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="f2a08-148">Si l’installation du plug-in Lync VDI est problématique, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="f2a08-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="f2a08-149">Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.</span><span class="sxs-lookup"><span data-stu-id="f2a08-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="f2a08-150">Assurez-vous que la protection en écriture est désactivée.</span><span class="sxs-lookup"><span data-stu-id="f2a08-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="f2a08-151">Reportez-vous à la documentation du fabricant de votre appareil pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="f2a08-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f2a08-152">Résolution des problèmes liés au jumelage</span><span class="sxs-lookup"><span data-stu-id="f2a08-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f2a08-153">En cas d’échec du jumelage du plug-in Lync VDI, l’icône de jumelage en bas à droite s’affiche sous la forme d’un « X » rouge, comme illustré :</span><span class="sxs-lookup"><span data-stu-id="f2a08-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="f2a08-154">Voici les raisons possibles des échecs et les actions que vous pouvez prendre pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="f2a08-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="f2a08-155">**L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f2a08-156">L’utilisateur doit se sortir de Skype Entreprise et se resserre avec les informations d’identification correctes.</span><span class="sxs-lookup"><span data-stu-id="f2a08-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="f2a08-157">La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.</span><span class="sxs-lookup"><span data-stu-id="f2a08-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="f2a08-158">**Une autre instance du client Bureau à distance est en cours d’exécution.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f2a08-159">S’ils utilisent la connexion Bureau à distance dans Windows, les utilisateurs doivent :</span><span class="sxs-lookup"><span data-stu-id="f2a08-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="f2a08-160">Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr**, puis cliquez sur **Démarrer le Gestionnaire des tâches**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="f2a08-161">Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f2a08-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="f2a08-162">Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="f2a08-163">Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f2a08-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="f2a08-164">**Les fichiers nécessaires n’ont pas été installés correctement.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f2a08-165">Une fois le plug-in installé sur l’ordinateur local, vérifiez que ces fichiers sont présents sous C:\Program Files\Microsoft Office\Office15 (ou la lettre de lecteur appropriée) :</span><span class="sxs-lookup"><span data-stu-id="f2a08-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="f2a08-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="f2a08-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="f2a08-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="f2a08-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="f2a08-168">**Le client Skype Entreprise est en cours d’exécution sur l’ordinateur local.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f2a08-169">Pour utiliser le plug-in Lync VDI, un client Skype Entreprise ne doit pas être en cours d’exécution sur l’ordinateur local, sinon le jumelage échouera.</span><span class="sxs-lookup"><span data-stu-id="f2a08-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f2a08-170">En tant que meilleure pratique, l’utilisateur ne doit pas installer de client Skype Entreprise sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f2a08-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f2a08-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2a08-171">See also</span></span>
<span data-ttu-id="f2a08-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f2a08-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="f2a08-173">Planifier Skype Entreprise dans les environnements VDI</span><span class="sxs-lookup"><span data-stu-id="f2a08-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
