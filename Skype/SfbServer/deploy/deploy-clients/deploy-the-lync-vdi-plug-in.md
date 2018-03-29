---
title: Déployer le plug-in Lync VDI dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype pour les entreprises lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="2c3e3-103">Déployer le plug-in Lync VDI dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2c3e3-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c3e3-104">Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype pour les entreprises lors de la connexion à un bureau virtuel distant.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="2c3e3-105">Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="2c3e3-106">Dans ces entreprises, les utilisateurs effectuent leur travail sur des ordinateurs Windows locaux et se servent de clients sur un bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="2c3e3-107">À l’aide de Skype pour entreprise sur une connexion qu’exige un logiciel de plug-in de VDI supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="2c3e3-108">Deux solutions sont disponibles pour le composant plug-in de VDI - un offerte par Microsoft et un offertes par Citrix.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="2c3e3-109">Microsoft recommande l’utilisation de la nouvelle solution de Pack d’optimisation HDX en temps réel dans les nouveaux déploiements, mais continuera à prendre en charge le plug-in de VDI Lync d’origine jusqu'à la fin de son cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="2c3e3-110">Cette rubrique fournit des détails sur le déploiement de Microsoft Lync VDI plug-in, qui est pris en charge uniquement sur Windows 7 et Windows 8 ou Windows Server 2008 et ne prend en charge Lync 2013 ou Skype pour les clients d’entreprise 2015.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="2c3e3-111">Il n’est pas prévu de la mise à jour de ce plug-in, mais le [Pack d’optimisation Citrix HDX en temps réel](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype pour entreprise sera mis à jour en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="2c3e3-112">Préparer votre environnement au plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="2c3e3-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="2c3e3-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="2c3e3-113"></span></span>

1. <span data-ttu-id="2c3e3-114">Dans Skype pour Business Server 2015, assurez-vous que EnableMediaRedirection a la valeur TRUE pour tous les utilisateurs du plug-in de Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="2c3e3-115">Pour plus d’informations, consultez les rubriques d’aide pour l’applet de commande [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) et l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2c3e3-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="2c3e3-116">Sur le serveur de centre de données, installez le Skype pour client d’entreprise 2015 sur tous les postes de travail virtuels.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="2c3e3-117">Sur les ordinateurs locaux, installez le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="2c3e3-118">Les utilisateurs doivent maintenant connecter un périphérique tel qu’un casque ou une webcam à leur ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="2c3e3-119">Configurer les paramètres de la connexion Bureau à distance</span><span class="sxs-lookup"><span data-stu-id="2c3e3-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="2c3e3-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="2c3e3-120"></span></span>

