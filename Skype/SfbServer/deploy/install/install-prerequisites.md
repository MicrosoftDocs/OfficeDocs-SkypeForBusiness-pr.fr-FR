---
title: Installation des composants prérequis pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : En savoir plus sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="f4524-104">Installation des composants prérequis pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="f4524-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f4524-105">**Résumé :** Obtenir des informations sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f4524-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="f4524-106">Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="f4524-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="f4524-107">L’installation des conditions préalables consiste à mettre en place Windows Server en installant les fonctionnalités et rôles requis pour chaque serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="f4524-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="f4524-108">Les conditions sont basées sur le rôle que le serveur va jouer dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="f4524-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="f4524-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="f4524-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="f4524-110">Cependant, vous devez suivre les étapes 6, 7, et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué sur le diagramme.</span><span class="sxs-lookup"><span data-stu-id="f4524-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="f4524-111">L’installation des conditions préalables est présentée dans l’étape 1 sur 8.</span><span class="sxs-lookup"><span data-stu-id="f4524-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Schéma de vue d’ensemble - Composants prérequis pour l’installation.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="f4524-113">Mise en place de Windows Server</span><span class="sxs-lookup"><span data-stu-id="f4524-113">Setup Windows Server</span></span>

<span data-ttu-id="f4524-114">Skype pour Business Server 2015 nécessite le système d’exploitation Windows et un certain nombre de conditions préalables avant de pouvoir l’installer.</span><span class="sxs-lookup"><span data-stu-id="f4524-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="f4524-115">Pour plus d’informations sur la planification de la configuration requise, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4524-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="f4524-p105">Cette procédure se base sur Windows Server 2012 R2. Si vous utilisez une version différente de Windows Server, la procédure peut être légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="f4524-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f4524-118">Avant de commencer, assurez-vous que le serveur Windows est à jour à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f4524-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="f4524-120">Regardez la vidéo des étapes pour **installer les composants requis** :</span><span class="sxs-lookup"><span data-stu-id="f4524-120">Watch the video steps for **install prerequisites**:</span></span>
  
