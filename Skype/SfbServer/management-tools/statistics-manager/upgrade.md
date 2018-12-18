---
title: Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server.'
ms.openlocfilehash: e2118377fc782af6818d070bc0bd3f5ddacab99e
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297894"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="bc594-103">Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="bc594-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="bc594-104">**Résumé :** Lisez cette rubrique pour savoir comment mettre à niveau des statistiques de gestionnaire de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc594-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="bc594-105">Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire de statistiques de Skype pour Business Server, un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="bc594-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="bc594-106">Vous pouvez interroger les données de performance sur des centaines de serveurs après quelques secondes et afficher les résultats instantanément sur le site Web de gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="bc594-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="bc594-107">Pour plus d’informations sur les statistiques Manager et les nouvelles fonctionnalités dans la version 2.0, voir [Planifier pour le Gestionnaire de statistiques de Skype pour Business Server](plan.md) et [Déployer des statistiques responsable Skype pour Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="bc594-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="bc594-108">Il existe deux méthodes de mise à niveau :</span><span class="sxs-lookup"><span data-stu-id="bc594-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="bc594-109">**Mise à niveau automatique.**</span><span class="sxs-lookup"><span data-stu-id="bc594-109">**Automated upgrade.**</span></span> <span data-ttu-id="bc594-110">Cette méthode utilise un script automatisé.</span><span class="sxs-lookup"><span data-stu-id="bc594-110">This method uses an automated script.</span></span> <span data-ttu-id="bc594-111">Il est la méthode la plus simple et s’applique à tous les scénarios de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bc594-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="bc594-112">**Mise à niveau manuelle.**</span><span class="sxs-lookup"><span data-stu-id="bc594-112">**Manual upgrade.**</span></span> <span data-ttu-id="bc594-113">Cette méthode est fournie en tant qu’un plan de sauvegarde dans le cas inhabituel qui échoue la mise à niveau automatisée.</span><span class="sxs-lookup"><span data-stu-id="bc594-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="bc594-114">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="bc594-114">Prerequisites</span></span>

<span data-ttu-id="bc594-115">Avant d’effectuer la mise à niveau, assurez-vous de disposer des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc594-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="bc594-116">Empreinte numérique de certificat d’écouteur actif</span><span class="sxs-lookup"><span data-stu-id="bc594-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="bc594-117">Mot de passe du service d’écoute (saisi lors de l’installation de l’écouteur et de chaque agent)</span><span class="sxs-lookup"><span data-stu-id="bc594-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="bc594-118">Configuration du certificat SSL du site web</span><span class="sxs-lookup"><span data-stu-id="bc594-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="bc594-119">Mise à niveau automatique</span><span class="sxs-lookup"><span data-stu-id="bc594-119">Automated upgrade</span></span>

<span data-ttu-id="bc594-120">Le script collecte les informations concernant votre certificat actuel ainsi que le mot de passe de l’écouteur et désinstalle l’ancienne version du produit avant d’installer la nouvelle.</span><span class="sxs-lookup"><span data-stu-id="bc594-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="bc594-121">L’instance Redis installée sur le serveur n’en est pas affectée, de sorte que toutes les données stockées dans la mémoire cache sont conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bc594-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="bc594-122">Placez les fichiers MSI pour la nouvelle version de l’agent, le port d’écoute et le site Web ainsi que le script de mise à jour-StatsMan.ps1 dans un seul dossier sur l’ordinateur du port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="bc594-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="bc594-123">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc594-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="bc594-124">Mettez à niveau l’écouteur :</span><span class="sxs-lookup"><span data-stu-id="bc594-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="bc594-125">Le mot de passe du service Gestionnaire de statistiques s’affichera en texte clair sur la ligne de commande, comme il est passé pour le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="bc594-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="bc594-126">Par conséquent, assurez-vous de protéger convenablement votre moniteur.</span><span class="sxs-lookup"><span data-stu-id="bc594-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="bc594-127">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="bc594-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="bc594-128">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="bc594-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="bc594-129">Si le service d’écoute est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bc594-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="bc594-130">Autoriser l’application à fermer (le Gestionnaire de statistiques de port d’écoute service va s’arrêter).</span><span class="sxs-lookup"><span data-stu-id="bc594-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="bc594-131">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="bc594-131">Continue the install process.</span></span> <span data-ttu-id="bc594-132">Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés.</span><span class="sxs-lookup"><span data-stu-id="bc594-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="bc594-133">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bc594-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="bc594-134">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc594-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="bc594-135">Mettez à niveau le site web :</span><span class="sxs-lookup"><span data-stu-id="bc594-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="bc594-136">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="bc594-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="bc594-137">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="bc594-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="bc594-138">Si le service d’agent est en cours d’exécution, vous serez invité à fermer l’application avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bc594-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="bc594-139">Autorisez la fermeture de l’application (le service d’agent StatsMan sera arrêté).</span><span class="sxs-lookup"><span data-stu-id="bc594-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="bc594-140">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="bc594-140">Continue the install process.</span></span> <span data-ttu-id="bc594-141">Normalement, le mot de passe du service et l’empreinte numérique du certificat sont déjà renseignés.</span><span class="sxs-lookup"><span data-stu-id="bc594-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="bc594-142">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bc594-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="bc594-143">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc594-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="bc594-144">Mettez à niveau l’agent :</span><span class="sxs-lookup"><span data-stu-id="bc594-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="bc594-145">Lors de l’exécution du script, une invite vous demande si vous souhaitez désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="bc594-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="bc594-146">Répondez Oui.</span><span class="sxs-lookup"><span data-stu-id="bc594-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="bc594-147">Continuez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="bc594-147">Continue the install process.</span></span> <span data-ttu-id="bc594-148">Normalement, le port du site web est déjà renseigné.</span><span class="sxs-lookup"><span data-stu-id="bc594-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="bc594-149">Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="bc594-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="bc594-150">Vérifiez que le site web fonctionne correctement à l’aide du navigateur.</span><span class="sxs-lookup"><span data-stu-id="bc594-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bc594-151">La mise à niveau de l’agent peut être effectuée avec le commutateur -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="bc594-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="bc594-152">Ainsi, le processus d’installation/désinstallation s’exécute silencieusement, ce qui permet à des outils tels que PSExec d’exécuter à distance la mise à niveau sur un grand nombre de serveurs.</span><span class="sxs-lookup"><span data-stu-id="bc594-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="bc594-153">Mise à niveau manuelle</span><span class="sxs-lookup"><span data-stu-id="bc594-153">Manual upgrade</span></span>

<span data-ttu-id="bc594-154">Si, pour une raison ou pour une autre, la mise à niveau automatique échoue, vous pouvez toujours effectuer une mise à niveau manuelle en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="bc594-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="bc594-155">	Sur l’ordinateur d’écoute, désinstallez l’écouteur, le site web et l’agent (s’il était installée sur ce serveur) à l’aide du panneau de commande Programmes et fonctionnalités.  </span><span class="sxs-lookup"><span data-stu-id="bc594-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="bc594-156"> Ne désinstallez pas Redis, afin que les données dans la mémoire cache soient conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bc594-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="bc594-p118">	Installez les nouvelles versions de ces composants, y compris les valeurs que vous avez enregistrées précédemment lorsqu’elles vous sont demandées. Pour plus d’informations sur l’installation des composants, consultez la rubrique [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="bc594-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="bc594-159">Pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="bc594-159">For more information</span></span>
<span data-ttu-id="bc594-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="bc594-160"></span></span>

<span data-ttu-id="bc594-161">Pour plus d’informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="bc594-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="bc594-162">Planifier Business Server pour le Gestionnaire de statistiques de Skype</span><span class="sxs-lookup"><span data-stu-id="bc594-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="bc594-163">Déployer des statistiques responsable Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="bc594-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="bc594-164">Résoudre les statistiques du gestionnaire pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="bc594-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