<span data-ttu-id="2c3e3-121">Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, procédez comme suit sur l’ordinateur local :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="2c3e3-122">Si l’ordinateur local exécute Windows 8, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="2c3e3-123">Si l’ordinateur exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du [client des Services Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="2c3e3-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="2c3e3-124">Démarrez le client des services Bureau à distance en cliquant sur **Démarrer**, puis sur **Connexion Bureau à distance **.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="2c3e3-125">Cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="2c3e3-126">Cliquez sur l’onglet **Ressources locales**. Sous **Sortie audio de l’ordinateur distant **, cliquez sur **Paramètres**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="2c3e3-127">Sous **Lecture audio à distance**, sélectionnez **Lire sur cet ordinateur **.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="2c3e3-128">Sous **Enregistrement audio à distance**, sélectionnez **Ne pas enregistrer **.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="2c3e3-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="2c3e3-130">Cliquez sur l’onglet **Expérience**. Sous **Performance **, désactivez la case à cocher **Mise en cache permanente des bitmaps **.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="2c3e3-131">Cliquez sur l’onglet **Général**. Dans **Ordinateur **, tapez le nom du bureau virtuel, puis cliquez sur **Connecter **. </span><span class="sxs-lookup"><span data-stu-id="2c3e3-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="2c3e3-132">Se connecter et utiliser Skype Entreprise sur le bureau virtuel</span><span class="sxs-lookup"><span data-stu-id="2c3e3-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="2c3e3-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="2c3e3-133"></span></span>

<span data-ttu-id="2c3e3-134">Une fois que le plug-in Lync VDI est activé, l’utilisateur suit ces étapes lorsque vous vous connectez à Skype pour entreprise 2015 sur le bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="2c3e3-135">L’utilisateur saisit ses informations d’identification dans le Skype pour client d’entreprise 2015 en cours d’exécution sur le bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="2c3e3-136">Une fois Skype pour entreprise 2015 détecte le plug-in Lync VDI, Skype pour entreprise 2015 invite l’utilisateur à entrer les informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="2c3e3-137">Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="2c3e3-138">Skype pour entreprise 2015 commence l’appariement avec le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="2c3e3-139">Lorsque cela se produit, le client affiche deux icônes dans le Skype pour entreprise 2015 barre d’état.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="2c3e3-140">L’icône en bas à gauche indique qu’aucun périphérique audio n’est disponible, tandis que l’icône qui clignote en bas à droite indique que le jumelage VDI est en cours, comme indiqué :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="2c3e3-141">Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="2c3e3-142">L’utilisateur peut désormais voir présence son sur Skype pour les périphériques compatibles 2015 d’entreprise qui sont connectés à l’ordinateur local et de placer et de répondent aux appels comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="2c3e3-143">Résolution des problèmes du plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="2c3e3-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="2c3e3-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="2c3e3-144"></span></span>

<span data-ttu-id="2c3e3-145">Reportez-vous aux sections suivantes si vous rencontrez des problèmes après l’installation du plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="2c3e3-146">Problèmes d’installation du plug-in Lync VDI </span><span class="sxs-lookup"><span data-stu-id="2c3e3-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="2c3e3-147">S’il existe des problèmes avec l’installation du plug-in Lync VDI, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="2c3e3-148">Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="2c3e3-149">Assurez-vous que la protection en écriture est désactivée.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="2c3e3-150">Reportez-vous à la documentation du fabricant du périphérique pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="2c3e3-151">Résolution des problèmes liés au jumelage</span><span class="sxs-lookup"><span data-stu-id="2c3e3-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="2c3e3-152">Lorsque Lync VDI plug-in d’appariement échoue, l’icône de correspondance dans le droit inférieur s’affiche sous la forme d’un « X » rouge comme indiqué :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="2c3e3-153">Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier. </span><span class="sxs-lookup"><span data-stu-id="2c3e3-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="2c3e3-154">**L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**</span><span class="sxs-lookup"><span data-stu-id="2c3e3-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="2c3e3-155">L’utilisateur doit se déconnecter de Skype pour les entreprises et reconnectez-vous avec les informations d’identification correctes.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="2c3e3-156">La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="2c3e3-157">**Une autre instance du client Bureau à distance est en cours d’exécution.**</span><span class="sxs-lookup"><span data-stu-id="2c3e3-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="2c3e3-158">Si elles sont à l’aide de connexion Bureau à distance dans Windows, les utilisateurs doivent faire les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="2c3e3-159">Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr **, puis cliquez sur **Démarrer le Gestionnaire des tâches**.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="2c3e3-160">Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="2c3e3-161">Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**. </span><span class="sxs-lookup"><span data-stu-id="2c3e3-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="2c3e3-162">Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter. </span><span class="sxs-lookup"><span data-stu-id="2c3e3-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="2c3e3-163">**Les fichiers nécessaires n’ont pas été installés correctement.**</span><span class="sxs-lookup"><span data-stu-id="2c3e3-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="2c3e3-164">Une fois le plug-in installé sur l’ordinateur local, vérifiez que les fichiers suivants se trouvent sous C:\Program Files\Microsoft Office\Office15 (ou la lettre de lecteur qui convient) :</span><span class="sxs-lookup"><span data-stu-id="2c3e3-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="2c3e3-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="2c3e3-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="2c3e3-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="2c3e3-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="2c3e3-167">**Le Skype pour client d’entreprise 2015 est en cours d’exécution sur l’ordinateur local.**</span><span class="sxs-lookup"><span data-stu-id="2c3e3-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="2c3e3-168">Pour utiliser le plug-in, qu'un Skype pour client d’entreprise 2015 ne doit pas être en cours d’exécution sur l’ordinateur local Lync VDI, sinon la correspondance échoue.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="2c3e3-169">Pour obtenir les meilleurs résultats, l’utilisateur n’installez pas un Skype pour entreprise 2015 client sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="2c3e3-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2c3e3-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c3e3-170">See also</span></span>
<span data-ttu-id="2c3e3-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="2c3e3-171"></span></span>

#### 

[<span data-ttu-id="2c3e3-172">Plan de Skype pour l’entreprise dans les environnements VDI</span><span class="sxs-lookup"><span data-stu-id="2c3e3-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

