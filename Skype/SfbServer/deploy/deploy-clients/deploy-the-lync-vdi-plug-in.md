---
title: Déploiement du plug-in Lync VDI avec Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288753"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="f8c96-103">Déploiement du plug-in Lync VDI avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f8c96-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="f8c96-104">Cette rubrique décrit les procédures de déploiement pour l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant.</span><span class="sxs-lookup"><span data-stu-id="f8c96-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="f8c96-105">Les considérations en matière de planification s’exécutent au [plan de Skype entreprise dans les environnements VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f8c96-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="f8c96-106">Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux.</span><span class="sxs-lookup"><span data-stu-id="f8c96-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="f8c96-107">Dans ces entreprises, les utilisateurs effectuent leur travail sur des ordinateurs Windows locaux et se servent de clients sur un bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="f8c96-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="f8c96-108">Utiliser Skype entreprise sur une connexion telle qu’un logiciel supplémentaire VDI supplémentaire est requis.</span><span class="sxs-lookup"><span data-stu-id="f8c96-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="f8c96-109">Il existe deux solutions disponibles pour le composant enfichable VDI, l’une proposée par Microsoft et celle proposée par Citrix.</span><span class="sxs-lookup"><span data-stu-id="f8c96-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="f8c96-110">Microsoft recommande d’utiliser la nouvelle solution HDX en temps réel d’optimisation en temps réel dans de nouveaux déploiements, mais continuera à prendre en charge le plug-in Lync VDI d’origine pour le reste de son cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="f8c96-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="f8c96-111">Cette rubrique fournit des détails sur le déploiement du plug-in Microsoft Lync VDI qui est uniquement pris en charge sur Windows 7 et Windows 8 ou Windows Server 2008 et ne prend en charge que les clients Lync 2013 ou Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f8c96-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="f8c96-112">Il n’est pas prévu de mettre à jour ce plug-in, mais le [Pack d’optimisation en temps réel de Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) pour Skype entreprise sera mis à jour selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="f8c96-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="f8c96-113">Préparer votre environnement au plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f8c96-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="f8c96-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c96-114"></span></span>

1. <span data-ttu-id="f8c96-115">Dans Skype entreprise Server, assurez-vous que EnableMediaRedirection est défini sur TRUE pour tous les utilisateurs du plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f8c96-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="f8c96-116">Pour plus d’informations, consultez les rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) et l’applet de connexion [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f8c96-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="f8c96-117">Sur le serveur du centre de données, installez le client Skype entreprise sur tous les ordinateurs de bureau virtuels.</span><span class="sxs-lookup"><span data-stu-id="f8c96-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="f8c96-118">Sur l’ordinateur local, installez le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f8c96-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="f8c96-119">Les utilisateurs doivent maintenant connecter un périphérique tel qu’un casque ou une webcam à leur ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f8c96-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="f8c96-120">Configurer les paramètres de la connexion Bureau à distance</span><span class="sxs-lookup"><span data-stu-id="f8c96-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="f8c96-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c96-121"></span></span>

<span data-ttu-id="f8c96-122">Pour préparer la connexion Bureau à distance pour le plug-in Lync VDI, procédez comme suit sur l’ordinateur local:</span><span class="sxs-lookup"><span data-stu-id="f8c96-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="f8c96-123">Si l’ordinateur local exécute Windows 8, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="f8c96-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f8c96-124">Si l’ordinateur local exécute Windows 7 avec SP1, installez la dernière version de Windows 8 du [client de services Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="f8c96-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="f8c96-125">Démarrez le client des services Bureau à distance en cliquant sur **Démarrer**, puis sur \*\*Connexion Bureau à distance \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8c96-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="f8c96-126">Cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="f8c96-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="f8c96-127">Cliquez sur l’onglet **Ressources locales**. Sous \*\*Sortie audio de l’ordinateur distant \*\*, cliquez sur **Paramètres**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8c96-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="f8c96-128">Sous **Lecture audio à distance**, sélectionnez \*\*Lire sur cet ordinateur \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8c96-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="f8c96-129">Sous **Enregistrement audio à distance**, sélectionnez \*\*Ne pas enregistrer \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8c96-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="f8c96-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8c96-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="f8c96-131">Cliquez sur l’onglet **Expérience**. Sous \*\*Performance \*\*, désactivez la case à cocher \*\*Mise en cache permanente des bitmaps \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8c96-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="f8c96-132">Cliquez sur l’onglet **Général**. Dans \*\*Ordinateur \*\*, tapez le nom du bureau virtuel, puis cliquez sur \*\*Connecter \*\*. </span><span class="sxs-lookup"><span data-stu-id="f8c96-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="f8c96-133">Se connecter et utiliser Skype Entreprise sur le bureau virtuel</span><span class="sxs-lookup"><span data-stu-id="f8c96-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="f8c96-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c96-134"></span></span>

<span data-ttu-id="f8c96-135">Une fois que le plug-in Lync VDI est activé, l’utilisateur suit les étapes suivantes lors de la connexion à Skype entreprise sur le bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="f8c96-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="f8c96-136">L’utilisateur tape ses informations d’identification sur le client Skype entreprise exécuté sur le bureau virtuel.</span><span class="sxs-lookup"><span data-stu-id="f8c96-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="f8c96-137">Après avoir détecté le plug-in Lync VDI, Skype entreprise invite l’utilisateur à entrer de nouveau les informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="f8c96-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="f8c96-138">Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f8c96-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="f8c96-139">Skype entreprise commence à jumeler avec le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f8c96-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="f8c96-140">Lorsque cela se produit, le client affiche deux icônes dans la barre d’état Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f8c96-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="f8c96-141">L’icône située dans le coin inférieur gauche indique qu’aucun périphérique audio n’est disponible et que l’icône clignotant dans le coin inférieur droit indique que le jumelage VDI est en cours: a.</span><span class="sxs-lookup"><span data-stu-id="f8c96-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="f8c96-142">Après le jumelage de l’infrastructure VDI, les icônes changent pour indiquer le périphérique audio à utiliser pour les appels et le succès du jumelage d’un appareil VDI: b.</span><span class="sxs-lookup"><span data-stu-id="f8c96-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="f8c96-143">L’utilisateur peut maintenant voir son statut de connexion sur les appareils compatibles Skype entreprise qui sont connectés à l’ordinateur local, et les appels et les réponses habituelles.</span><span class="sxs-lookup"><span data-stu-id="f8c96-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="f8c96-144">Résolution des problèmes du plug-in Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f8c96-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="f8c96-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c96-145"></span></span>

<span data-ttu-id="f8c96-146">Reportez-vous aux sections suivantes si vous rencontrez des problèmes après l’installation du plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f8c96-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="f8c96-147">Problèmes d’installation du plug-in Lync VDI </span><span class="sxs-lookup"><span data-stu-id="f8c96-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="f8c96-148">Si vous rencontrez des problèmes lors de l’installation du plug-in Lync VDI, vérifiez les points suivants:</span><span class="sxs-lookup"><span data-stu-id="f8c96-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="f8c96-149">Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.</span><span class="sxs-lookup"><span data-stu-id="f8c96-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="f8c96-150">Assurez-vous que la protection en écriture est désactivée.</span><span class="sxs-lookup"><span data-stu-id="f8c96-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="f8c96-151">Pour obtenir des instructions, consultez la documentation fournie par le fabricant de votre appareil.</span><span class="sxs-lookup"><span data-stu-id="f8c96-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f8c96-152">Résolution des problèmes liés au jumelage</span><span class="sxs-lookup"><span data-stu-id="f8c96-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f8c96-153">Lorsque le jumelage du plug-in Lync VDI échoue, l’icône de jumelage dans le coin inférieur droit s’affiche sous la forme d’un «X» rouge, comme illustré ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="f8c96-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="f8c96-154">Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier. </span><span class="sxs-lookup"><span data-stu-id="f8c96-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="f8c96-155">**L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**</span><span class="sxs-lookup"><span data-stu-id="f8c96-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f8c96-156">Pour que l’utilisateur se déconnecte de Skype entreprise, vous devez vous reconnecter avec les informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="f8c96-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="f8c96-157">La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.</span><span class="sxs-lookup"><span data-stu-id="f8c96-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="f8c96-158">**Une autre instance du client Bureau à distance est en cours d’exécution.**</span><span class="sxs-lookup"><span data-stu-id="f8c96-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f8c96-159">S’ils utilisent une connexion Bureau à distance dans Windows, les utilisateurs doivent procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="f8c96-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="f8c96-160">Démarrez le Gestionnaire des tâches : appuyez sur \*\*Alt+Ctrl+Suppr \*\*, puis cliquez sur **Démarrer le Gestionnaire des tâches**.</span><span class="sxs-lookup"><span data-stu-id="f8c96-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="f8c96-161">Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f8c96-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="f8c96-162">Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**. </span><span class="sxs-lookup"><span data-stu-id="f8c96-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="f8c96-163">Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter. </span><span class="sxs-lookup"><span data-stu-id="f8c96-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="f8c96-164">**Les fichiers nécessaires n’ont pas été installés correctement.**</span><span class="sxs-lookup"><span data-stu-id="f8c96-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f8c96-165">Une fois le plug-in installé sur l’ordinateur local, vérifiez que les fichiers suivants se trouvent sous C:\Program Files\Microsoft Office\Office15 (ou la lettre de lecteur qui convient) :</span><span class="sxs-lookup"><span data-stu-id="f8c96-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="f8c96-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="f8c96-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="f8c96-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="f8c96-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="f8c96-168">**Le client Skype entreprise est en cours d’exécution sur l’ordinateur local.**</span><span class="sxs-lookup"><span data-stu-id="f8c96-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f8c96-169">Pour utiliser le plug-in Lync VDI, un client Skype entreprise ne doit pas être en cours d’exécution sur l’ordinateur local, sinon le jumelage échoue.</span><span class="sxs-lookup"><span data-stu-id="f8c96-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f8c96-170">En règle générale, l’utilisateur ne doit pas installer un client Skype entreprise sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f8c96-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f8c96-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8c96-171">See also</span></span>
<span data-ttu-id="f8c96-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c96-172"></span></span>

[<span data-ttu-id="f8c96-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="f8c96-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
