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
description: 'Résumé : Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server 2015.'
ms.openlocfilehash: d10dd5cd92fc0d7dbbb3285c43df78e8149f58c0
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295705"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="5e49d-103">Upgrade Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e49d-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e49d-104">**Résumé :** Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5e49d-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5e49d-105">Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire de statistiques de Skype pour Business Server, un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="5e49d-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="5e49d-106">Vous pouvez interroger les données de performance sur des centaines de serveurs après quelques secondes et afficher les résultats instantanément sur le site Web de gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="5e49d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="5e49d-107">Pour plus d’informations sur les statistiques Manager et les nouvelles fonctionnalités de la version 1.1, voir [planification pour le Gestionnaire de statistiques de Skype pour Business Server 2015](plan.md) et [Déployer des statistiques responsable Skype pour Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="5e49d-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="5e49d-108">Pour plus d'informations sur les problèmes connus résolus dans la version 1.1, reportez-vous à la rubrique [Problèmes connus résolus dans la version 1.1](upgrade.md#BKMK_Fixed).</span><span class="sxs-lookup"><span data-stu-id="5e49d-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="5e49d-109">Il existe deux méthodes de mise à niveau :</span><span class="sxs-lookup"><span data-stu-id="5e49d-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="5e49d-110">**Mise à niveau automatique.**</span><span class="sxs-lookup"><span data-stu-id="5e49d-110">**Automated upgrade.**</span></span> <span data-ttu-id="5e49d-111">Cette méthode utilise un script automatisé.</span><span class="sxs-lookup"><span data-stu-id="5e49d-111">This method uses an automated script.</span></span> <span data-ttu-id="5e49d-112">Il est la méthode la plus simple et s’applique à tous les scénarios de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5e49d-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="5e49d-113">**Mise à niveau manuelle.**</span><span class="sxs-lookup"><span data-stu-id="5e49d-113">**Manual upgrade.**</span></span> <span data-ttu-id="5e49d-114">Cette méthode est fournie en tant qu’un plan de sauvegarde dans le cas inhabituel qui échoue la mise à niveau automatisée.</span><span class="sxs-lookup"><span data-stu-id="5e49d-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="5e49d-115">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="5e49d-115">Prerequisites</span></span>

<span data-ttu-id="5e49d-116">Avant d’effectuer la mise à niveau, assurez-vous de disposer des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e49d-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="5e49d-117">Empreinte numérique de certificat d’écouteur actif</span><span class="sxs-lookup"><span data-stu-id="5e49d-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="5e49d-118">Mot de passe du service d’écoute (saisi lors de l’installation de l’écouteur et de chaque agent)</span><span class="sxs-lookup"><span data-stu-id="5e49d-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="5e49d-119">Configuration du certificat SSL du site web</span><span class="sxs-lookup"><span data-stu-id="5e49d-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="5e49d-120">Mise à niveau automatique</span><span class="sxs-lookup"><span data-stu-id="5e49d-120">Automated upgrade</span></span>

<span data-ttu-id="5e49d-121">Le script collecte les informations concernant votre certificat actuel ainsi que le mot de passe de l’écouteur et désinstalle l’ancienne version du produit avant d’installer la nouvelle.</span><span class="sxs-lookup"><span data-stu-id="5e49d-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="5e49d-122">L’instance Redis installée sur le serveur n’en est pas affectée, de sorte que toutes les données stockées dans la mémoire cache sont conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5e49d-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="5e49d-123">Placez les fichiers MSI pour la nouvelle version de l’agent, le port d’écoute et le site Web ainsi que le script de mise à jour-StatsMan.ps1 dans un seul dossier sur l’ordinateur du port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="5e49d-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="5e49d-124">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e49d-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="5e49d-125">Mettez à niveau l’écouteur :</span><span class="sxs-lookup"><span data-stu-id="5e49d-125">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="5e49d-126">Le mot de passe du service Gestionnaire de statistiques s’affichera en texte clair sur la ligne de commande, comme il est passé pour le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="5e49d-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="5e49d-127">Par conséquent, assurez-vous de protéger convenablement votre moniteur.</span><span class="sxs-lookup"><span data-stu-id="5e49d-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="5e49d-128">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="5e49d-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="5e49d-129">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="5e49d-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="5e49d-130">Si le service d’écoute est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="5e49d-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="5e49d-131">Autoriser l’application à fermer (le Gestionnaire de statistiques de port d’écoute service va s’arrêter).</span><span class="sxs-lookup"><span data-stu-id="5e49d-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="5e49d-132">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5e49d-132">Continue the install process.</span></span> <span data-ttu-id="5e49d-133">Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés.</span><span class="sxs-lookup"><span data-stu-id="5e49d-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="5e49d-134">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="5e49d-134">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="5e49d-135">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e49d-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="5e49d-136">Mettez à niveau le site web :</span><span class="sxs-lookup"><span data-stu-id="5e49d-136">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="5e49d-137">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="5e49d-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="5e49d-138">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="5e49d-138">Answer Yes.</span></span>
    
