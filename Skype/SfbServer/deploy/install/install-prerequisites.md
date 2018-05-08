---
title: Installation des composants prérequis pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : En savoir plus sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6d11b83cf760b47072bca743b6fe3b5fac3794d9
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="d1055-104">Installation des composants prérequis pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d1055-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1055-105">**Résumé :** Obtenir des informations sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d1055-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="d1055-106">Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="d1055-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="d1055-107">L’installation des conditions préalables consiste à mettre en place Windows Server en installant les fonctionnalités et rôles requis pour chaque serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="d1055-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="d1055-108">Les conditions sont basées sur le rôle que le serveur va jouer dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="d1055-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="d1055-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="d1055-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="d1055-110">Cependant, vous devez suivre les étapes 6, 7, et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué sur le diagramme.</span><span class="sxs-lookup"><span data-stu-id="d1055-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="d1055-111">L’installation des conditions préalables est présentée dans l’étape 1 sur 8.</span><span class="sxs-lookup"><span data-stu-id="d1055-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Schéma de vue d’ensemble - Composants prérequis pour l’installation.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="d1055-113">Mise en place de Windows Server</span><span class="sxs-lookup"><span data-stu-id="d1055-113">Setup Windows Server</span></span>

<span data-ttu-id="d1055-114">Skype pour Business Server 2015 requiert le système d’exploitation Windows Server et un certain nombre de conditions préalables avant de pouvoir installer.</span><span class="sxs-lookup"><span data-stu-id="d1055-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="d1055-115">Pour plus d’informations sur la planification des conditions préalables, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1055-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="d1055-p105">Cette procédure se base sur Windows Server 2012 R2. Si vous utilisez une version différente de Windows Server, la procédure peut être légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="d1055-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d1055-118">Avant de commencer, assurez-vous que Windows Server est mise à jour à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="d1055-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="d1055-120">Regardez la vidéo des étapes pour **installer les composants requis** :</span><span class="sxs-lookup"><span data-stu-id="d1055-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="d1055-121">Installez les fonctionnalités et rôles requis pour les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="d1055-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="d1055-122">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajouter des rôles et fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="d1055-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="d1055-123">Lisez la page **Avant de commencer** pour vous familiariser avec l’installation des rôles et fonctionnalités dans Windows Server, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d1055-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="d1055-124">Sélectionnez une **Installation basée sur un rôle ou une fonctionnalité**, et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d1055-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="d1055-125">Sélectionnez le serveur sur lequel vous seront installation Skype pour Business Server 2015, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d1055-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="d1055-126">Sélectionnez le rôle du **Serveur Web (IIS)**, et lorsque la fenêtre des fonctionnalités requises s’ouvre, cliquez sur **Ajouter des fonctionnalités**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d1055-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="d1055-127">Assurez-vous que les fonctions logicielles répertoriées dans le [logiciel qui doit être installé avant un Skype pour le déploiement de Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) sont sur le serveur qui exécutera Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d1055-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="d1055-128">Voici une liste abrégée :</span><span class="sxs-lookup"><span data-stu-id="d1055-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="d1055-129">Fonctionnalités de .NET framework</span><span class="sxs-lookup"><span data-stu-id="d1055-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="d1055-130">Services WCF</span><span class="sxs-lookup"><span data-stu-id="d1055-130">WCF Services</span></span>
    
   - <span data-ttu-id="d1055-131">Activation HTTP</span><span class="sxs-lookup"><span data-stu-id="d1055-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1055-p107">L’activation HTTP requiert des fonctionnalités supplémentaires. Cliquez sur **Ajouter des fonctionnalités** dans la boîte de dialogue d’avertissement qui s’ouvre lorsque vous sélectionnez l’activation HTTP.</span><span class="sxs-lookup"><span data-stu-id="d1055-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="d1055-134">Media Foundation (requis par les serveurs Standard Edition et les serveurs frontaux utilisés pour la conférence).</span><span class="sxs-lookup"><span data-stu-id="d1055-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="d1055-135">Outils d’administration de serveur distant</span><span class="sxs-lookup"><span data-stu-id="d1055-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="d1055-136">Outils d’administration de rôles</span><span class="sxs-lookup"><span data-stu-id="d1055-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="d1055-137">SERVICES AD DS</span><span class="sxs-lookup"><span data-stu-id="d1055-137">AD DS</span></span> 
    
   - <span data-ttu-id="d1055-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="d1055-138">AD LDS</span></span>
    
   - <span data-ttu-id="d1055-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="d1055-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="d1055-140">Cliquez sur **Suivant** pour continuer avec l’assistant.</span><span class="sxs-lookup"><span data-stu-id="d1055-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="d1055-141">Lisez les remarques sur le **Rôle de serveur web (IIS)**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d1055-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="d1055-142">Sélectionnez les **services de rôle de serveur web (IIS)** suivants.</span><span class="sxs-lookup"><span data-stu-id="d1055-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="d1055-143">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="d1055-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="d1055-144">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="d1055-144">Default Document</span></span>
    
   - <span data-ttu-id="d1055-145">Exploration des répertoires</span><span class="sxs-lookup"><span data-stu-id="d1055-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="d1055-146">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="d1055-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="d1055-147">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="d1055-147">Static Content</span></span>
    
   - <span data-ttu-id="d1055-148">Intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="d1055-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="d1055-149">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="d1055-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="d1055-150">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="d1055-150">Logging Tools</span></span>
    
   - <span data-ttu-id="d1055-151">Suivi</span><span class="sxs-lookup"><span data-stu-id="d1055-151">Tracing</span></span>
    
   - <span data-ttu-id="d1055-152">Performances</span><span class="sxs-lookup"><span data-stu-id="d1055-152">Performance</span></span>
    
   - <span data-ttu-id="d1055-153">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="d1055-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="d1055-154">Compression du contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="d1055-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="d1055-155">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d1055-155">Security</span></span>
    
   - <span data-ttu-id="d1055-156">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="d1055-156">Request Filtering</span></span>
    
   - <span data-ttu-id="d1055-157">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="d1055-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="d1055-158">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="d1055-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="d1055-159">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="d1055-159">Application Development</span></span>
    
   - <span data-ttu-id="d1055-160">.NET Extensibility 3.5</span><span class="sxs-lookup"><span data-stu-id="d1055-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="d1055-161">.NET Extensibility 4.5</span><span class="sxs-lookup"><span data-stu-id="d1055-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="d1055-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="d1055-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="d1055-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="d1055-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="d1055-164">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="d1055-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="d1055-165">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="d1055-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="d1055-166">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="d1055-166">Management Tools</span></span>
    
   - <span data-ttu-id="d1055-167">Console de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="d1055-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="d1055-168">Scripts et outils de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="d1055-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="d1055-169">Cliquez sur **Suivant** pour continuer avec l’assistant.</span><span class="sxs-lookup"><span data-stu-id="d1055-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="d1055-170">Vérifiez les choix d’installation pour vous assurer que toutes les conditions sont sélectionnées, puis cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="d1055-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d1055-171">Windows Server 2012 R2 n’installe pas tous les fichiers source pour les fonctionnalités requises par défaut.</span><span class="sxs-lookup"><span data-stu-id="d1055-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="d1055-172">Si le serveur n’est pas connecté à internet, vous devrez installer le média Windows Server 2012 R2 et sélectionner **Spécifier un autre chemin d’accès source** afin d’installer les fonctionnalités requises.</span><span class="sxs-lookup"><span data-stu-id="d1055-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="d1055-173">Les fichiers source se trouvent dans le répertoire sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="d1055-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="d1055-174">Par exemple, si le média Windows Server 2012 R2 se trouve dans le lecteur D, sélectionnez le chemin d’accès vers `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="d1055-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="d1055-175">> Il est important que vous avez les dernières mises à jour à partir de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="d1055-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="d1055-176">Si vous n’êtes pas connecté à internet, vous devrez installer manuellement toutes les mises à jour appropriées et toutes les conditions préalables pour les mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="d1055-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="d1055-177">Lorsque la boîte de dialogue indiquera que l’installation a bien été effectuée, vous devrez redémarrer le serveur pour terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="d1055-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="d1055-178">Réexécutez **Windows Update** pour vérifier les mises à jour pour les rôles et services qui ont été installés.</span><span class="sxs-lookup"><span data-stu-id="d1055-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="d1055-179">Si vous utilisez Skype pour le panneau de configuration serveur Business sur ce serveur vous devez également installer Silverlight.</span><span class="sxs-lookup"><span data-stu-id="d1055-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="d1055-180">Pour installer Silverlight, voir [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="d1055-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="d1055-181">Vous pouvez installer les conditions préalables en exécutant la commande PowerShell suivante.</span><span class="sxs-lookup"><span data-stu-id="d1055-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="d1055-182">Veuillez noter que la commande recherche des fichiers source dans un ordre spécifique.</span><span class="sxs-lookup"><span data-stu-id="d1055-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="d1055-183">Si vous êtes connecté à internet, la commande aura accès à Windows Update.</span><span class="sxs-lookup"><span data-stu-id="d1055-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="d1055-184">Si vous n’êtes pas connecté à internet, vous devrez vous assurer que les fichiers source sont accessibles à la commande.</span><span class="sxs-lookup"><span data-stu-id="d1055-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="d1055-185">Pour plus d’informations sur l’utilisation de PowerShell pour installer des rôles et fonctionnalités, voir [installer ou désinstaller des rôles, Services de rôle ou fonctionnalités](https://technet.microsoft.com/en-us/library/hh831809.aspx) et [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1055-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="d1055-186">N’oubliez pas de réexécuter Windows Update après avoir installé les conditions préalables, même si vous utilisez la commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1055-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="d1055-187">Les conditions préalables pour les serveurs ayant d’autres rôles que celui de serveur frontal (notamment les rôles de directeur, de conversation permanente, ou Edge) ont leurs propres conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="d1055-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="d1055-188">Pour plus d’informations sur la configuration exacte requise par chaque type de serveur, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1055-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

