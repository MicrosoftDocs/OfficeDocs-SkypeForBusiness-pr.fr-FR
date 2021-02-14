---
title: Mise à niveau du Gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Résumé : Lisez cette rubrique pour découvrir comment mettre à niveau le Gestionnaire de statistiques pour Skype Entreprise Server.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821764"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="5d347-103">Mise à niveau du Gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5d347-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="5d347-104">**Résumé :** Lisez cette rubrique pour découvrir comment mettre à niveau le Gestionnaire de statistiques pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5d347-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="5d347-105">Cette rubrique décrit comment mettre à niveau une installation existante du Gestionnaire de statistiques pour Skype Entreprise Server, un outil puissant qui vous permet d’afficher les données d’état et de performances de Skype Entreprise Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="5d347-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="5d347-106">Vous pouvez sonder les données de performances sur des centaines de serveurs toutes les quelques secondes et afficher les résultats instantanément sur le site web du Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="5d347-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="5d347-107">Pour plus d’informations sur le Gestionnaire de statistiques et les nouvelles fonctionnalités de la version 2.0, voir [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy Statistics Manager for Skype for Business [Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="5d347-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="5d347-108">Il existe deux méthodes pour la mise à niveau :</span><span class="sxs-lookup"><span data-stu-id="5d347-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="5d347-109">**Mise à niveau automatisée.**</span><span class="sxs-lookup"><span data-stu-id="5d347-109">**Automated upgrade.**</span></span> <span data-ttu-id="5d347-110">Cette méthode utilise un script automatisé.</span><span class="sxs-lookup"><span data-stu-id="5d347-110">This method uses an automated script.</span></span> <span data-ttu-id="5d347-111">Il s’agit de la méthode la plus simple et elle doit s’appliquer à tous les scénarios de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5d347-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="5d347-112">**Mise à niveau manuelle.**</span><span class="sxs-lookup"><span data-stu-id="5d347-112">**Manual upgrade.**</span></span> <span data-ttu-id="5d347-113">Cette méthode est fournie en tant que plan de sauvegarde dans les cas inhabituels d’échec de la mise à niveau automatisée.</span><span class="sxs-lookup"><span data-stu-id="5d347-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="5d347-114">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="5d347-114">Prerequisites</span></span>

<span data-ttu-id="5d347-115">Avant de mettre à niveau, assurez-vous que vous avez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d347-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="5d347-116">Empreinte numérique du certificat d’écoute actif</span><span class="sxs-lookup"><span data-stu-id="5d347-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="5d347-117">Mot de passe du service d’écoute (entré lors de l’installation de l’écoute et de chaque agent)</span><span class="sxs-lookup"><span data-stu-id="5d347-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="5d347-118">Configuration du certificat SSL pour le site web</span><span class="sxs-lookup"><span data-stu-id="5d347-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="5d347-119">Mise à niveau automatisée</span><span class="sxs-lookup"><span data-stu-id="5d347-119">Automated upgrade</span></span>

