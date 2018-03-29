---
title: Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : Lisez cette rubrique pour savoir comment mettre à niveau le Gestionnaire de statistiques pour Skype pour Business Server 2015.'
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="34c22-103">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="34c22-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="34c22-104">**Résumé :** Lisez cette rubrique pour savoir comment mettre à niveau le Gestionnaire de statistiques pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="34c22-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="34c22-105">Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire des statistiques pour Skype pour Business Server, un outil puissant qui vous permet d’afficher les Skype pour les données de santé et les performances de serveur d’entreprise en temps réel.</span><span class="sxs-lookup"><span data-stu-id="34c22-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="34c22-106">Vous pouvez interroger les données de performance sur des centaines de serveurs toutes les quelques secondes et afficher les résultats d’instantanément sur le site Web du Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="34c22-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="34c22-107">Pour plus d’informations sur le Gestionnaire de statistiques et les nouvelles fonctionnalités de la version 1.1, consultez [planification pour le Gestionnaire de statistiques pour Skype pour Business Server 2015](plan.md) et [Déployer le Gestionnaire de statistiques pour Skype pour Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="34c22-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="34c22-108">Pour plus d'informations sur les problèmes connus résolus dans la version 1.1, reportez-vous à la rubrique [Problèmes connus résolus dans la version 1.1](upgrade.md#BKMK_Fixed).</span><span class="sxs-lookup"><span data-stu-id="34c22-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="34c22-109">Il existe deux méthodes de mise à niveau :</span><span class="sxs-lookup"><span data-stu-id="34c22-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="34c22-110">**Mise à niveau automatique.**</span><span class="sxs-lookup"><span data-stu-id="34c22-110">**Automated upgrade.**</span></span> <span data-ttu-id="34c22-111">Cette méthode utilise un script automatisé.</span><span class="sxs-lookup"><span data-stu-id="34c22-111">This method uses an automated script.</span></span> <span data-ttu-id="34c22-112">Elle est la méthode la plus simple et devrait être applicable à tous les scénarios de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="34c22-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="34c22-113">**Mise à niveau manuelle.**</span><span class="sxs-lookup"><span data-stu-id="34c22-113">**Manual upgrade.**</span></span> <span data-ttu-id="34c22-114">Cette méthode est fournie sous la forme d’un plan de sauvegarde dans le cas rare que la mise à niveau automatique échoue.</span><span class="sxs-lookup"><span data-stu-id="34c22-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="34c22-115">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="34c22-115">Prerequisites</span></span>

<span data-ttu-id="34c22-116">Avant d’effectuer la mise à niveau, assurez-vous de disposer des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="34c22-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="34c22-117">Empreinte numérique de certificat d’écouteur actif</span><span class="sxs-lookup"><span data-stu-id="34c22-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="34c22-118">Mot de passe du service d’écoute (saisi lors de l’installation de l’écouteur et de chaque agent)</span><span class="sxs-lookup"><span data-stu-id="34c22-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="34c22-119">Configuration du certificat SSL du site web</span><span class="sxs-lookup"><span data-stu-id="34c22-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="34c22-120">Mise à niveau automatique</span><span class="sxs-lookup"><span data-stu-id="34c22-120">Automated upgrade</span></span>

<span data-ttu-id="34c22-121">Le script collecte les informations concernant votre certificat actuel ainsi que le mot de passe de l’écouteur et désinstalle l’ancienne version du produit avant d’installer la nouvelle.</span><span class="sxs-lookup"><span data-stu-id="34c22-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="34c22-122">L’instance Redis installée sur le serveur n’en est pas affectée, de sorte que toutes les données stockées dans la mémoire cache sont conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="34c22-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="34c22-123">Placez les fichiers MSI pour la nouvelle version de l’agent, un récepteur et un site Web avec le script de mise à jour-StatsMan.ps1 dans un dossier unique sur l’ordinateur récepteur.</span><span class="sxs-lookup"><span data-stu-id="34c22-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="34c22-124">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34c22-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="34c22-125">Mettez à niveau l’écouteur :</span><span class="sxs-lookup"><span data-stu-id="34c22-125">Upgrade the Listener component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> <span data-ttu-id="34c22-126">Le mot de passe du service Gestionnaire de statistiques s’afficheront en texte clair sur la ligne de commande lorsqu’elle est transmise à l’installateur.</span><span class="sxs-lookup"><span data-stu-id="34c22-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="34c22-127">Par conséquent, assurez-vous de protéger convenablement votre moniteur.</span><span class="sxs-lookup"><span data-stu-id="34c22-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="34c22-128">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="34c22-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="34c22-129">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="34c22-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="34c22-130">Si le service d’écoute est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="34c22-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="34c22-131">Autoriser l’application se ferme (l’écouteur statistiques Manager service va être arrêté).</span><span class="sxs-lookup"><span data-stu-id="34c22-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="34c22-132">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="34c22-132">Continue the install process.</span></span> <span data-ttu-id="34c22-133">Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés.</span><span class="sxs-lookup"><span data-stu-id="34c22-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="34c22-134">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="34c22-134">If not, add the values you saved before continuing.</span></span>
    
3. <span data-ttu-id="34c22-135">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34c22-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="34c22-136">Mettez à niveau le site web :</span><span class="sxs-lookup"><span data-stu-id="34c22-136">Upgrade the Website component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. <span data-ttu-id="34c22-137">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="34c22-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="34c22-138">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="34c22-138">Answer Yes.</span></span>
    
2. <span data-ttu-id="34c22-139">Si le service d’agent est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="34c22-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="34c22-140">Autorisez la fermeture de l’application (le service d’agent StatsMan sera arrêté).</span><span class="sxs-lookup"><span data-stu-id="34c22-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
3. <span data-ttu-id="34c22-141">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="34c22-141">Continue the install process.</span></span> <span data-ttu-id="34c22-142">Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés.</span><span class="sxs-lookup"><span data-stu-id="34c22-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="34c22-143">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="34c22-143">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="34c22-144">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34c22-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="34c22-145">Mettez à niveau l’agent :</span><span class="sxs-lookup"><span data-stu-id="34c22-145">Upgrade the Agent component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. <span data-ttu-id="34c22-146">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="34c22-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="34c22-147">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="34c22-147">Answer Yes.</span></span>
    
2. <span data-ttu-id="34c22-148">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="34c22-148">Continue the install process.</span></span> <span data-ttu-id="34c22-149">Normalement, le port du site web est déjà renseigné.</span><span class="sxs-lookup"><span data-stu-id="34c22-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="34c22-150">Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="34c22-150">If not, add the value you saved before continuing.</span></span>
    
3. <span data-ttu-id="34c22-151">Vérifiez que le site web fonctionne correctement à l’aide du navigateur.</span><span class="sxs-lookup"><span data-stu-id="34c22-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="34c22-152">La mise à niveau de l’agent peut être effectuée avec le commutateur -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="34c22-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="34c22-153">Ainsi, le processus d’installation/désinstallation s’exécute silencieusement, ce qui permet à des outils tels que PSExec d’exécuter à distance la mise à niveau sur un grand nombre de serveurs.</span><span class="sxs-lookup"><span data-stu-id="34c22-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="34c22-154">Mise à niveau manuelle</span><span class="sxs-lookup"><span data-stu-id="34c22-154">Manual upgrade</span></span>

<span data-ttu-id="34c22-155">Si, pour une raison ou pour une autre, la mise à niveau automatique échoue, vous pouvez toujours effectuer une mise à niveau manuelle en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="34c22-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="34c22-156">	Sur l’ordinateur d’écoute, désinstallez l’écouteur, le site web et l’agent (s’il était installée sur ce serveur) à l’aide du panneau de commande Programmes et fonctionnalités.  </span><span class="sxs-lookup"><span data-stu-id="34c22-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="34c22-157"> Ne désinstallez pas Redis, afin que les données dans la mémoire cache soient conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="34c22-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="34c22-p119">	Installez les nouvelles versions de ces composants, y compris les valeurs que vous avez enregistrées précédemment lorsqu’elles vous sont demandées. Pour plus d’informations sur l’installation des composants, consultez la rubrique [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="34c22-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="34c22-160">Problèmes connus résolus dans la version 1.1</span><span class="sxs-lookup"><span data-stu-id="34c22-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="34c22-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="34c22-161"></span></span>

<span data-ttu-id="34c22-162">Les problèmes connus suivants ont été corrigés dans la version 1.1 :</span><span class="sxs-lookup"><span data-stu-id="34c22-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="34c22-163">L’interface utilisateur/serveur/Agent - nombreuses la fiabilité et performances</span><span class="sxs-lookup"><span data-stu-id="34c22-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="34c22-164">L’interface utilisateur - principal filtre contrôle maintenant trie correctement avec des casses différentes (a été de pointe qui fait de certains serveurs n’étaient pas dans le système lorsqu’elles étaient)</span><span class="sxs-lookup"><span data-stu-id="34c22-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="34c22-165">Server : les composants du serveur peuvent désormais être installés sur des serveurs qui ne sont pas en anglais.</span><span class="sxs-lookup"><span data-stu-id="34c22-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="34c22-166">Serveur/Agent : dans certains cas, les composants de l’agent et du serveur ne pouvaient pas être installés à cause d’erreurs .NET dues à une version spécifique de .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="34c22-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="34c22-167">Ce problème est résolu.</span><span class="sxs-lookup"><span data-stu-id="34c22-167">This has been resolved.</span></span>
    
- <span data-ttu-id="34c22-168">Agent - l’enregistrement des événements étendu ajouté pour le StatsMan Agent.</span><span class="sxs-lookup"><span data-stu-id="34c22-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="34c22-169">L’agent ne se bloque plus lorsqu’il est installé sur un serveur qui n’est pas dans la topologie ; cette situation est désormais consignée dans le journal d’événements, avec de nombreuses autres conditions d’erreurs possibles.</span><span class="sxs-lookup"><span data-stu-id="34c22-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="34c22-170">L’interface utilisateur - les clients Web via le navigateur Chrome voir plusieurs invites d’ouverture de session lors de l’utilisation d’un ordinateur client non joints au même groupe de travail ou domaine que le serveur Web du Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="34c22-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="34c22-171">Désormais, une seule connexion par session suffit.</span><span class="sxs-lookup"><span data-stu-id="34c22-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="34c22-172">Pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="34c22-172">For more information</span></span>
<span data-ttu-id="34c22-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="34c22-173"></span></span>

<span data-ttu-id="34c22-174">Pour plus d'informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="34c22-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="34c22-175">Planification pour le Gestionnaire de statistiques pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34c22-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="34c22-176">Déployer le Gestionnaire de statistiques pour Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34c22-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="34c22-177">Résoudre les problèmes de statistiques responsable Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34c22-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="34c22-178">Skype pour Business Server Manager statistiques de blog</span><span class="sxs-lookup"><span data-stu-id="34c22-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