6. <span data-ttu-id="5e49d-139">Si le service d’agent est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="5e49d-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="5e49d-140">Autorisez la fermeture de l’application (le service d’agent StatsMan sera arrêté).</span><span class="sxs-lookup"><span data-stu-id="5e49d-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="5e49d-141">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5e49d-141">Continue the install process.</span></span> <span data-ttu-id="5e49d-142">Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés.</span><span class="sxs-lookup"><span data-stu-id="5e49d-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="5e49d-143">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="5e49d-143">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="5e49d-144">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e49d-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="5e49d-145">Mettez à niveau l’agent :</span><span class="sxs-lookup"><span data-stu-id="5e49d-145">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="5e49d-146">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="5e49d-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="5e49d-147">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="5e49d-147">Answer Yes.</span></span>
    
10. <span data-ttu-id="5e49d-148">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5e49d-148">Continue the install process.</span></span> <span data-ttu-id="5e49d-149">Normalement, le port du site web est déjà renseigné.</span><span class="sxs-lookup"><span data-stu-id="5e49d-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="5e49d-150">Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="5e49d-150">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="5e49d-151">Vérifiez que le site web fonctionne correctement à l’aide du navigateur.</span><span class="sxs-lookup"><span data-stu-id="5e49d-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5e49d-152">La mise à niveau de l’agent peut être effectuée avec le commutateur -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="5e49d-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="5e49d-153">Ainsi, le processus d’installation/désinstallation s’exécute silencieusement, ce qui permet à des outils tels que PSExec d’exécuter à distance la mise à niveau sur un grand nombre de serveurs.</span><span class="sxs-lookup"><span data-stu-id="5e49d-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="5e49d-154">Mise à niveau manuelle</span><span class="sxs-lookup"><span data-stu-id="5e49d-154">Manual upgrade</span></span>

<span data-ttu-id="5e49d-155">Si, pour une raison ou pour une autre, la mise à niveau automatique échoue, vous pouvez toujours effectuer une mise à niveau manuelle en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="5e49d-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="5e49d-156">	Sur l’ordinateur d’écoute, désinstallez l’écouteur, le site web et l’agent (s’il était installée sur ce serveur) à l’aide du panneau de commande Programmes et fonctionnalités.  </span><span class="sxs-lookup"><span data-stu-id="5e49d-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5e49d-157"> Ne désinstallez pas Redis, afin que les données dans la mémoire cache soient conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5e49d-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="5e49d-p119">	Installez les nouvelles versions de ces composants, y compris les valeurs que vous avez enregistrées précédemment lorsqu’elles vous sont demandées. Pour plus d’informations sur l’installation des composants, consultez la rubrique [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="5e49d-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="5e49d-160">Problèmes connus résolus dans la version 1.1</span><span class="sxs-lookup"><span data-stu-id="5e49d-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="5e49d-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="5e49d-161"></span></span>

<span data-ttu-id="5e49d-162">Les problèmes connus suivants ont été corrigés dans la version 1.1 :</span><span class="sxs-lookup"><span data-stu-id="5e49d-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="5e49d-163">L’interface utilisateur/serveur/Agent - nombreuses la fiabilité et performances</span><span class="sxs-lookup"><span data-stu-id="5e49d-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="5e49d-164">L’interface utilisateur - contrôle de filtre principal maintenant trie correctement avec différents cas (a été entraînant des personnes à prendre en compte certains serveurs n’ont pas été dans le système lorsqu’elles étaient)</span><span class="sxs-lookup"><span data-stu-id="5e49d-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="5e49d-165">Server : les composants du serveur peuvent désormais être installés sur des serveurs qui ne sont pas en anglais.</span><span class="sxs-lookup"><span data-stu-id="5e49d-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="5e49d-166">Serveur/Agent : dans certains cas, les composants de l’agent et du serveur ne pouvaient pas être installés à cause d’erreurs .NET dues à une version spécifique de .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="5e49d-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="5e49d-167">Ce problème est résolu.</span><span class="sxs-lookup"><span data-stu-id="5e49d-167">This has been resolved.</span></span>
    
- <span data-ttu-id="5e49d-168">Agent - enregistrement des événements étendu ajoutée pour le StatsMan Agent.</span><span class="sxs-lookup"><span data-stu-id="5e49d-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="5e49d-169">L’agent ne se bloque plus lorsqu’il est installé sur un serveur qui n’est pas dans la topologie ; cette situation est désormais consignée dans le journal d’événements, avec de nombreuses autres conditions d’erreurs possibles.</span><span class="sxs-lookup"><span data-stu-id="5e49d-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="5e49d-170">L’interface utilisateur - les clients Web à l’aide du navigateur Chrome voir plusieurs invites d’ouverture de session lorsqu’à l’aide d’un ordinateur client non lié à la même groupe de travail ou domaine que le serveur Web de gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="5e49d-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="5e49d-171">Désormais, une seule connexion par session suffit.</span><span class="sxs-lookup"><span data-stu-id="5e49d-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="5e49d-172">Pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="5e49d-172">For more information</span></span>
<span data-ttu-id="5e49d-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="5e49d-173"></span></span>

<span data-ttu-id="5e49d-174">Pour plus d’informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="5e49d-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="5e49d-175">Plan for Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e49d-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="5e49d-176">Deploy Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e49d-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="5e49d-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e49d-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="5e49d-178">Blog du gestionnaire de statistiques Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5e49d-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