<span data-ttu-id="5d347-120">Le script collecte les informations de certificat et le mot de passe de l’écoute actuels, désinstalle l’ancienne version du produit, puis installe la nouvelle version du produit.</span><span class="sxs-lookup"><span data-stu-id="5d347-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="5d347-121">L’instance Redis installée sur le serveur ne sera pas touché, de sorte que les données stockées dans le cache seront conservées pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5d347-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="5d347-122">Placez les fichiers MSI pour la nouvelle version de l’agent, de l’écoute et du site web avec le script Update-StatsMan.ps1 dans un dossier unique sur l’ordinateur d’écoute.</span><span class="sxs-lookup"><span data-stu-id="5d347-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="5d347-123">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d347-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="5d347-124">Mettre à niveau le composant d’écoute :</span><span class="sxs-lookup"><span data-stu-id="5d347-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="5d347-125">Le mot de passe du service Gestionnaire de statistiques s’affiche en texte clair sur la ligne de commande lors de son passage au programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="5d347-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="5d347-126">Assurez-vous de protéger votre moniteur selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5d347-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="5d347-127">Lors de l’exécution du script, vous devez être invité à désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="5d347-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="5d347-128">Réponse Oui.</span><span class="sxs-lookup"><span data-stu-id="5d347-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="5d347-129">Si le service d’écoute est en cours d’exécution, vous êtes invité à fermer l’application avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="5d347-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="5d347-130">Autorisez la fermeture de l’application (le service d’écoute du Gestionnaire de statistiques sera arrêté).</span><span class="sxs-lookup"><span data-stu-id="5d347-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="5d347-131">Poursuivez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5d347-131">Continue the install process.</span></span> <span data-ttu-id="5d347-132">Notez que le mot de passe de service et l’empreinte numérique du certificat sont pré-remplis.</span><span class="sxs-lookup"><span data-stu-id="5d347-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="5d347-133">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="5d347-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="5d347-134">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d347-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="5d347-135">Mettre à niveau le composant Site web :</span><span class="sxs-lookup"><span data-stu-id="5d347-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="5d347-136">Lors de l’exécution du script, vous devez être invité à désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="5d347-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="5d347-137">Réponse Oui.</span><span class="sxs-lookup"><span data-stu-id="5d347-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="5d347-138">Si le service Agent est en cours d’exécution, vous êtes invité à fermer l’application avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="5d347-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="5d347-139">Autorisez la fermeture de l’application (le service d’agent StatsMan est arrêté).</span><span class="sxs-lookup"><span data-stu-id="5d347-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="5d347-140">Poursuivez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5d347-140">Continue the install process.</span></span> <span data-ttu-id="5d347-141">Notez que le mot de passe de service et l’empreinte numérique du certificat sont pré-remplis.</span><span class="sxs-lookup"><span data-stu-id="5d347-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="5d347-142">Si ce n’est pas le cas, ajoutez les valeurs que vous avez enregistrées avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="5d347-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="5d347-143">Ouvrez une fenêtre d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d347-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="5d347-144">Mettre à niveau le composant Agent :</span><span class="sxs-lookup"><span data-stu-id="5d347-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="5d347-145">Lors de l’exécution du script, vous devez être invité à désinstaller l’ancienne version du produit.</span><span class="sxs-lookup"><span data-stu-id="5d347-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="5d347-146">Réponse Oui.</span><span class="sxs-lookup"><span data-stu-id="5d347-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="5d347-147">Poursuivez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5d347-147">Continue the install process.</span></span> <span data-ttu-id="5d347-148">Notez que le port du site web est pré-rempli.</span><span class="sxs-lookup"><span data-stu-id="5d347-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="5d347-149">Si ce n’est pas le cas, ajoutez la valeur que vous avez enregistrée avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="5d347-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="5d347-150">Vérifiez que le site web fonctionne comme prévu à l’aide du navigateur.</span><span class="sxs-lookup"><span data-stu-id="5d347-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d347-151">La mise à niveau de l’agent peut être utilisée avec le commutateur -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="5d347-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="5d347-152">Cela permettra au processus de désinstallation/installation de s’exécuter en mode silencieux, ce qui permettra aux outils tels que PSExec d’exécuter la mise à niveau à distance sur un grand nombre de serveurs.</span><span class="sxs-lookup"><span data-stu-id="5d347-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="5d347-153">Mise à niveau manuelle</span><span class="sxs-lookup"><span data-stu-id="5d347-153">Manual upgrade</span></span>

<span data-ttu-id="5d347-154">Si, pour une raison quelconque, la mise à niveau automatisée échoue, vous pouvez toujours effectuer une mise à niveau manuelle comme suit :</span><span class="sxs-lookup"><span data-stu-id="5d347-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="5d347-155">Sur l’ordinateur d’écoute, désinstallez l’écoute, le site web et l’agent (s’il a été installé sur ce serveur) via le panneau de contrôle Programmes et fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="5d347-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5d347-156">Maintenez Redis installé afin que les données dans le cache soient ensuite conservées tout au long du processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5d347-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="5d347-157">Installez les nouvelles versions des composants, y compris les valeurs que vous avez enregistrées ci-dessus lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="5d347-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="5d347-158">Pour plus d’informations sur l’installation des composants, voir [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="5d347-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="5d347-159">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="5d347-159">For more information</span></span>
<span data-ttu-id="5d347-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="5d347-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="5d347-161">Pour plus d'informations, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="5d347-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="5d347-162">Planifier le gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5d347-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="5d347-163">Déploiement du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5d347-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="5d347-164">Dépannage du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5d347-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