![Votre navigateur ne prend pas en charge la vidéo. Installez Microsoft Silverlight, Adobe Flash Player ou Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="f4524-123">Installez les fonctionnalités et rôles requis pour les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="f4524-123">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="f4524-124">Ouvrez le Gestionnaire de serveur et cliquez sur **Ajouter des rôles et fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="f4524-124">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="f4524-125">Lisez la page **Avant de commencer** pour vous familiariser avec l’installation des rôles et fonctionnalités dans Windows Server, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4524-125">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="f4524-126">Sélectionnez une **Installation basée sur un rôle ou une fonctionnalité**, et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4524-126">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="f4524-127">Sélectionnez le serveur sur lequel vous fera l’installation Skype pour Business Server 2015, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4524-127">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="f4524-128">Sélectionnez le rôle du **Serveur Web (IIS)**, et lorsque la fenêtre des fonctionnalités requises s’ouvre, cliquez sur **Ajouter des fonctionnalités**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4524-128">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f4524-129">Assurez-vous que les fonctions logicielles répertoriées dans le [logiciel qui doit être installé avant un Skype pour le déploiement de Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) sont sur le serveur qui exécutera Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f4524-129">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="f4524-130">Voici une liste abrégée :</span><span class="sxs-lookup"><span data-stu-id="f4524-130">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="f4524-131">Fonctionnalités du.NET Framework</span><span class="sxs-lookup"><span data-stu-id="f4524-131">.NET Framework Features</span></span>
    
   - <span data-ttu-id="f4524-132">Services WCF</span><span class="sxs-lookup"><span data-stu-id="f4524-132">WCF Services</span></span>
    
   - <span data-ttu-id="f4524-133">Activation HTTP</span><span class="sxs-lookup"><span data-stu-id="f4524-133">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4524-p108">L’activation HTTP requiert des fonctionnalités supplémentaires. Cliquez sur **Ajouter des fonctionnalités** dans la boîte de dialogue d’avertissement qui s’ouvre lorsque vous sélectionnez l’activation HTTP.</span><span class="sxs-lookup"><span data-stu-id="f4524-p108">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="f4524-136">Media Foundation (requis par les serveurs Standard Edition et les serveurs frontaux utilisés pour la conférence).</span><span class="sxs-lookup"><span data-stu-id="f4524-136">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="f4524-137">Outils d’administration de serveur distant</span><span class="sxs-lookup"><span data-stu-id="f4524-137">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="f4524-138">Outils d’administration de rôles</span><span class="sxs-lookup"><span data-stu-id="f4524-138">Role Administration Tools</span></span>
    
   - <span data-ttu-id="f4524-139">SERVICES AD DS</span><span class="sxs-lookup"><span data-stu-id="f4524-139">AD DS</span></span> 
    
   - <span data-ttu-id="f4524-140">AD LDS</span><span class="sxs-lookup"><span data-stu-id="f4524-140">AD LDS</span></span>
    
   - <span data-ttu-id="f4524-141">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="f4524-141">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="f4524-142">Cliquez sur **Suivant** pour continuer avec l’assistant.</span><span class="sxs-lookup"><span data-stu-id="f4524-142">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="f4524-143">Lisez les remarques sur le **Rôle de serveur web (IIS)**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4524-143">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="f4524-144">Sélectionnez les **services de rôle de serveur web (IIS)** suivants.</span><span class="sxs-lookup"><span data-stu-id="f4524-144">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="f4524-145">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="f4524-145">Common HTTP Features</span></span>
    
   - <span data-ttu-id="f4524-146">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="f4524-146">Default Document</span></span>
    
   - <span data-ttu-id="f4524-147">Exploration des répertoires</span><span class="sxs-lookup"><span data-stu-id="f4524-147">Directory Browsing</span></span>
    
   - <span data-ttu-id="f4524-148">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="f4524-148">HTTP Errors</span></span>
    
   - <span data-ttu-id="f4524-149">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="f4524-149">Static Content</span></span>
    
   - <span data-ttu-id="f4524-150">Intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f4524-150">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="f4524-151">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="f4524-151">HTTP Logging</span></span>
    
   - <span data-ttu-id="f4524-152">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="f4524-152">Logging Tools</span></span>
    
   - <span data-ttu-id="f4524-153">Suivi</span><span class="sxs-lookup"><span data-stu-id="f4524-153">Tracing</span></span>
    
   - <span data-ttu-id="f4524-154">Performances</span><span class="sxs-lookup"><span data-stu-id="f4524-154">Performance</span></span>
    
   - <span data-ttu-id="f4524-155">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="f4524-155">Static Content Compression</span></span>
    
   - <span data-ttu-id="f4524-156">Compression du contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="f4524-156">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="f4524-157">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f4524-157">Security</span></span>
    
   - <span data-ttu-id="f4524-158">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="f4524-158">Request Filtering</span></span>
    
   - <span data-ttu-id="f4524-159">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="f4524-159">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="f4524-160">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="f4524-160">Windows Authentication</span></span>
    
   - <span data-ttu-id="f4524-161">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f4524-161">Application Development</span></span>
    
   - <span data-ttu-id="f4524-162">.NET Extensibility 3.5</span><span class="sxs-lookup"><span data-stu-id="f4524-162">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="f4524-163">.NET Extensibility 4.5</span><span class="sxs-lookup"><span data-stu-id="f4524-163">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="f4524-164">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="f4524-164">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="f4524-165">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="f4524-165">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="f4524-166">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="f4524-166">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="f4524-167">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="f4524-167">ISAPI Filters</span></span>
    
   - <span data-ttu-id="f4524-168">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="f4524-168">Management Tools</span></span>
    
   - <span data-ttu-id="f4524-169">Console de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="f4524-169">IIS Management Console</span></span>
    
   - <span data-ttu-id="f4524-170">Scripts et outils de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="f4524-170">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="f4524-171">Cliquez sur **Suivant** pour continuer avec l’assistant.</span><span class="sxs-lookup"><span data-stu-id="f4524-171">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="f4524-172">Vérifiez les choix d’installation pour vous assurer que toutes les conditions sont sélectionnées, puis cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="f4524-172">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f4524-173">Windows Server 2012 R2 n’installe pas tous les fichiers source pour les fonctionnalités requises par défaut.</span><span class="sxs-lookup"><span data-stu-id="f4524-173">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="f4524-174">Si le serveur n’est pas connecté à internet, vous devrez installer le média Windows Server 2012 R2 et sélectionner **Spécifier un autre chemin d’accès source** afin d’installer les fonctionnalités requises.</span><span class="sxs-lookup"><span data-stu-id="f4524-174">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="f4524-175">Les fichiers source se trouvent dans le répertoire sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="f4524-175">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="f4524-176">Par exemple, si le média Windows Server 2012 R2 se trouve dans le lecteur D, sélectionnez le chemin d’accès vers `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="f4524-176">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="f4524-177">> Il est important que vous avez les dernières mises à jour à partir de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f4524-177">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="f4524-178">Si vous n’êtes pas connecté à internet, vous devrez installer manuellement toutes les mises à jour appropriées et toutes les conditions préalables pour les mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="f4524-178">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="f4524-179">Lorsque la boîte de dialogue indiquera que l’installation a bien été effectuée, vous devrez redémarrer le serveur pour terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="f4524-179">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="f4524-180">Réexécutez **Windows Update** pour vérifier les mises à jour pour les rôles et services qui ont été installés.</span><span class="sxs-lookup"><span data-stu-id="f4524-180">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="f4524-181">Si vous utilisez Skype pour le panneau de configuration de Business Server sur ce serveur vous devez également installer Silverlight.</span><span class="sxs-lookup"><span data-stu-id="f4524-181">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="f4524-182">Pour installer Silverlight, consultez [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="f4524-182">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="f4524-183">Vous pouvez installer les conditions préalables en exécutant la commande PowerShell suivante.</span><span class="sxs-lookup"><span data-stu-id="f4524-183">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="f4524-184">Veuillez noter que la commande recherche des fichiers source dans un ordre spécifique.</span><span class="sxs-lookup"><span data-stu-id="f4524-184">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="f4524-185">Si vous êtes connecté à internet, la commande aura accès à Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f4524-185">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="f4524-186">Si vous n’êtes pas connecté à internet, vous devrez vous assurer que les fichiers source sont accessibles à la commande.</span><span class="sxs-lookup"><span data-stu-id="f4524-186">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="f4524-187">Pour plus d’informations sur l’utilisation de PowerShell pour installer des rôles et fonctionnalités, consultez [installer ou désinstaller des rôles, Services de rôle ou fonctionnalités](https://technet.microsoft.com/en-us/library/hh831809.aspx) et [Installation-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="f4524-187">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="f4524-188">N’oubliez pas de réexécuter Windows Update après avoir installé les conditions préalables, même si vous utilisez la commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4524-188">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="f4524-189">Les conditions préalables pour les serveurs ayant d’autres rôles que celui de serveur frontal (notamment les rôles de directeur, de conversation permanente, ou Edge) ont leurs propres conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="f4524-189">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="f4524-190">Pour plus d’informations sur les composants d’exacts requis par chaque type de serveur, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4524-190">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

