---
title: Déployer du gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Résumé : consultez cette rubrique pour connaître la procédure de déploiement du gestionnaire de statistiques de Skype Entreprise Serveur.'
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803964"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="17263-103">Déployer le Gestionnaire de Statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="17263-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="17263-104">**Résumé:** consultez cette rubrique pour connaître la procédure de déploiement du gestionnaire de statistiques de Skype Entreprise Server .</span><span class="sxs-lookup"><span data-stu-id="17263-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="17263-105">Le Gestionnaire de statistiques pour Skype Entreprise Server est un outil puissant qui permet de consulter Skype pour l’état et les performances des données entreprise Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="17263-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="17263-106">Vous pouvez interroger les données de performances sur des centaines de serveurs à des intervalles de quelques secondes et afficher les résultats instantanément sur le site Web de Gestionnaire de Statistiques.</span><span class="sxs-lookup"><span data-stu-id="17263-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="17263-107">Avant de procéder à l’installation du Gestionnaire de Statistiques, veillez à vous familiariser avec la configuration logicielle, matérielle et les spécifications réseau requises.</span><span class="sxs-lookup"><span data-stu-id="17263-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="17263-108">Pour plus d’informations,[Planifier le Gestionnaire de Statistiques pour Skype Entreprise Server](plan.md).</span><span class="sxs-lookup"><span data-stu-id="17263-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="17263-109">Si vous procédez à la mise à niveau à partir d’une version précédente de Gestionnaire des Statistiques, reportez-vous à la rubrique[ Mettre à niveau le Gestionnaire de Statistiques dans Skype Entreprise Server Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="17263-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="17263-110">Le site Web du gestionnaire de statistiques a été testé et fonctionne correctement sur Internet Explorer 11+, Microsoft Edge 20.10240+ et Chrome 46+ (version Evergreen actuelle).</span><span class="sxs-lookup"><span data-stu-id="17263-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="17263-111">Vous trouverez le Gestionnaire de statistiques téléchargeable en [ https://aka.ms/StatsManDownload ](https://aka.ms/StatsManDownload).</span><span class="sxs-lookup"><span data-stu-id="17263-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="17263-112">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="17263-113">Déploiement du gestionnaire de statistiques</span><span class="sxs-lookup"><span data-stu-id="17263-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="17263-114">Dépannage de votre déploiement</span><span class="sxs-lookup"><span data-stu-id="17263-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="17263-115">Création d’un certificat auto-signé</span><span class="sxs-lookup"><span data-stu-id="17263-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="17263-116">Déploiement du gestionnaire de statistiques</span><span class="sxs-lookup"><span data-stu-id="17263-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="17263-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="17263-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="17263-118">Pour déployer le Gestionnaire de Statistiques, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17263-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="17263-119">Préparez l’ordinateur hôte de l’écouteur en installant le système de mise en cache en mémoire Redis et vérifiez que les certificats appropriés sont installés.</span><span class="sxs-lookup"><span data-stu-id="17263-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="17263-120">Installez le service d’écoute sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="17263-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="17263-121">Installez le site Web sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="17263-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="17263-122">Installez un agent sur chaque ordinateur Skype Entreprise Server que vous souhaitez surveiller.</span><span class="sxs-lookup"><span data-stu-id="17263-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="17263-123">Importez la topologie des serveurs que vous surveillez.</span><span class="sxs-lookup"><span data-stu-id="17263-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="17263-124">Le système Redis, le service d’écoute et le site Web doivent être installés sur le même ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="17263-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="17263-125">N’oubliez pas de que l’ordinateur hôte n’a pas Skype Entreprise Server installé.</span><span class="sxs-lookup"><span data-stu-id="17263-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="17263-126">Préparation de l’ordinateur hôte</span><span class="sxs-lookup"><span data-stu-id="17263-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="17263-127">Pour préparer l’ordinateur hôte, vous devrez installer le système de mise en cache en mémoire Redis et vous assurer qu’un certificat valide est installé sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="17263-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="17263-128">Microsoft recommande d’installer la dernière version stable de Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="17263-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="17263-129">Le Gestionnaire de Statistiques version 2.0 a été testé avec Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="17263-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="17263-130">Télécharger Redis à partir du site suivant : [ https://github.com/MSOpenTech/redis ](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="17263-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="17263-131">Les programmes d’installation non signés peuvent être téléchargés à partir de [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="17263-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="17263-132">Si nécessaire, les fichiers binaires signés sont accessibles via les responsables de package populaires : [Nuget](https://www.nuget.org/packages/Redis-64/) et [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="17263-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="17263-133">Exécutez le fichier .msi fourni et suivez les invites.</span><span class="sxs-lookup"><span data-stu-id="17263-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="17263-134">Ne sélectionnez pas la case à cocher pour ajouter une règle de pare-feu.</span><span class="sxs-lookup"><span data-stu-id="17263-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="17263-135">Le service d’écoute requiert un certificat.</span><span class="sxs-lookup"><span data-stu-id="17263-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="17263-136">Microsoft recommande vivement que votre certificat signé provienne d’une autorité de certification approuvée.</span><span class="sxs-lookup"><span data-stu-id="17263-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="17263-137">Si vous souhaitez utiliser un certificat auto-signé, par exemple à des fins de test au sein d’un laboratoire, reportez-vous à l’article [Création d’un certificat auto-signé](deploy.md#BKMK_SelfCert).</span><span class="sxs-lookup"><span data-stu-id="17263-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="17263-p106">Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne). Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="17263-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="17263-140">Installation du service de l’écouteur</span><span class="sxs-lookup"><span data-stu-id="17263-140">Install the Listener service</span></span>

<span data-ttu-id="17263-141">Pour installer le service d’écoute sur l’ordinateur hôte, exécutez le fichier StatsManPerfAgentListener.msi et spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="17263-142">Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**. </span><span class="sxs-lookup"><span data-stu-id="17263-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="17263-143">Dans la page suivante, spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="17263-144">**Mot de passe du service :** il s’agit du mot de passe que les agents distants utiliseront pour s’authentifier auprès du service d’écoute.</span><span class="sxs-lookup"><span data-stu-id="17263-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="17263-145">**Port du service :** il s’agit du numéro de port HTTPS que l’écouteur utilisera pour communiquer avec les agents.</span><span class="sxs-lookup"><span data-stu-id="17263-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="17263-146">Lors de l’installation, ce port pourra traverser le pare-feu local, une ACL d’URL sera créée et un certificat SSL sera lié à ce port.</span><span class="sxs-lookup"><span data-stu-id="17263-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="17263-147">La valeur par défaut est 8443.</span><span class="sxs-lookup"><span data-stu-id="17263-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="17263-148">**Empreinte de certificat :** il s’agit de l’empreinte de certificat que l’écouteur utilisera pour chiffrer le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="17263-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="17263-149">Le service réseau doit disposer d’un accès en lecture à la clé privée.</span><span class="sxs-lookup"><span data-stu-id="17263-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="17263-150">Cliquez sur le bouton **Sélectionner...** pour choisir l’empreinte.</span><span class="sxs-lookup"><span data-stu-id="17263-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="17263-151">Vous pouvez trouver l’empreinte de certificat à l’aide du gestionnaire de certificats ou de la commande PowerShell :</span><span class="sxs-lookup"><span data-stu-id="17263-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="17263-152">\*\*Répertoire d’installation: \*\* il s’agit du répertoire dans lequel les fichiers binaires seront installés.</span><span class="sxs-lookup"><span data-stu-id="17263-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="17263-153">Vous pouvez modifier le répertoire par défaut à l’aide du bouton **Parcourir...**.</span><span class="sxs-lookup"><span data-stu-id="17263-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="17263-154">**Répertoire AppData :** il s’agit du répertoire dans lequel le dossier Journaux et d’autres données seront stockés.</span><span class="sxs-lookup"><span data-stu-id="17263-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="17263-155">Vous pouvez modifier le répertoire par défaut.</span><span class="sxs-lookup"><span data-stu-id="17263-155">You may change it from the default.</span></span> <span data-ttu-id="17263-156">Il ne sera pas supprimé lors de la désinstallation.</span><span class="sxs-lookup"><span data-stu-id="17263-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="17263-157">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="17263-157">Click **Install**.</span></span>
    
<span data-ttu-id="17263-158">Pour valider l’installation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17263-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="17263-159">Ouvrez un navigateur et accédez à https://localhost:\<service-port\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="17263-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="17263-160">Par défaut, le port du service est 8443 (sauf si vous spécifiez un autre port).</span><span class="sxs-lookup"><span data-stu-id="17263-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="17263-161">Pour vérifier l’installation correcte de l’écouteur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17263-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="17263-162">Si la page de vérification d’intégrité s’affiche, l’écouteur a été correctement installé.</span><span class="sxs-lookup"><span data-stu-id="17263-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="17263-163">Si KnownServerCount est supérieur ou défini à 1, la connexion à ReDim est établie.</span><span class="sxs-lookup"><span data-stu-id="17263-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="17263-164">Après l’installation d’au moins un agent, patientez quelques minutes et vérifiez que le compteur ValuesWritten augmente.</span><span class="sxs-lookup"><span data-stu-id="17263-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="17263-165">Installation du site Web</span><span class="sxs-lookup"><span data-stu-id="17263-165">Install the Website</span></span>

<span data-ttu-id="17263-166">Installer le site Web de l’ordinateur hôte en exécutant le StatsManWebSite.msi (inclus avec [Skype Entreprise Server, en temps réel statistiques Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) et en spécifiant des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="17263-167">Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**. </span><span class="sxs-lookup"><span data-stu-id="17263-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="17263-168">Dans la page suivante, spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="17263-169">**Port du service :** il s’agit du numéro de port que le site Web écoutera.</span><span class="sxs-lookup"><span data-stu-id="17263-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="17263-170">Vous pouvez le modifier ultérieurement à l’aide de la liaison du gestionnaire IIS.</span><span class="sxs-lookup"><span data-stu-id="17263-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="17263-171">Lors de l’installation, ce port pourra traverser le pare-feu local.</span><span class="sxs-lookup"><span data-stu-id="17263-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="17263-172">**Répertoire d’installation :** Il s’agit du répertoire dans lequel les fichiers binaires seront installés.</span><span class="sxs-lookup"><span data-stu-id="17263-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="17263-173">Vous pouvez modifier le répertoire par défaut à l’aide du bouton **Parcourir...**.</span><span class="sxs-lookup"><span data-stu-id="17263-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="17263-174">**Répertoire AppData :** il s’agit du répertoire dans lequel le dossier Journaux et d’autres données seront stockés.</span><span class="sxs-lookup"><span data-stu-id="17263-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="17263-175">Vous pouvez modifier le répertoire par défaut.</span><span class="sxs-lookup"><span data-stu-id="17263-175">You may change it from the default.</span></span> <span data-ttu-id="17263-176">Il ne sera pas supprimé lors de la désinstallation.</span><span class="sxs-lookup"><span data-stu-id="17263-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="17263-177">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="17263-177">Click **Install**.</span></span>
    
<span data-ttu-id="17263-178">Pour afficher le site Web, ouvrez un navigateur et accédez à:http://localhost,webport\>/.</span><span class="sxs-lookup"><span data-stu-id="17263-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="17263-179">Pour afficher uniquement les informations d’intégrité, ouvrez un navigateur et accédez à :http://localhost:\<webport\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="17263-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="17263-180">Par défaut, le numéro de port Web est 8080.</span><span class="sxs-lookup"><span data-stu-id="17263-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="17263-181">Vous pouvez modifier la liaison de port du site Web à l’aide du gestionnaire IIS.</span><span class="sxs-lookup"><span data-stu-id="17263-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="17263-182">Le programme d’installation Web ajoute un groupe de sécurité local appelé StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="17263-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="17263-183">Vous pouvez ajouter des comptes à ce groupe de sécurité pour accorder l’accès au site Web.</span><span class="sxs-lookup"><span data-stu-id="17263-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="17263-184">Installation des agents</span><span class="sxs-lookup"><span data-stu-id="17263-184">Install the Agents</span></span>

<span data-ttu-id="17263-185">Pour installer un agent sur chaque Skype Entreprise Server que vous souhaitez surveiller, exécutez le fichier StatsManPerfAgent.msi et spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="17263-186">Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**. </span><span class="sxs-lookup"><span data-stu-id="17263-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="17263-187">Dans la page suivante, spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="17263-188">**Mot de passe du service :** il s’agit du mot de passe que l’agent distant utilisera pour s’authentifier auprès du service d’écoute.</span><span class="sxs-lookup"><span data-stu-id="17263-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="17263-189">**URI du service :** il s’agit de l’URI où réside l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="17263-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="17263-190">Elle doit utiliser le formathttps://name:port.</span><span class="sxs-lookup"><span data-stu-id="17263-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="17263-191">Vous pouvez utiliser un nom NETBIOS ou un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="17263-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="17263-192">Vous pouvez utiliser le nom qui est également spécifié comme **Objet** ou **Autres noms de l’objet** du certificat sur le service d’écoute, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="17263-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="17263-193">**Empreinte du service :** il s’agit de l’empreinte du certificat SSL utilisé par l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="17263-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="17263-194">L’agent utilisera cette empreinte pour s’authentifier auprès de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="17263-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="17263-195">(Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.)</span><span class="sxs-lookup"><span data-stu-id="17263-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="17263-196">\*\*Répertoire d’installation: \*\* il s’agit du répertoire dans lequel les fichiers binaires seront installés.</span><span class="sxs-lookup"><span data-stu-id="17263-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="17263-197">Vous pouvez modifier le répertoire par défaut à l’aide du bouton **Parcourir...**.</span><span class="sxs-lookup"><span data-stu-id="17263-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="17263-198">**Répertoire AppData :** Il s’agit du répertoire dans lequel le dossier Journaux et le fichier password.txt chiffré seront stockés.</span><span class="sxs-lookup"><span data-stu-id="17263-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="17263-199">Vous pouvez le modifier à partir du répertoire par défaut.</span><span class="sxs-lookup"><span data-stu-id="17263-199">You may thanks change it from the default.</span></span> <span data-ttu-id="17263-200">Il ne sera pas supprimé lors de la désinstallation.</span><span class="sxs-lookup"><span data-stu-id="17263-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="17263-201">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="17263-201">Click **Install**.</span></span>
    
<span data-ttu-id="17263-p121">Si vous installez un agent sur différents ordinateurs, vous souhaitez peut-être le faire en mode sans assistance. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="17263-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="17263-204">Importation de la topologie</span><span class="sxs-lookup"><span data-stu-id="17263-204">Import the topology</span></span>
<span data-ttu-id="17263-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="17263-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="17263-206">Lorsque le Gestionnaire de Statistiques est installé et en cours d’exécution, vous devez importer la topologie Skype Entreprise Server de manière à ce que le Gestionnaire de Statistiques puisse connaître le site, le pool et le rôle de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="17263-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="17263-207">Pour importer votre topologie Skype Entreprise Server, utilisez l’applet de commande[Obtenir-CSPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) pour récupérer les informations relatives à chaque pool utilisé dans votre organisation, puis importez-les dans le Gestionnaire de Statistiques.</span><span class="sxs-lookup"><span data-stu-id="17263-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="17263-208">Pour importer a topologie de Skype Entreprise Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17263-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="17263-209">Sur un hôte qui a Skype Entreprise Server pour les applets de commande PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17263-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="17263-210">a.</span><span class="sxs-lookup"><span data-stu-id="17263-210">a.</span></span> <span data-ttu-id="17263-211">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="17263-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="17263-212">b.</span><span class="sxs-lookup"><span data-stu-id="17263-212">b.</span></span> <span data-ttu-id="17263-213">Copiez le fichier «mypoolinfo.xml» sur le serveur exécutant l’Écouteur.</span><span class="sxs-lookup"><span data-stu-id="17263-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="17263-214">Sur l’hôte exécutant l’Écouteur :</span><span class="sxs-lookup"><span data-stu-id="17263-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="17263-215">a.</span><span class="sxs-lookup"><span data-stu-id="17263-215">a.</span></span> <span data-ttu-id="17263-216">Exécutez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17263-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="17263-217">b.</span><span class="sxs-lookup"><span data-stu-id="17263-217">b.</span></span> <span data-ttu-id="17263-218">Accédez au répertoire dans lequel l’écouteur est installé.</span><span class="sxs-lookup"><span data-stu-id="17263-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="17263-219">Valeur par défaut :</span><span class="sxs-lookup"><span data-stu-id="17263-219">The default is:</span></span> 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="17263-220">Pour confirmer les serveurs qui sont ajoutés et mis à jour, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="17263-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="17263-221">La commande suivante permet d’afficher toutes les options :</span><span class="sxs-lookup"><span data-stu-id="17263-221">The following command enables you to view all options:</span></span>
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="17263-222">Pour consulter les informations du serveur importé, exécutez le script suivant :</span><span class="sxs-lookup"><span data-stu-id="17263-222">To see your currently imported server information, run the following script:</span></span> 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="17263-223">Si vous souhaitez surveiller des serveurs qui ne font pas partie de votre topologie Skype Entreprise Server, par exemple un serveur Exchange, vous pouvez effectuer une importation de serveur unique vers l’hôte qui exécute l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="17263-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="17263-224">Pour effectuer une importation de serveur , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17263-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="17263-225">Accédez au répertoire dans lequel l’écouteur est installé.</span><span class="sxs-lookup"><span data-stu-id="17263-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="17263-226">Valeur par défaut :</span><span class="sxs-lookup"><span data-stu-id="17263-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="17263-227">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="17263-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="17263-228">Dépannage de votre déploiement</span><span class="sxs-lookup"><span data-stu-id="17263-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="17263-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="17263-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="17263-230">Si un agent ne démarre pas, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="17263-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="17263-231">L’agent est-il enregistré auprès du Gestionnaire de Statistiques?</span><span class="sxs-lookup"><span data-stu-id="17263-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="17263-p129">	Assurez-vous que vous avez suivi les instructions pour importer la topologie. Consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="17263-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="17263-234">Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, nœuds dans un cluster SQL AlwaysOn), vous devrez ajouter l’agent manuellement en suivant les instructions de la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="17263-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="17263-235">L’agent peut-il contacter l’écouteur ?</span><span class="sxs-lookup"><span data-stu-id="17263-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="17263-236">Vérifiez que le service d’écoute est exécuté.</span><span class="sxs-lookup"><span data-stu-id="17263-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="17263-237">Si ce n’est pas le cas, vérifiez que le système Redis est en cours d’exécution, puis essayez de redémarrer l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="17263-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="17263-238">Assurez-vous que le port est ouvert sur le service d’écoute et que l’ordinateur de l’agent peut communiquer avec le port.</span><span class="sxs-lookup"><span data-stu-id="17263-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="17263-239">Pour vérifier que le Gestionnaire de Statistiques collecte des données, vous pouvez consulter le fichier CSV comme suit. </span><span class="sxs-lookup"><span data-stu-id="17263-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="17263-240">La commande suivante récupère les noms de stockage de compteur :</span><span class="sxs-lookup"><span data-stu-id="17263-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="17263-241">La commande suivante récupère les valeurs des compteurs spécifiés :</span><span class="sxs-lookup"><span data-stu-id="17263-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="17263-242">Pour plus d’informations sur l’ensemble des événements qui peuvent figurer dans le journal d’événements de l’application, reportez-vous à la rubrique [Résolution de Gestionnaire de Statistiques dans Skype Entreprise Server](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="17263-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="17263-243">Création d’un certificat auto-signé</span><span class="sxs-lookup"><span data-stu-id="17263-243">Create a self-signed certificate</span></span>
<span data-ttu-id="17263-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="17263-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="17263-245">Microsoft recommande vivement d’utiliser un certificat signé par une autorité de certification approuvée.</span><span class="sxs-lookup"><span data-stu-id="17263-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="17263-246">Toutefois, si vous souhaitez utiliser un certificat auto-signé à des fins de test, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17263-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="17263-247">Connectez-vous à une console PowerShell en tant qu’administrateur, et tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17263-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="17263-248">Type `certlm.msc`.</span><span class="sxs-lookup"><span data-stu-id="17263-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="17263-249">Le Gestionnaire de Certificat s’ouvrira pour l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="17263-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="17263-250">Accédez à **Personnel** et ouvrez**Certificats**.</span><span class="sxs-lookup"><span data-stu-id="17263-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="17263-251">Cliquez à l’aide du bouton droit de la souris sur **StatsManListener-\>Toutes les Tâches-\>Gérer les clés privées Keys…**</span><span class="sxs-lookup"><span data-stu-id="17263-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="17263-252">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="17263-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="17263-253">Dans la zone **Entrer les noms d’objets à sélectionner**, tapez Service réseau.</span><span class="sxs-lookup"><span data-stu-id="17263-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="17263-254">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17263-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="17263-p132">Sous **Contrôle total**, désactivez la case à cocher **Autoriser**. Seul un accès en lecture est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="17263-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="17263-257">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17263-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="17263-258">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="17263-258">For more information</span></span>
<span data-ttu-id="17263-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="17263-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="17263-260">Pour plus d'informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="17263-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="17263-261">Planifier le gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="17263-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="17263-262">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="17263-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="17263-263">[Dépannage du gestionnaire de statistiques pour Skype Entreprise Server](troubleshoot.md)ß</span><span class="sxs-lookup"><span data-stu-id="17263-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
