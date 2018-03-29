---
title: Documentation sur les outils du Kit de ressources techniques Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Cette rubrique décrit les outils disponibles dans le Skype pour le Kit de ressources de Business Server 2015, y compris l’objectif de chaque outil et des exemples de son utilisation. Le Skype pour le Kit de ressources de Business Server 2015 permet de faciliter les tâches de routine pour les administrateurs qui déploient et gérer Skype pour Business Server 2015. Par exemple, l’outil Web Conf données permet de contrôler facilement les données de téléchargement par les utilisateurs lors d’une réunion en ligne. L’outil de SEFAUtil peut être utilisé pour définir un appel de délégué de transfert et de réponse pour les utilisateurs. Nous encourageons les administrateurs informatiques à utiliser ces outils pour gérer plus efficacement les Skype pour Business Server 2015.
ms.openlocfilehash: 8367400ea7730eabbd2686c3bb2b7c16cdf9a1f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="6f369-107">Documentation sur les outils du Kit de ressources techniques Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f369-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>
 
<span data-ttu-id="6f369-108">Cette rubrique décrit les outils disponibles dans le Skype pour le Kit de ressources de Business Server 2015, y compris l’objectif de chaque outil et des exemples de son utilisation.</span><span class="sxs-lookup"><span data-stu-id="6f369-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="6f369-109">Le Skype pour le Kit de ressources de Business Server 2015 permet de faciliter les tâches de routine pour les administrateurs qui déploient et gérer Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="6f369-110">Par exemple, l’outil **Web Conf Data** permet de contrôler aisément les données téléchargées par les utilisateurs au cours d’une réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="6f369-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="6f369-111">L’outil **SEFAUtil** permet de définir le transfert des appels de délégué et le répondeur automatique pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f369-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="6f369-112">Nous encourageons les administrateurs informatiques à utiliser ces outils pour gérer plus efficacement les Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>
  
## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="6f369-113">Installation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="6f369-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="6f369-114">Pour installer le Skype pour le Kit de ressources de Business Server 2015, téléchargez [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="6f369-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>
  
<span data-ttu-id="6f369-p103">Exécutez **OCSResKit.msi ** pour effectuer une installation simple. Le fichier .msi installe tous les outils dans le chemin d’accès suivant :  **%Program Files%\Skype for Business Server 2015\ResKit**. Les outils exécutables autonomes se trouvent dans ce dossier. Les outils comportant également des fichiers de prise en charge se trouvent dans leur propre sous-dossier.</span><span class="sxs-lookup"><span data-stu-id="6f369-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>
  
## <a name="supported-environments"></a><span data-ttu-id="6f369-119">Environnements pris en charge</span><span class="sxs-lookup"><span data-stu-id="6f369-119">Supported Environments</span></span>

<span data-ttu-id="6f369-120">Le Skype pour le Kit de ressources de 2015 Business Server doit être installé sur un serveur qui répond aux spécifications nécessaires à Skype pour Business Server 2015, généralement un utilisée pour exécuter Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>
  
## <a name="resource-kit-tools-overview"></a><span data-ttu-id="6f369-121">Présentation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="6f369-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="6f369-122">Voici une liste des outils fournis dans le Skype pour le Kit de ressources de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="6f369-123">Une description de chaque outil (configuration requise et exemple d’utilisation compris) est incluse dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="6f369-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>
  
- [<span data-ttu-id="6f369-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="6f369-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)
    
- [<span data-ttu-id="6f369-125">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="6f369-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)
    
- [<span data-ttu-id="6f369-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="6f369-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)
    
- [<span data-ttu-id="6f369-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="6f369-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)
    
- [<span data-ttu-id="6f369-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="6f369-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)
    
- [<span data-ttu-id="6f369-129">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="6f369-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)
    
- [<span data-ttu-id="6f369-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="6f369-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)
    
- [<span data-ttu-id="6f369-131">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="6f369-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)
    
- [<span data-ttu-id="6f369-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="6f369-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)
    
- [<span data-ttu-id="6f369-133">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="6f369-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)
    
- [<span data-ttu-id="6f369-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="6f369-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)
    
- [<span data-ttu-id="6f369-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6f369-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)
    
- [<span data-ttu-id="6f369-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="6f369-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)
    
- [<span data-ttu-id="6f369-137">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="6f369-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)
    
- [<span data-ttu-id="6f369-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="6f369-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)
    
## <a name="absconfig"></a><span data-ttu-id="6f369-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="6f369-139">ABSConfig</span></span>
<span data-ttu-id="6f369-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-140"></span></span>

<span data-ttu-id="6f369-141">L’outil de Configuration du Service annuaire adresse (ABSConfig) est un outil d’administration permettant aux administrateurs de personnaliser la configuration du Service de carnet d’adresses dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="6f369-142">Cet outil permet également de Skype pour Business Server 2015 aux administrateurs de restaurer les paramètres du Service de carnet d’adresses par défaut.</span><span class="sxs-lookup"><span data-stu-id="6f369-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-143">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-143">Description</span></span>

<span data-ttu-id="6f369-144">ABSConfig est une application d’interface utilisateur graphique qui permet aux administrateurs de configurer des attributs de Services de domaine Active Directory qui sont liés à un Service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="6f369-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>
  
<span data-ttu-id="6f369-145">Les principaux scénarios suivants s’appliquent à l’outil :</span><span class="sxs-lookup"><span data-stu-id="6f369-145">The primary scenarios for the tool are the following:</span></span>
  
- <span data-ttu-id="6f369-146">Pour permettre aux administrateurs de mapper des attributs dans les Services de domaine Active Directory pour les attributs pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="6f369-147">permettre aux administrateurs de spécifier un attribut des services de domaine Active Directory à inclure dans les fichiers du service de carnet d’adresses ou à exclure de ceux-ci ;</span><span class="sxs-lookup"><span data-stu-id="6f369-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>
    
- <span data-ttu-id="6f369-148">permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="6f369-148">To enable administrators to restore default Address Book Service settings.</span></span>
    
<span data-ttu-id="6f369-149">L’outil ABSConfig peut être démarré à l’aide du fichier ABSConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="6f369-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="6f369-150">L’outil s’ouvre sur l’onglet **Configurer les attributs** . Cette table contient des options pour mapper les attributs de Services de domaine Active Directory pour les champs d’attribut pour Skype pour Business Server 2015 et pour spécifier les utilisateurs à inclure ou à exclure dans les fichiers de Service carnet d’adresses en fonction des filtres d’attribut spécifique.</span><span class="sxs-lookup"><span data-stu-id="6f369-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="6f369-151">D’autres options permettent de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="6f369-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="6f369-152">L’option **Restore Defaults (Paramètres par défaut) ** permet aux administrateurs de restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="6f369-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>
  
### <a name="output"></a><span data-ttu-id="6f369-153">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-153">Output</span></span>

<span data-ttu-id="6f369-154">ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6f369-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>
  
```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="6f369-155">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-155">Purpose</span></span>

<span data-ttu-id="6f369-156">ABSConfig fournit un moyen rapide et facile à personnaliser Skype pour le Service de carnet d’adresse Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-156">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="6f369-157">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-157">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="6f369-158">Ordinateur</span><span class="sxs-lookup"><span data-stu-id="6f369-158">Computer</span></span>

<span data-ttu-id="6f369-159">ABSConfig peut être exécuté qu’à partir d’un ordinateur à un domaine qui a Skype pour Business Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="6f369-159">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="6f369-160">Dans le cas de Skype pour Business Server 2015, Enterprise Edition, cet outil peut être exécuté sur tous les serveurs Front-End dont le Service de carnet d’adresse activée lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="6f369-160">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>
  
#### <a name="network"></a><span data-ttu-id="6f369-161">Réseau</span><span class="sxs-lookup"><span data-stu-id="6f369-161">Network</span></span>

<span data-ttu-id="6f369-162">L’ordinateur doit pouvoir se connecter au pool frontal et à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="6f369-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>
  
#### <a name="software"></a><span data-ttu-id="6f369-163">Logiciels</span><span class="sxs-lookup"><span data-stu-id="6f369-163">Software</span></span>

<span data-ttu-id="6f369-164">Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :</span><span class="sxs-lookup"><span data-stu-id="6f369-164">The following software components must be installed before running the ABSConfig tool:</span></span>
  
- <span data-ttu-id="6f369-165">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f369-165">Skype for Business Server 2015</span></span>
    
#### <a name="users"></a><span data-ttu-id="6f369-166">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6f369-166">Users</span></span>

<span data-ttu-id="6f369-167">Administrateurs qui ont les autorisations nécessaires pour la mise à jour de la Skype pour le déploiement de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-167">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-168">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-168">Examples</span></span>

<span data-ttu-id="6f369-p108">ABSConfig peut être démarré en tapant **ABSConfig.exe** dans une invite de commandes. L’interface utilisateur de l’outil ABSConfig se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f369-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>
  
![Outil ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)
  
### <a name="summary"></a><span data-ttu-id="6f369-172">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-172">Summary</span></span>

<span data-ttu-id="6f369-173">L’outil ABSConfig fournit aux administrateurs un outil facile à utiliser et rapide pour personnaliser Skype pour le Service de carnet d’adresse Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>
  
## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="6f369-174">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="6f369-174">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="6f369-175"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-175"></span></span>

<span data-ttu-id="6f369-176">L’outil Bandwidth Policy Service Monitor permet aux administrateurs d’afficher la liste des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-176">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>
  
1. <span data-ttu-id="6f369-177">Tous le Skype configuré pour les services de stratégie de bande passante Business Server 2015 (authentification et Core) dans la topologie</span><span class="sxs-lookup"><span data-stu-id="6f369-177">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>
    
2. <span data-ttu-id="6f369-178">connexions effectuées par chaque service aux autres services de stratégie de bande passante et aux serveurs Edge ;</span><span class="sxs-lookup"><span data-stu-id="6f369-178">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>
    
3. <span data-ttu-id="6f369-179">liaisons configurées dans le document de configuration du réseau et utilisation de la bande passante en temps réel, telle que signalée par les services de stratégie de bande passante individuels.</span><span class="sxs-lookup"><span data-stu-id="6f369-179">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>
    
### <a name="description"></a><span data-ttu-id="6f369-180">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-180">Description</span></span>

<span data-ttu-id="6f369-p109">L’outil Bandwidth Policy Service Monitor est implémenté sous la forme d’une application à interface utilisateur graphique. Les administrateurs démarrent l’outil en exécutant PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="6f369-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>
  
<span data-ttu-id="6f369-p110">Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie. Une fois la mise à jour initiale effectuée, le volet situé à gauche de la fenêtre reçoit une liste de services regroupés selon les clusters auxquels ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="6f369-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>
  
<span data-ttu-id="6f369-p111">Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet situé à droite affiche les informations relatives à ce service particulier. Ce volet inclut également deux onglets principaux qui affichent des informations.</span><span class="sxs-lookup"><span data-stu-id="6f369-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>
  
#### <a name="machine-info-tab"></a><span data-ttu-id="6f369-187">Onglet Machine Info (Informations sur l’ordinateur)</span><span class="sxs-lookup"><span data-stu-id="6f369-187">Machine Info Tab</span></span>

<span data-ttu-id="6f369-188">L’onglet **Machine Info (Informations sur l’ordinateur)** fournit des informations sur le service de stratégie de bande passante sélectionné, ainsi que la liste et l’état des connexions effectuées par le service de stratégie de bande passante sélectionné aux autres services.</span><span class="sxs-lookup"><span data-stu-id="6f369-188">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>
  
#### <a name="topology-info-tab"></a><span data-ttu-id="6f369-189">Onglet Topology Info (Informations sur la topologie)</span><span class="sxs-lookup"><span data-stu-id="6f369-189">Topology Info Tab</span></span>

<span data-ttu-id="6f369-p112">L’onglet **Topology Info (Informations sur la topologie)** affiche la liste des liaisons configurées dans les paramètres de configuration du réseau. Pour chaque liaison, la capacité de bande passante audio et vidéo est indiquée. La bande passante actuellement utilisée est également indiquée, en Kbps et en pourcentage de la capacité. L’outil utilise des couleurs pour mettre en valeur les liaisons dont l’utilisation atteint presque la capacité maximale afin que les administrateurs puissent les isoler rapidement.</span><span class="sxs-lookup"><span data-stu-id="6f369-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6f369-194">Si l’outil Moniteur de Service de stratégie de bande passante a problème lorsqu’il se connecte à un des services de stratégie de bande passante configurées, les informations dans les **Informations de l’ordinateur** et les infos de **Topologie** ne sont pas complétées.</span><span class="sxs-lookup"><span data-stu-id="6f369-194">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="6f369-195">Il est toutefois possible que l’outil se connecte avant de perdre la connexion au service.</span><span class="sxs-lookup"><span data-stu-id="6f369-195">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="6f369-196">En pareil cas, les administrateurs peuvent voir des informations obsolètes.</span><span class="sxs-lookup"><span data-stu-id="6f369-196">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="6f369-197">Les onglets incluent des informations d’horodatage (**Last Updated (Dernière mise à jour)**) qui permettent aux administrateurs de voir la date/l’heure de la dernière mise à jour des données pour un service de stratégie de bande passante particulier.</span><span class="sxs-lookup"><span data-stu-id="6f369-197">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>
  
### <a name="output"></a><span data-ttu-id="6f369-198">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-198">Output</span></span>

<span data-ttu-id="6f369-199">Il n’y a aucune sortie de ligne de commande. La sortie du programme apparaît dans l’interface utilisateur graphique principale.</span><span class="sxs-lookup"><span data-stu-id="6f369-199">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>
  
### <a name="purpose"></a><span data-ttu-id="6f369-200">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-200">Purpose</span></span>

<span data-ttu-id="6f369-p114">L’outil Bandwidth Policy Service Monitor permet aux administrateurs de consulter l’état des services de stratégie de bande passante définis dans la topologie. Ils peuvent également voir l’utilisation de la bande passante en temps réel pour toutes les liaisons définies dans le document de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="6f369-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="6f369-203">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-203">Requirements</span></span>

<span data-ttu-id="6f369-204">L’outil Moniteur de Service de stratégie de bande passante doit être exécuté sur un ordinateur qui fait partie de la Skype pour la topologie du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6f369-204">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>
  
### <a name="summary"></a><span data-ttu-id="6f369-205">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-205">Summary</span></span>

<span data-ttu-id="6f369-206">L’outil Bandwidth Policy Service Monitor est utile pour contrôler l’état des services de stratégie de bande passante dans la topologie et connaître l’utilisation de la bande passante en temps réel pour les liaisons définies dans les paramètres de configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="6f369-206">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>
  
## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="6f369-207">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="6f369-207">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="6f369-208"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-208"></span></span>

<span data-ttu-id="6f369-p115">L’outil Bandwidth Utilization Analyzer crée des rapports sur divers affichages de la consommation de bande passante par les points de terminaison d’UC entre les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports permettent d’identifier le modèle actuel de consommation de la bande passante et de planifier la capacité de bande passante.</span><span class="sxs-lookup"><span data-stu-id="6f369-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-211">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-211">Description</span></span>

<span data-ttu-id="6f369-p116">Bandwidth Utilization Analyzer est implémenté sous la forme d’une application à interface utilisateur graphique. Cet outil génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau et constitue une aide pour planifier la capacité. Il traite également la capacité de bande passante affectée aux diverses liaisons par itération.</span><span class="sxs-lookup"><span data-stu-id="6f369-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>
  
### <a name="output"></a><span data-ttu-id="6f369-215">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-215">Output</span></span>

<span data-ttu-id="6f369-216">Bandwidth Utilization Analyzer offre une représentation graphique de la capacité de bande passante et de l’utilisation de la bande passante audio pour les liaisons de réseau étendu configurées dans le système.</span><span class="sxs-lookup"><span data-stu-id="6f369-216">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="6f369-217">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-217">Purpose</span></span>

<span data-ttu-id="6f369-218">Dans n’importe quel voix et le déploiement de vidéo, il est essentiel pour surveiller et comprendre l’évolution de l’utilisation de la bande passante du trafic multimédia sur le réseau de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6f369-218">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="6f369-219">L’outil Bandwidth Utilization Analyzer permet aux administrateurs d’y parvenir.</span><span class="sxs-lookup"><span data-stu-id="6f369-219">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="6f369-220">L’outil effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-220">This tool does the following:</span></span>
  
- <span data-ttu-id="6f369-221">génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau ;</span><span class="sxs-lookup"><span data-stu-id="6f369-221">Generates specific reports for audio utilization across the network</span></span>
    
- <span data-ttu-id="6f369-222">permet de planifier la capacité plus efficacement et de traiter la capacité de bande passante affectée aux diverses liaisons par itération.</span><span class="sxs-lookup"><span data-stu-id="6f369-222">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>
    
<span data-ttu-id="6f369-223">Bandwidth Utilization Analyzer peut générer une représentation graphique des rapports sur la capacité et l’utilisation de la bande passante, comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f369-223">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>
  
- <span data-ttu-id="6f369-224">liaisons de réseau étendu au sein du réseau d’entreprise ;</span><span class="sxs-lookup"><span data-stu-id="6f369-224">All the WAN links in the enterprise network</span></span>
    
- <span data-ttu-id="6f369-225">filtrage des liaisons de réseau étendu sélectionnées ;</span><span class="sxs-lookup"><span data-stu-id="6f369-225">Filtered by selected WAN links that have been chosen</span></span>
    
- <span data-ttu-id="6f369-226">filtrage des liaisons de réseau étendu ayant dépassé leur capacité ;</span><span class="sxs-lookup"><span data-stu-id="6f369-226">Filtered by WAN links that have exceeded link capacity</span></span>
    
- <span data-ttu-id="6f369-227">filtrage des liaisons de réseau étendu ayant sous-utilisé la bande passante approvisionnée ;</span><span class="sxs-lookup"><span data-stu-id="6f369-227">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>
    
- <span data-ttu-id="6f369-228">filtrage des liaisons de réseau étendu ayant atteint des niveaux critiques (utilisation de la bande passante supérieure à 90 % de la capacité de bande passante de la liaison de réseau étendu) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-228">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>
    
- <span data-ttu-id="6f369-229">filtrage selon le type de liaison de réseau étendu (liaisons réseau-site, liaisons inter-régions et liaisons au sein d’un site) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-229">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>
    
- <span data-ttu-id="6f369-230">filtrage par région réseau.</span><span class="sxs-lookup"><span data-stu-id="6f369-230">Filtered by network region</span></span>
    
#### <a name="applications"></a><span data-ttu-id="6f369-231">Applications</span><span class="sxs-lookup"><span data-stu-id="6f369-231">Applications</span></span>

<span data-ttu-id="6f369-232">Bandwidth Utilization Analyzer inclut les deux applications (outils) suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-232">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>
  
- <span data-ttu-id="6f369-233">**WanLinkLogCollector.exe** cet outil permet à l’utilisateur d’entrer les informations requises.</span><span class="sxs-lookup"><span data-stu-id="6f369-233">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>
    
- <span data-ttu-id="6f369-234">**BandwidthUtilizationAnalyzer.xlsm** rapport de logiciel de feuille de calcul A Microsoft Excel est automatiquement lancé par WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="6f369-234">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="6f369-235">Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6f369-235">This application allows the user to apply filters to the report as shown later in this article.</span></span>
    
#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="6f369-236">Phases d’utilisation de Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="6f369-236">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="6f369-237">L’utilisation de Bandwidth Utilization Analyzer implique deux phases :</span><span class="sxs-lookup"><span data-stu-id="6f369-237">There are two phases when using Bandwidth Utilization Analyzer:</span></span>
  
- <span data-ttu-id="6f369-238">collecte des journaux, effectuée à l’aide de WanLinkLogCollector.exe ;</span><span class="sxs-lookup"><span data-stu-id="6f369-238">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>
    
- <span data-ttu-id="6f369-239">personnalisation des rapports, effectuée à l’aide de BandwidthUtilizationAnalyzer.xlsm.</span><span class="sxs-lookup"><span data-stu-id="6f369-239">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6f369-240">Il est recommandé que BandwidthUtilizationAnalyzer.xlsm ne soit pas démarré manuellement par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="6f369-240">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span> 
  
#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="6f369-241">Démarrage de Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="6f369-241">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="6f369-242">Démarrez WanLinkLogCollector.exe dans une invite de commandes ou à l’aide de l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="6f369-242">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>
  
 <span data-ttu-id="6f369-243">**Utilisation de WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="6f369-243">**Using WanLinkLogCollector.exe**</span></span>
  
<span data-ttu-id="6f369-244">L’utilisation de WanLinkLogCollector.exe comporte trois étapes :</span><span class="sxs-lookup"><span data-stu-id="6f369-244">There are three steps to using WanLinkLogCollector.exe:</span></span>
  
1. <span data-ttu-id="6f369-245">**Journal de la chronologie** Fournir le rapport doit être généré pour la chronologie</span><span class="sxs-lookup"><span data-stu-id="6f369-245">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>
    
2. <span data-ttu-id="6f369-246">**Spécifier les répertoires de fichiers** Fournir des informations d’emplacement de fichier</span><span class="sxs-lookup"><span data-stu-id="6f369-246">**Specify the file directories** Provide file location information</span></span>
    
3. <span data-ttu-id="6f369-247">**Collecter les journaux et lancer la visionneuse de rapports** Exécutez la commande pour générer l’état</span><span class="sxs-lookup"><span data-stu-id="6f369-247">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>
    
#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="6f369-248">Étape 1 - Définition de la chronologie</span><span class="sxs-lookup"><span data-stu-id="6f369-248">Step 1 - Log the timeline</span></span>

<span data-ttu-id="6f369-249">La définition de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme indiqué dans la figure suivante. </span><span class="sxs-lookup"><span data-stu-id="6f369-249">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span> 
  
1. <span data-ttu-id="6f369-250">**Date de début** Il s’agit de la date de début de la chronologie le rapport doit être généré par exemple, le 1er août 2010.</span><span class="sxs-lookup"><span data-stu-id="6f369-250">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>
    
2. <span data-ttu-id="6f369-251">**Date de fin** Il s’agit de la date de fin du montage que le rapport doit être généré par exemple, le 30 septembre 2010.</span><span class="sxs-lookup"><span data-stu-id="6f369-251">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
     ![Dates de début et de fin de l’utilisation de la bande passante A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)
  
#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="6f369-253">Étape 2 - Définition des répertoires de fichiers</span><span class="sxs-lookup"><span data-stu-id="6f369-253">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="6f369-254">Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur, comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="6f369-254">The following file directories can be specified by the user as shown.</span></span>
  
- <span data-ttu-id="6f369-255">**Emplacement des fichiers journaux de serveur** L’emplacement du dossier où sont stockés les journaux de serveur de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="6f369-255">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="6f369-256">Il s’agit généralement de \<serveur de fichiers\>\\< choice de FE\>\AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="6f369-256">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>
    
- <span data-ttu-id="6f369-257">**Emplacement de stockage des fichiers temporaires** L’emplacement du fichier temporaire où les fichiers intermédiaires sont stockées pendant la génération du rapport.</span><span class="sxs-lookup"><span data-stu-id="6f369-257">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>
    
![Répertoires de fichiers dans Bandwidth Utilization Anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)
  
> [!NOTE]
> <span data-ttu-id="6f369-259">Vérifiez que l’utilisateur de l’outil dispose d’un accès suffisant aux journaux de serveur et au dossier du magasin des fichiers temporaires.</span><span class="sxs-lookup"><span data-stu-id="6f369-259">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span> 
  
#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="6f369-260">Étape 3 - Collecte des journaux et démarrage de la visionneuse de rapports</span><span class="sxs-lookup"><span data-stu-id="6f369-260">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="6f369-p120">Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **Execute (Exécuter)** comme indiqué ci-dessous. Cette opération permet de collecter les données requises.</span><span class="sxs-lookup"><span data-stu-id="6f369-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>
  
![Collecte de données d’analyse de l’utilisation de la bande passante](../media/Reskit_2012_Tools_Documentation_Image6.jpg)
  
<span data-ttu-id="6f369-264">Une fois le contenu saisi validé, le message suivant apparaît.</span><span class="sxs-lookup"><span data-stu-id="6f369-264">When the input validation is successful, the message shown below is displayed.</span></span>
  
![Notifications sur les journaux collectés dans Bandwidth Utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)
  
<span data-ttu-id="6f369-p121">Cliquez sur **OK**. BandwidthUtilizationAnalyzer.xlsm démarre automatiquement. Suivez les instructions du message. Pour plus d’informations, voir **Utilisation de BandwidthUtilizationAnalyzer.xlsm ** dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="6f369-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>
  
#### 

### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="6f369-270">Utilisation de BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="6f369-270">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="6f369-271">Une fois BandwidthUtilizationAnalyzer.xlsm démarré automatiquement, cliquez sur **Refresh (Actualiser)**, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-271">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)
  
2. <span data-ttu-id="6f369-p122">Si un dossier de fichiers est ouvert, sélectionnez consolidated.csv à l’emplacement spécifié dans le message, comme indiqué ci-dessous. L’emplacement du répertoire **C:\Temp** est également indiqué.</span><span class="sxs-lookup"><span data-stu-id="6f369-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>
    
     ![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)
  
3. <span data-ttu-id="6f369-276">Cliquez sur **Import (Importer)**.</span><span class="sxs-lookup"><span data-stu-id="6f369-276">Click **Import**.</span></span>
    
4. <span data-ttu-id="6f369-p123">La représentation graphique est générée automatiquement. Elle est disponible lorsque le pointeur de traitement en arrière-plan disparaît.</span><span class="sxs-lookup"><span data-stu-id="6f369-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
     ![Application de filtres à l’affichage du rapport.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="6f369-280">Application de filtres à l’affichage du rapport</span><span class="sxs-lookup"><span data-stu-id="6f369-280">Applying Filters to the Report View</span></span>

<span data-ttu-id="6f369-281">Les filtres suivants peuvent être appliqués à l’affichage du rapport :</span><span class="sxs-lookup"><span data-stu-id="6f369-281">The filters that can be applied to the report view as shown below are described as follows:</span></span>
  
![Application de filtres à l’affichage du rapport.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
1. <span data-ttu-id="6f369-283">**Name (Nom)** Filtrage des liaisons de réseau étendu (le filtre apparaît dans la partie droite du graphique). Le préfixe représente les types de liaisons suivants (voir l’encadré bleu vertical) :</span><span class="sxs-lookup"><span data-stu-id="6f369-283">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
  - <span data-ttu-id="6f369-284">**S Site (S (site))** Liaison de réseau étendu entre un site réseau et une région réseau</span><span class="sxs-lookup"><span data-stu-id="6f369-284">**S Site** The WAN link from a network site to a network region</span></span>
    
  - <span data-ttu-id="6f369-285">**IS Inter-Site (IS (intersite))** Liaison de réseau étendu entre deux sites réseau</span><span class="sxs-lookup"><span data-stu-id="6f369-285">**IS Inter-Site** The WAN link between two network sites</span></span>
    
  - <span data-ttu-id="6f369-286">**R Inter-Region (R (inter-régions))**Liaison de réseau étendu entre deux régions réseau</span><span class="sxs-lookup"><span data-stu-id="6f369-286">**R Inter-Region** The WAN link between two network region</span></span>
    
2. <span data-ttu-id="6f369-287">**Exceeded limit (Limite dépassée)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est supérieure à la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="6f369-287">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>
    
3. <span data-ttu-id="6f369-288">**Critical levels (Niveaux critiques)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante a atteint 90 % ou plus de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="6f369-288">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>
    
4. <span data-ttu-id="6f369-289">**Under-utilized (Sous-utilisé)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est inférieure à 25 % de la capacité de bande passante</span><span class="sxs-lookup"><span data-stu-id="6f369-289">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>
    
5. <span data-ttu-id="6f369-290">**Link type (Type de liaison)** Filtrage des types de liaisons de réseau étendu suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-290">**Link type** Filter by the following WAN links types:</span></span>
    
  - <span data-ttu-id="6f369-291">**Network site (Site réseau)**</span><span class="sxs-lookup"><span data-stu-id="6f369-291">**Network site** type</span></span>
    
  - <span data-ttu-id="6f369-292">**Inter-site (intersite)**</span><span class="sxs-lookup"><span data-stu-id="6f369-292">**Inter-site** type</span></span>
    
  - <span data-ttu-id="6f369-293">**Inter-Region (Inter-régions)**</span><span class="sxs-lookup"><span data-stu-id="6f369-293">**Inter-Region link** type</span></span>
    
6. <span data-ttu-id="6f369-294">**Region (Région)** Filtrage de la région réseau</span><span class="sxs-lookup"><span data-stu-id="6f369-294">**Region** Filter by network region</span></span>
    
<span data-ttu-id="6f369-295">Les figures suivantes présentent les filtres décrits précédemment.</span><span class="sxs-lookup"><span data-stu-id="6f369-295">The following figures show the previously described filters.</span></span>
  
<span data-ttu-id="6f369-p124">Filtrage sur **Name (Nom)**. Sélectionnez la liste des liaisons devant être affichées dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>
  
![Filtrage sur Name (Nom) dans BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)
  
<span data-ttu-id="6f369-p125">Filtrage sur **Exceeded limit (Limite dépassée)**. Sélectionnez **True ** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="6f369-p125">Filter by **Exceeded limit**. Select **True** to enforce the filter.</span></span>
  
![Filtrage sur Exceeded limit (Limite dépassée).](../media/Reskit_2012_Tools_Documentation_Image13.jpg)
  
<span data-ttu-id="6f369-p126">Filtrage sur **Critical levels (Niveaux critiques)**. Sélectionnez **True** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="6f369-p126">Filter by **Critical levels**. Select **True** to enforce the filter.</span></span>
  
![Filtrage sur Critical Levels (Niveaux critiques).](../media/Reskit_2012_Tools_Documentation_Image14.jpg)
  
<span data-ttu-id="6f369-p127">Filtrage sur **Under utilized (Sous-utilisé)**. Sélectionnez **True** pour appliquer le filtre.</span><span class="sxs-lookup"><span data-stu-id="6f369-p127">Filter by **Under utilized**. Select **True** to enforce the filter.</span></span>
  
![Filtrage sur Under Utilized (Sous-utilisé).](../media/Reskit_2012_Tools_Documentation_Image15.jpg)
  
<span data-ttu-id="6f369-p128">Filtrage sur **Link Type (Type de liaison)**. Sélectionnez le ou les types devant être affichés.</span><span class="sxs-lookup"><span data-stu-id="6f369-p128">Filter by **Link Type**. Select the type or types that need to be displayed.</span></span>
  
![Filtrage sur Link Type (Type de lien).](../media/Reskit_2012_Tools_Documentation_Image16.jpg)
  
<span data-ttu-id="6f369-p129">Filtrage sur **Region (Région)**. Sélectionnez la liste des régions pour lesquelles afficher les liaisons.</span><span class="sxs-lookup"><span data-stu-id="6f369-p129">Filter by **Region**. Select a list of regions whose links need to be displayed.</span></span>
  
![Filtrage sur (Region) Région.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)
  
### <a name="requirements"></a><span data-ttu-id="6f369-314">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-314">Requirements</span></span>

- <span data-ttu-id="6f369-315">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="6f369-315">The .NET Framework 3.5</span></span>
    
- <span data-ttu-id="6f369-316">Microsoft Excel 2010 ou Excel 2007</span><span class="sxs-lookup"><span data-stu-id="6f369-316">Microsoft Excel 2010 or Excel 2007</span></span>
    
### <a name="summary"></a><span data-ttu-id="6f369-317">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-317">Summary</span></span>

<span data-ttu-id="6f369-p130">Bandwidth Utilization Analyzer permet de représenter l’utilisation de la bande passante audio pour le trafic des communications unifiées dans le réseau. Il permet également de créer des rapports sur l’utilisation de la bande passante vidéo dans le réseau.</span><span class="sxs-lookup"><span data-stu-id="6f369-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>
  
## <a name="call-parkometer"></a><span data-ttu-id="6f369-320">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="6f369-320">Call Parkometer</span></span>
<span data-ttu-id="6f369-321"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-321"></span></span>

<span data-ttu-id="6f369-322">L’application en ligne de commande Call Parkometer permet d’accéder facilement à la base de données des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-322">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-323">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-323">Description</span></span>

<span data-ttu-id="6f369-324">L’outil Call Parkometer permet de suivre les appels actuellement parqués.</span><span class="sxs-lookup"><span data-stu-id="6f369-324">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="6f369-325">Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-325">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="6f369-326">Cet outil de ligne de commande fournit à la fois en lecture et accès en écriture à l’orbite de CPS de la base de données SQL Server à partir d’un ordinateur local ou à distance connecté.</span><span class="sxs-lookup"><span data-stu-id="6f369-326">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>
  
<span data-ttu-id="6f369-p132">Toutes les options s’excluent mutuellement. La syntaxe suivante est appliquée à la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="6f369-p132">All options are mutually exclusive. Command-line syntax is as follows:</span></span>
  
- <span data-ttu-id="6f369-329">paramètre **-o** — listes tous orbite plages configurées pour ce pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-329">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>
    
- <span data-ttu-id="6f369-330">paramètre **-n** : orbites répertorie tous les actuellement utilisés dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-330">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="6f369-331">Les informations suivantes sont affichées :</span><span class="sxs-lookup"><span data-stu-id="6f369-331">The information displayed is as follows:</span></span>
    
  - <span data-ttu-id="6f369-332">URI (Uniform Resource Identifier) SIP du parqué et du parqueur.</span><span class="sxs-lookup"><span data-stu-id="6f369-332">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
  - <span data-ttu-id="6f369-333">Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.</span><span class="sxs-lookup"><span data-stu-id="6f369-333">Host name of the CPS where the call is parked.</span></span>
    
  - <span data-ttu-id="6f369-334">Date/heure du parcage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-334">Time stamp of when the call was parked.</span></span>
    
- <span data-ttu-id="6f369-335">paramètre **-f** — indique le nombre d’orbites libres dans le pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-335">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>
    
- <span data-ttu-id="6f369-336">**r - \<n\> ** paramètre — répertorie les \<n\> dernier stationnés appels.</span><span class="sxs-lookup"><span data-stu-id="6f369-336">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="6f369-337">Les informations suivantes sont affichées :</span><span class="sxs-lookup"><span data-stu-id="6f369-337">The information displayed is as follows:</span></span>
    
  - <span data-ttu-id="6f369-338">URI SIP du parqué.</span><span class="sxs-lookup"><span data-stu-id="6f369-338">Parkee SIP URI.</span></span>
    
  - <span data-ttu-id="6f369-339">URI SIP du parqueur.</span><span class="sxs-lookup"><span data-stu-id="6f369-339">Parker SIP URI.</span></span>
    
  - <span data-ttu-id="6f369-340">Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.</span><span class="sxs-lookup"><span data-stu-id="6f369-340">Host name of the CPS where the call was parked.</span></span>
    
  - <span data-ttu-id="6f369-341">Date/heure de récupération ou d’abandon de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-341">Time stamp of when the call was retrieved or dropped.</span></span>
    
- <span data-ttu-id="6f369-342">**-t\<n\> ** paramètre - teste la réservation d’une orbite dans la base de données pour afficher le caractère aléatoire des nombres orbite affectées.</span><span class="sxs-lookup"><span data-stu-id="6f369-342">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>
    
### <a name="output"></a><span data-ttu-id="6f369-343">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-343">Output</span></span>

<span data-ttu-id="6f369-344">Selon les paramètres d’entrée spécifiés dans l’invite de commandes, l’outil Call Parkometer affiche la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="6f369-344">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>
  
- <span data-ttu-id="6f369-345">plages d’orbites configurées pour ce pool ;</span><span class="sxs-lookup"><span data-stu-id="6f369-345">All orbit ranges that are configured for this pool</span></span>
    
- <span data-ttu-id="6f369-346">appels actuellement parqués ;</span><span class="sxs-lookup"><span data-stu-id="6f369-346">Currently parked calls</span></span>
    
- <span data-ttu-id="6f369-347">nombre d’orbites libres (disponibles) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-347">Number of free (available) orbits</span></span>
    
- <span data-ttu-id="6f369-348">appels parqués récemment ;</span><span class="sxs-lookup"><span data-stu-id="6f369-348">Recently parked calls</span></span>
    
- <span data-ttu-id="6f369-349">orbites réservées pour le test des valeurs d’orbite uniformes et aléatoires.</span><span class="sxs-lookup"><span data-stu-id="6f369-349">Reserved orbits for testing uniform and random orbit values</span></span>
    
### <a name="purpose"></a><span data-ttu-id="6f369-350">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-350">Purpose</span></span>

<span data-ttu-id="6f369-p135">L’outil CPS vie à fournir un accès par ligne de commande à la base de données du serveur de parcage d’appel. L’administrateur peut consulter l’utilisation du serveur de parcage d’appel et déterminer le nombre d’orbites affectées à un pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="6f369-353">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-353">Requirements</span></span>

<span data-ttu-id="6f369-354">Aucune configuration n’est requise si cet outil est exécuté sur l’ordinateur qui exécute le serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-354">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="6f369-355">Si cet outil est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Skype pour Business Server 2015 doit être configuré pour autoriser l’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="6f369-355">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="6f369-356">Appel de Parkometer doit être configuré avec une chaîne de connexion de base de données SQL Server pour se connecter à SQL Server du pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-356">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="6f369-357">Cette chaîne de connexion de base de données SQL Server est définie dans le fichier de configuration **parkometer.exe.config**. Il doit être placé dans le même répertoire où se trouve le parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="6f369-357">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="6f369-358">Le fichier XML suivant est un exemple d’un parkometer.exe.config. Les paramètres qui doivent être configurés sont les nom d’utilisateur (par exemple, mydomain\Administrator), le mot de passe (par exemple, MonMotdePasse) et nom d’hôte (par exemple, myserver).</span><span class="sxs-lookup"><span data-stu-id="6f369-358">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>
  
```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a><span data-ttu-id="6f369-359">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-359">Examples</span></span>

<span data-ttu-id="6f369-360">Déployé des plages d’orbite : le paramètre-o répertorie toutes les plages d’orbite qui sont configurées pour ce pool comme indiqué</span><span class="sxs-lookup"><span data-stu-id="6f369-360">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>
  
![Plages d’orbites dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)
  
<span data-ttu-id="6f369-362">Actuellement stationnés appels : le paramètre-n répertorie tous les orbites actuellement utilisés sur ce pool comme indiqué</span><span class="sxs-lookup"><span data-stu-id="6f369-362">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>
  
![Appels actuellement parqués dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)
  
<span data-ttu-id="6f369-364">Nombre d’orbites libres : le paramètre-f répertorie le nombre d’orbites libres dans le pool comme indiqué</span><span class="sxs-lookup"><span data-stu-id="6f369-364">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>
  
![Orbites libres dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)
  
<span data-ttu-id="6f369-366">Récemment stationnés appels : - r \<n\> listes de paramètres de la \<n\> stationnés dernier appels comme indiqué</span><span class="sxs-lookup"><span data-stu-id="6f369-366">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>
  
![Appels parqués récemment dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)
  
<span data-ttu-id="6f369-368">Réservation de l’orbite de test : -t \<n\> paramètre teste la réservation d’une orbite dans la base de données comme indiqué</span><span class="sxs-lookup"><span data-stu-id="6f369-368">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>
  
![Test de réservation d’orbite dans Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)
  
### <a name="summary"></a><span data-ttu-id="6f369-370">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-370">Summary</span></span>

<span data-ttu-id="6f369-371">L’outil en ligne de commande Call Parkometer fournit des informations détaillées sur le serveur de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-371">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>
  
## <a name="dbanalyze"></a><span data-ttu-id="6f369-372">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="6f369-372">DBAnalyze</span></span>
<span data-ttu-id="6f369-373"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-373"></span></span>

### <a name="description"></a><span data-ttu-id="6f369-374">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-374">Description</span></span>

<span data-ttu-id="6f369-375">DBAnalyze est un outil de ligne de commande qui permet aux administrateurs d’établir des rapports d’analyse sur le Skype pour les bases de données Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-375">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="6f369-376">DBAnalyze inclut les modes suivants : diagnostic, données des utilisateurs, conférence, unités de contrôle multipoint et fragmentation des disques :</span><span class="sxs-lookup"><span data-stu-id="6f369-376">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>
  
- <span data-ttu-id="6f369-377">**Mode diagnostic** Crée un rapport qui inclut des informations sur les tables (nombre d’enregistrements, la fragmentation, taille des données et la taille de l’index), des tailles de fichiers journaux et de données, la sauvegarde dernière, distribution des contacts entre les serveurs qui exécutent Microsoft Office Communications Server, le Nombre moyen d’autorisations, contacts, conteneurs, abonnements, publications, points de terminaison par utilisateur, les utilisateurs hébergées de manière incorrecte, les utilisateurs qui ne peuvent pas être routés, le nombre moyen de conférences organisées par utilisateur, des conférences, des conférences actives, et la version de la base de données.</span><span class="sxs-lookup"><span data-stu-id="6f369-377">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f369-378">L’exécution du mode Diagnostic peut affecter les performances des serveurs.</span><span class="sxs-lookup"><span data-stu-id="6f369-378">Running diagnostic mode can affect server performance.</span></span> 
  
- <span data-ttu-id="6f369-379">**Mode de données utilisateur** Rapports contact, conteneur, abonnement, publication, autorisation et des données de groupe de contact pour un utilisateur spécifié ou pour les utilisateurs qui ont cet utilisateur dans leurs listes de contact et d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="6f369-379">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="6f369-380">Ce mode transmet également des données résumées sur les conférences organisées par un utilisateur ou auxquelles il est invité.</span><span class="sxs-lookup"><span data-stu-id="6f369-380">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>
    
- <span data-ttu-id="6f369-381">**Mode conférence** Rapports des données détaillées pour une conférence spécifique, y compris tous les détails de planification au moment de la conférence, la liste des invités, la liste des types de médias autorisés pour la conférence, active MCU (unité de contrôle multipoint), la liste des participants actif et chacun état de signalisation du participant.</span><span class="sxs-lookup"><span data-stu-id="6f369-381">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>
    
- <span data-ttu-id="6f369-382">**ID de la réunion de décodage** Décode un réseau téléphonique public commuté (RTPC) ID qui est spécifié par le commutateur **/pstnid** , mais ne se connecte pas au serveur principal pour obtenir des informations détaillées de la réunion.</span><span class="sxs-lookup"><span data-stu-id="6f369-382">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>
    
- <span data-ttu-id="6f369-383">**Résoudre la conférence** Décode un ID de réunion RTPC qui est spécifié par le commutateur **/pstnid** et affiche des informations sur la conférence indiquée par le code.</span><span class="sxs-lookup"><span data-stu-id="6f369-383">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>
    
- <span data-ttu-id="6f369-384">**Mode de MCU** Signale l’ID type de média, URL, état de pulsation, charge de conférence et charge participant pour chaque MCU dans le pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-384">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>
    
- <span data-ttu-id="6f369-385">**Mode de fragmentation de disque** Affiche l’état de fragmentation de tous les disques.</span><span class="sxs-lookup"><span data-stu-id="6f369-385">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>
    
<span data-ttu-id="6f369-p139">Cet outil permet de diagnostiquer plusieurs problèmes ou de planifier la capacité. Par exemple, si la plupart des utilisateurs hébergés sur un serveur A définissent des utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs du serveur A vers le serveur B afin de réduire le trafic entre les serveurs.</span><span class="sxs-lookup"><span data-stu-id="6f369-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>
  
### <a name="output"></a><span data-ttu-id="6f369-388">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-388">Output</span></span>

<span data-ttu-id="6f369-389">Cet outil génère des rapports prédéfinis sur le Skype pour la base de données de l’activité serveur 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-389">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="6f369-390">**Chemin d’accès**: %ProgramFiles%\Skype pour les entreprises 2015\Reskit de serveur</span><span class="sxs-lookup"><span data-stu-id="6f369-390">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>
  
### <a name="purpose"></a><span data-ttu-id="6f369-391">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-391">Purpose</span></span>

<span data-ttu-id="6f369-392">Pour installer Dbanalyze.exe, copiez-le dans un dossier local et ensuite exécuter l’outil.</span><span class="sxs-lookup"><span data-stu-id="6f369-392">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="6f369-393">Pour utiliser l’outil, exécutez la commande suivante à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="6f369-393">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="6f369-394">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Les descriptions pour les options de ligne de commande sont présentées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-394">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>
  
![Option de ligne de commande pour Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)
  
### <a name="requirements"></a><span data-ttu-id="6f369-396">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="6f369-396">Requirements</span></span>

 <span data-ttu-id="6f369-397">**Ordinateur** DBAnalyze peut être exécuté qu’à partir d’un ordinateur à un domaine qui a Skype pour Business Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="6f369-397">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>
  
 <span data-ttu-id="6f369-398">**Réseau** L’ordinateur doit pouvoir se connecter à la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="6f369-398">**Network** The computer should be able to connect to the back-end database.</span></span>
  
 <span data-ttu-id="6f369-399">**Logiciel** Skype pour les composants du logiciel Business Server 2015 doit être installé avant d’exécuter DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="6f369-399">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>
  
 <span data-ttu-id="6f369-400">**Utilisateurs** Le tableau ci-dessous montre les administrateurs qui disposent des autorisations nécessaires pour accéder à des bases de données Business Server 2015 Skype.</span><span class="sxs-lookup"><span data-stu-id="6f369-400">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>
  
![Tableau d’autorisations pour Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)
  
> [!NOTE]
> <span data-ttu-id="6f369-402">Un compte d’administrateur local est nécessaire pour le mode **/report:disk**.</span><span class="sxs-lookup"><span data-stu-id="6f369-402">A local administrator account is required for **/report:disk** mode.</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-403">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-403">Examples</span></span>

<span data-ttu-id="6f369-404">Les exemples suivants constituent des commandes Dbanalyze.exe correctes :</span><span class="sxs-lookup"><span data-stu-id="6f369-404">The following are examples of valid Dbanalyze.exe commands:</span></span>
  
```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="6f369-405">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-405">Summary</span></span>

<span data-ttu-id="6f369-406">DBAnalyzer fournit aux administrateurs une rapide et facile à analyser Skype pour les bases de données Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-406">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>
  
## <a name="import-storage-service-data"></a><span data-ttu-id="6f369-407">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="6f369-407">Import Storage Service Data</span></span>
<span data-ttu-id="6f369-408"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-408"></span></span>

<span data-ttu-id="6f369-409">L’outil de kit de ressources ImportStorageServiceData permet de réimporter les données de file d’attente et de point de terminaison éliminées du service de stockage Lync Server dans le service de stockage.</span><span class="sxs-lookup"><span data-stu-id="6f369-409">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-410">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-410">Description</span></span>

<span data-ttu-id="6f369-411">L’élimination de données du service de stockage peut être automatique (périodique) selon le statut des éléments de file d’attente ou la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="6f369-411">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="6f369-412">Elle peut survenir suite à l’invocation manuelle de l’applet de commande de basculement du pool ou StorageServiceFullFlush (invoquée par l’applet de commande de basculement du pool).</span><span class="sxs-lookup"><span data-stu-id="6f369-412">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="6f369-413">Notez que données doivent idéalement pas être importées à nouveau si une de la taille de la base de données stockage Service (LYSS) sur les serveurs frontaux est supérieure au niveau normal, car cela provoquera probablement des simplement plus de données à exporter à l’arrière. En outre, les problèmes qui aurait peuvent contribuer à des erreurs qui a provoqué la file d’attente du Service de stockage de croître doivent tout d’abord être résolus (pour les erreurs de point de terminaison exemple Exchange, des problèmes de réseau ou autres problèmes).</span><span class="sxs-lookup"><span data-stu-id="6f369-413">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>
  
 <span data-ttu-id="6f369-414">**Scénario 1 :** lors du basculement du pool, les fichiers peuvent être éliminés du service de stockage de chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="6f369-414">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="6f369-415">Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.</span><span class="sxs-lookup"><span data-stu-id="6f369-415">After failover is completed, the tool should be run to re-import the data.</span></span>
  
 <span data-ttu-id="6f369-416">**Scénario 2 :** les données sont éliminées automatiquement chaque jour ou suite au dépassement de certains seuils de taille par la base de données du service de stockage (par exemple, 60 %, 80 %, 90 % de remplissage).</span><span class="sxs-lookup"><span data-stu-id="6f369-416">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="6f369-417">Ces données éliminées automatiquement doivent être régulièrement réimportées par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-417">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="6f369-418">Dans ce cas, si le pack SCOM surveillance n’est pas déployé, il sont des événements de Skype pour le Service de stockage Business Server relatives aux données à partir du Service de stockage en cours de vidage.</span><span class="sxs-lookup"><span data-stu-id="6f369-418">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="6f369-419">Les ID d’événement 32075 (démarrage du vidage complet), 32076 (fin du vidage complet), 32082 (démarrage du vidage de niveau maintenance), 32083 (fin du vidage de niveau maintenance), 32089 (vidage effectué à cause du remplissage de la base de données).</span><span class="sxs-lookup"><span data-stu-id="6f369-419">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="6f369-420">Notez que ces ID d’événement correspondent à la version finale.</span><span class="sxs-lookup"><span data-stu-id="6f369-420">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="6f369-421">Lorsqu’un administrateur voit ces événements, cela signifie qu’il existe des fichiers qui ont été vidées. Ces données doivent être régulièrement importées à l’aide de cet outil, par exemple une fois par semaine.</span><span class="sxs-lookup"><span data-stu-id="6f369-421">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>
  
<span data-ttu-id="6f369-422">Pour la version de Service en ligne, si le pack SCOM Skype pour serveur d’entreprise de contrôle d’état est déployé, il y a les nouvelles alertes qui peuvent être déclenchés et qui demandent à l’administrateur de réimporter les données vidangées vers le Service de stockage.</span><span class="sxs-lookup"><span data-stu-id="6f369-422">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="6f369-423">Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui a déclenché l’alerte.</span><span class="sxs-lookup"><span data-stu-id="6f369-423">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="6f369-424">L’événement donnera une description du chemin d’accès Parent sous lequel se trouvent les fichiers de données vidées, ainsi que la manière dont de nombreux fichiers sont qui remplissent les critères d’alerte.</span><span class="sxs-lookup"><span data-stu-id="6f369-424">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="6f369-425">Les critères d’alerte est qu’il sont X ou plus de fichiers sous le chemin d’accès parent particulier qui sont au moins Y jours (où X et Y sont prédéfinies dans la StorageService mais peuvent être substituée en modifiant le fichier APPCONFIG.) Deux exemples d’événements qui peuvent déclencher l’alerte de santé figurent ci-dessous, la différence étant le chemin d’accès de leur parent.</span><span class="sxs-lookup"><span data-stu-id="6f369-425">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="6f369-426">Il est possible sous partage de fichier du service Web, tandis que l’autre est le répertoire de données d’Application local de chaque front-end.</span><span class="sxs-lookup"><span data-stu-id="6f369-426">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="6f369-427">(par exemple c:\ProgramData\Microsoft\Skype pour Business Server 2015\StorageService).</span><span class="sxs-lookup"><span data-stu-id="6f369-427">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="6f369-428">L’administrateur exécutera alors cet outil du Kit de ressources.</span><span class="sxs-lookup"><span data-stu-id="6f369-428">The administrator will then run this reskit tool.</span></span>
  
<span data-ttu-id="6f369-429">Cet outil augmente la charge processeur et d’E/S sur le serveur frontal sur lequel il est exécuté, ainsi que sur les autre serveurs frontaux, si les données n’appartiennent pas au serveur frontal sur lequel l’outil est exécuté.</span><span class="sxs-lookup"><span data-stu-id="6f369-429">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="6f369-430">Il est recommandé d’exécuter cet outil lorsque les serveurs frontaux ne sont pas soumis à une charge processeur et d’E/S importante, par exemple en dehors des heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="6f369-430">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="6f369-431">Deuxièmement, cet outil peut prendre 2 à 3 minutes pour importer un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="6f369-431">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="6f369-432">Vous devez garder cette information à l’esprit lorsque vous cherchez à estimer le délai d’exécution de l’outil.</span><span class="sxs-lookup"><span data-stu-id="6f369-432">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="6f369-433">Le fichier journal détaillé généré par l’outil apparaît par défaut dans le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="6f369-433">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="6f369-434">Supprimez-le si aucune erreur n’est signalée, car la taille de celui-ci peut atteindre plusieurs Mo, voire davantage.</span><span class="sxs-lookup"><span data-stu-id="6f369-434">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>
  
![Exemple d’événements du journal des événements du serveur de stockage.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)
  
### <a name="requirements"></a><span data-ttu-id="6f369-436">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="6f369-436">Requirements</span></span>

<span data-ttu-id="6f369-437">Installer le Skype pour les outils du Kit de ressources de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-437">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="6f369-438">L’outil s’exécute sur des ordinateurs à un domaine dans lequel sont installés les Skype pour Business Server et Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6f369-438">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="6f369-439">L’outil utilise une applet de commande à partir du shell de gestion pour identifier tous les serveurs frontaux dans le pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-439">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="6f369-440">Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur dans le pool qui a installé la base de données **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="6f369-440">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="6f369-441">Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichier WEBSERVICE pour le pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-441">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="6f369-442">En outre, avant d’utiliser l’outil, chaque serveur frontal devez d’abord activer à l’aide de **PSRemoting de l’activer** sur chaque serveur frontal, ainsi que l’ordinateur sur lequel l’outil est exécuté à partir d’accès distant de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f369-442">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="6f369-443">Dans le cas contraire, les commandes Windows PowerShell à distance à partir de cet outil échoue.</span><span class="sxs-lookup"><span data-stu-id="6f369-443">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="6f369-444">Accès distant de Windows PowerShell peut être désactivée sur tous les serveurs frontaux dans le pool une fois qu’il est terminé.</span><span class="sxs-lookup"><span data-stu-id="6f369-444">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="6f369-445">Enfin, le compte ou les informations d’identification de l’appel de l’outil doivent avoir des autorisations en lecture/écriture pour le partage de fichiers pour le pool qu’ils sont exécutent cet outil sur webservice.</span><span class="sxs-lookup"><span data-stu-id="6f369-445">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="6f369-446">Dans le cas contraire, l’outil va échouer avec des erreurs d’autorisation e/s.</span><span class="sxs-lookup"><span data-stu-id="6f369-446">Otherwise the tool will fail with IO Permission errors.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f369-447">Sur Windows Server 2012, la communication à distance de Windows PowerShell est activée par défaut, mais pas sur le système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="6f369-447">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span> 
  
### <a name="examples"></a><span data-ttu-id="6f369-448">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-448">Examples</span></span>

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                    
-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a><span data-ttu-id="6f369-449">LCSSync</span><span class="sxs-lookup"><span data-stu-id="6f369-449">LCSSync</span></span>
<span data-ttu-id="6f369-450"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-450"></span></span>

<span data-ttu-id="6f369-451">L’outil LCSSync permet de déployer Skype pour le logiciel de communication 2015 de serveur d’entreprise dans un environnement à plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="6f369-451">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="6f369-452">Cet outil est utilisé pour synchroniser les utilisateurs et les groupes à partir de forêts autre utilisateur sous la forme d’un Active Directory Domain Services contactez objet vers une forêt centrale où Skype pour Business Server 2015 est installé.</span><span class="sxs-lookup"><span data-stu-id="6f369-452">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-453">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-453">Description</span></span>

 <span data-ttu-id="6f369-454">LCSSync utilise les Services de domaine Active Directory synchronisée objets contacts de la forêt centrale pour permettre aux utilisateurs de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="6f369-454">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="6f369-455">Pour fournir de l’authentification unique, le compte d’utilisateur principal doit être mappé à l’objet de contact des Services de domaine Active Directory dans la forêt centrale pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-455">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="6f369-456">Cet outil aide à effectuer l’opération de mappage.</span><span class="sxs-lookup"><span data-stu-id="6f369-456">This tool helps perform that mapping.</span></span> <span data-ttu-id="6f369-457">Il fournit des modèles pour la création des agents de gestion dans Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="6f369-457">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>
  
### <a name="summary"></a><span data-ttu-id="6f369-458">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-458">Summary</span></span>

<span data-ttu-id="6f369-459">L’outil LCSSync permet de déployer Skype pour 2015 de serveur d’entreprise dans un environnement à plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="6f369-459">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>
  
## <a name="lookup-user-console"></a><span data-ttu-id="6f369-460">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="6f369-460">Lookup User Console</span></span>
<span data-ttu-id="6f369-461"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-461"></span></span>

<span data-ttu-id="6f369-462">L’outil LookupUserConsole affiche interne Skype Business Server informations de routage sur des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6f369-462">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="6f369-463">Ces informations peuvent être utiles au personnel du support technique Microsoft dans le cadre du diagnostic des problèmes de déploiement et de routage.</span><span class="sxs-lookup"><span data-stu-id="6f369-463">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-464">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-464">Description</span></span>

 <span data-ttu-id="6f369-465">L’exécution de LookupUserConsole.exe, une invite de commandes qui accepte les adresses SIP et tente d’afficher Skype interne pour les informations de routage Business Server concernant les s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="6f369-465">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="6f369-466">Tapez **exit** pour quitter l’outil LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="6f369-466">Type **exit** to quit the LookupUserConsole tool.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="6f369-467">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-467">Requirements</span></span>

<span data-ttu-id="6f369-468">Installer le Skype pour le Kit de ressources de serveur 2015 Business.</span><span class="sxs-lookup"><span data-stu-id="6f369-468">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="6f369-469">L’outil s’exécute sur des ordinateurs à un domaine dans lequel Skype pour Business Server est installé.</span><span class="sxs-lookup"><span data-stu-id="6f369-469">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-470">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-470">Examples</span></span>

<span data-ttu-id="6f369-471">Files\Skype C:\Program pour Business Server 2015\ResKit\>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="6f369-471">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>
  
```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a><span data-ttu-id="6f369-472">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="6f369-472">MsTurnPing</span></span>
<span data-ttu-id="6f369-473"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-473"></span></span>

<span data-ttu-id="6f369-474">L’outil MSTurnPing permet à un administrateur de Skype pour le logiciel de communication Business Server 2015 pour vérifier l’état des serveurs exécutant les services Audio/vidéo et Audio/vidéo authentification ainsi que les serveurs qui exécutent les règles de bande passante Services de la topologie.</span><span class="sxs-lookup"><span data-stu-id="6f369-474">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-475">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-475">Description</span></span>

<span data-ttu-id="6f369-476">L’outil MSTurnPing permet à un administrateur de Skype pour le logiciel de communication Business Server 2015 pour vérifier l’état des serveurs exécutant les services Audio/vidéo et Audio/vidéo authentification ainsi que les serveurs qui exécutent les règles de bande passante Services de la topologie.</span><span class="sxs-lookup"><span data-stu-id="6f369-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>
  
<span data-ttu-id="6f369-477">L’outil permet d’effectuer les tests suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-477">The tool allows the administrator to perform the following tests:</span></span>
  
1. <span data-ttu-id="6f369-478">Test des serveurs Edge A/V : l’outil effectue des tests sur tous les serveurs Edge A/V dans la topologie comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f369-478">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
  - <span data-ttu-id="6f369-479">Vérification que le Skype pour le service de l’authentification du serveur Audio/vidéo professionnels est lancé et peut émettre des informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="6f369-479">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
  - <span data-ttu-id="6f369-480">Vérification que le Skype pour service d’entreprise, serveur Edge Audio/vidéo est démarré et qu’il peut allouer les ressources de la périphérie externe avec succès.</span><span class="sxs-lookup"><span data-stu-id="6f369-480">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>
    
2. <span data-ttu-id="6f369-481">Test des services de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs exécutant les services de stratégie de bande passante dans la topologie comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f369-481">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
  - <span data-ttu-id="6f369-482">Vérification que le Skype pour le Service de stratégie de bande passante Business Server (authentification) est démarré et peut émettre des informations d’identification appropriées.</span><span class="sxs-lookup"><span data-stu-id="6f369-482">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
  - <span data-ttu-id="6f369-483">Vérification que le Skype pour le Service de stratégie de bande passante Business Server (principal) est démarré et qu’il peut effectuer la vérification de la bande passante avec succès.</span><span class="sxs-lookup"><span data-stu-id="6f369-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>
    
<span data-ttu-id="6f369-484">Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé. </span><span class="sxs-lookup"><span data-stu-id="6f369-484">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span> 
  
### <a name="output"></a><span data-ttu-id="6f369-485">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-485">Output</span></span>

<span data-ttu-id="6f369-486">L’outil génère des résultats pour chacune des opérations.</span><span class="sxs-lookup"><span data-stu-id="6f369-486">The tool outputs the results of each of the operations.</span></span>
  
- <span data-ttu-id="6f369-487">Pour le test **AudioVideoEdgeServer**, l’outil génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-487">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
  - <span data-ttu-id="6f369-488">Les résultats de test des ordinateurs qui fournissent le Skype pour le service d’authentification de serveur 2015 Audio/vidéo professionnels dans la topologie</span><span class="sxs-lookup"><span data-stu-id="6f369-488">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>
    
  - <span data-ttu-id="6f369-489">Les résultats de test des ordinateurs qui fournissent le Skype pour le service Business Server 2015 Audio/vidéo bord dans la topologie</span><span class="sxs-lookup"><span data-stu-id="6f369-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>
    
- <span data-ttu-id="6f369-490">Pour le test **BandwidthPolicyServer**, l’outil génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-490">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
  - <span data-ttu-id="6f369-491">Les résultats de test des ordinateurs qui fournissent le Skype pour entreprise 2015 bande passante stratégie de Service du serveur (authentification) dans la topologie</span><span class="sxs-lookup"><span data-stu-id="6f369-491">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>
    
  - <span data-ttu-id="6f369-492">Les résultats de test des ordinateurs qui fournissent le Skype pour Business Server 2015 bande passante stratégie Service (de base) dans la topologie</span><span class="sxs-lookup"><span data-stu-id="6f369-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>
    
### <a name="requirements"></a><span data-ttu-id="6f369-493">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-493">Requirements</span></span>

- <span data-ttu-id="6f369-494">Cet outil doit être exécuté à partir d’un ordinateur de la topologie sur lequel le magasin local est installé.</span><span class="sxs-lookup"><span data-stu-id="6f369-494">This tool must be run from a computer that is in the topology and that has the local store.</span></span>
    
- <span data-ttu-id="6f369-495">L’outil doit être exécuté par un administrateur ayant accès au magasin local.</span><span class="sxs-lookup"><span data-stu-id="6f369-495">The tool must be run as an administrator who has access to the local store.</span></span>
    
### <a name="examples"></a><span data-ttu-id="6f369-496">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-496">Examples</span></span>

<span data-ttu-id="6f369-497">Voici un exemple de saisie pour l’outil.</span><span class="sxs-lookup"><span data-stu-id="6f369-497">The following is an example of the tool input.</span></span>
  
```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="6f369-498">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-498">Summary</span></span>

<span data-ttu-id="6f369-499">Cet outil peut être une ressource précieuse pour Skype pour Business Server 2015 les administrateurs qui souhaitent vérifier l’état des serveurs qui exécutent audio/vidéo et des services de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="6f369-499">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>
  
## <a name="network-configuration-viewer"></a><span data-ttu-id="6f369-500">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="6f369-500">Network Configuration Viewer</span></span>
<span data-ttu-id="6f369-501"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-501"></span></span>

<span data-ttu-id="6f369-502">Visionneuse de Configuration réseau peut être utilisé par Skype pour les administrateurs de logiciel Business Server 2015 communications permet d’afficher la topologie de réseau appel admission contrôle (CAC) pour une entreprise qui est configurée pour autoriser les sessions de communication en temps réel, telles que appels vocaux ou vidéo basés sur la capacité de la bande passante spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6f369-502">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="6f369-503">Skype pour les administrateurs d’entreprise serveur 2015 définir des stratégies CAC, qui sont appliquées par les services de règles de bande passante qui sont installés avec Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-503">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-504">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-504">Description</span></span>

<span data-ttu-id="6f369-505">Network Configuration Viewer (NetworkConfigurationViewer.exe) permet aux administrateurs d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-505">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>
  
- <span data-ttu-id="6f369-506">Charger et de visualiser la topologie du réseau à partir d’un Skype pour le déploiement de Business Server 2015 CAC dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-506">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>
    
- <span data-ttu-id="6f369-507">charger et afficher la topologie réseau de contrôle d’admission des appels à partir d‘un fichier journal de serveur de stratégie de bande passante dans un format graphique ;</span><span class="sxs-lookup"><span data-stu-id="6f369-507">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>
    
- <span data-ttu-id="6f369-508">enregistrer et stocker la topologie réseau de contrôle d’admission des appels dans un format XML sur le disque ;</span><span class="sxs-lookup"><span data-stu-id="6f369-508">Save and store CAC network topology in an XML format on the disk.</span></span>
    
- <span data-ttu-id="6f369-509">enregistrer et stocker le diagramme de la topologie réseau de contrôle d’admission des appels au format JPG ou BMP ;</span><span class="sxs-lookup"><span data-stu-id="6f369-509">Save and store CAC network topology diagram in JPG or BMP format.</span></span>
    
- <span data-ttu-id="6f369-510">afficher les données de configuration de la topologie réseau de contrôle d’admission des appels ;</span><span class="sxs-lookup"><span data-stu-id="6f369-510">View CAC network topology configuration data.</span></span>
    
- <span data-ttu-id="6f369-511">afficher la topologie réseau de contrôle d’admission des appels dans une arborescence ;</span><span class="sxs-lookup"><span data-stu-id="6f369-511">View CAC network topology in a tree-view style.</span></span>
    
- <span data-ttu-id="6f369-512">définir des connecteurs personnalisés pour les liaisons de la topologie réseau de contrôle d’admission des appels (par exemple, liaisons site-région, région-région et site-site) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-512">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>
    
- <span data-ttu-id="6f369-513">afficher les informations de site, informations de région, stratégies de bande passante et liaisons réseau approvisionnées de la topologie réseau de contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="6f369-513">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>
    
### <a name="purpose"></a><span data-ttu-id="6f369-514">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-514">Purpose</span></span>

<span data-ttu-id="6f369-515">Afficher les liaisons de la topologie réseau de contrôle d’admission des appels dans une interface graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-515">View enterprise CAC network topology links in a graphical interface.</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-516">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-516">Examples</span></span>

 <span data-ttu-id="6f369-517">**Chargement et affichage de topologie de réseau CAC à partir d’un Skype pour le déploiement de Business Server 2015 dans un format graphique**: charger et afficher la configuration de la topologie réseau CAC sur n’importe quel Skype pour ordinateur Business Server 2015 par Skype pour les administrateurs d’entreprise serveur 2015 à l’aide de l’option de **Configuration du téléchargement du réseau** comme indiqué dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-517">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="6f369-518">L’outil ne pourra pas télécharger ou afficher une configuration lors du déploiement sur un ordinateur qui ne dispose pas de connectivité à la Skype pour le magasin de configuration Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-518">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>
  
![Téléchargement de la configuration réseau.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)
  
 <span data-ttu-id="6f369-520">**De charge et vue CAC topologie de réseau à partir d’un fichier de journal de serveur de stratégie de bande passante dans un format graphique :** Skype pour les serveurs de stratégie de bande passante Business Server 2015 enregistrer la topologie du réseau CAC dans le cadre du mécanisme de journalisation sous le Skype pour l’emplacement de partage de fichier Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-520">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="6f369-521">Skype pour les administrateurs d’entreprise serveur 2015 peut afficher ce type de fichier dans un format graphique à l’aide de l’option de **Configuration de réseau ouvert** comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-521">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>
  
![Ouverture d’un fichier journal de serveur de stratégie de bande passante.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)
  
<span data-ttu-id="6f369-523">Enregistrer et stocker la topologie du réseau CAC au format XML sur le disque : Skype pour les administrateurs d’entreprise serveur 2015 peut enregistrer le fichier de configuration de topologie réseau CAC au format XML à l’aide de l’option **Enregistrer une copie de la Configuration réseau** comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-523">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="6f369-524">Le fichier de configuration enregistré peut ensuite être utilisé en mode hors connexion à des fins d’affichage graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-524">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>
  
![Enregistrement de la configuration réseau en tant que fichier XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)
  
<span data-ttu-id="6f369-526">Enregistrer et le diagramme de la topologie réseau CAC du magasin au format JPG ou BMP : Skype pour les administrateurs d’entreprise serveur 2015 peut enregistrer la configuration de topologie de réseau CAC dans un format graphique (formats de fichier JPG et BMP) à l’aide du diagramme de **Enregistrer la Configuration du réseau en tant que image** option comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-526">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>
  
![Enregistrement de la configuration réseau en tant qu’image.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)
  
 <span data-ttu-id="6f369-528">**Aux données de configuration de la topologie de réseau affichage CAC :** Skype pour les administrateurs d’entreprise serveur 2015 peut afficher les données de configuration réseau associés tels que les zones de réseaux, les sites de réseau, les profils de la bande passante et adresses IP de sous-réseau site dans un format textuel à l’aide de l’option Afficher la Configuration réseau de données comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-528">**View CAC network topology configuration data:**Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span> 
  
![Affichage des données de configuration réseau.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)
  
 <span data-ttu-id="6f369-530">**Topologie de réseau de vue CAC dans un style d’affichage de l’arborescence :** Skype pour les administrateurs d’entreprise serveur 2015 peut afficher les données de configuration réseau associés dans un style d’affichage graphique d’arborescence à l’aide du Panneau de commande sur le côté gauche de la fenêtre outil, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-530">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>
  
![Affichage des données de configuration réseau dans une arborescence.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)
  
 <span data-ttu-id="6f369-532">**Définir des connecteurs personnalisés pour CAC réseau topologie des liens (liens de site à site à l’autre et région à l’autre) :** Skype pour les administrateurs d’entreprise serveur 2015 peut définir des connecteurs de graphiques personnalisés pour les liaisons WAN de CAC réseau configuration à l’aide de l’option paramètres comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-532">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="6f369-533">Ceci permet de différencier divers types de liaisons réseau approvisionnées dans la configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="6f369-533">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>
  
![Outils](../media/Reskit_2012_Tools_Documentation_Image29.jpg)
  
 <span data-ttu-id="6f369-535">**Affichage CAC site informations sur la topologie, les informations de région et les stratégies de bande passante mis en service :** Skype pour les administrateurs d’entreprise serveur 2015 peut afficher des informations connexes relatives à la région de réseau CAC, les informations de site et la bande passante CAC mise en service d’informations à l’aide des options ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f369-535">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="6f369-536">(Par exemple, cliquez sur **Infos** dans une région de réseau ou d’un objet de site réseau.)</span><span class="sxs-lookup"><span data-stu-id="6f369-536">(For example, click **Info** in a network region or network site object.)</span></span>
  
![Définition de connecteurs personnalisés pour votre réseau.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)
  
### <a name="summary"></a><span data-ttu-id="6f369-538">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-538">Summary</span></span>

<span data-ttu-id="6f369-539">Cet outil peut être une ressource précieuse pour Skype pour les administrateurs de 2015 de serveur d’entreprise qui souhaite afficher la topologie du réseau CAC pour leur déploiement dans un format graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-539">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>
  
## <a name="response-group-agent-live"></a><span data-ttu-id="6f369-540">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="6f369-540">Response Group Agent Live</span></span>
<span data-ttu-id="6f369-541"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-541"></span></span>

<span data-ttu-id="6f369-542">L’application Response Group permet aux agents d’accéder à des informations utiles en temps réel via son service web intégré.</span><span class="sxs-lookup"><span data-stu-id="6f369-542">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="6f369-543">Aucun affichage graphique de ces données n’est toutefois disponible en dehors de l’application.</span><span class="sxs-lookup"><span data-stu-id="6f369-543">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="6f369-544">L’outil du Kit de ressources Live de réponse groupe Agent résout ce problème en fournissant un moyen simple et graphique pour accéder à ces informations, améliorées avec Skype en temps réel pour les informations de logiciel communications commerciales telles que la présence d’autres agents.</span><span class="sxs-lookup"><span data-stu-id="6f369-544">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-545">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-545">Description</span></span>

<span data-ttu-id="6f369-546">L’application Windows Response Group Agent Live fournit des fonctionnalités de connexion et de déconnexion et donne des informations en temps réel (appartenance aux groupes, nombre actuel d’appels, etc.) aux agents Response Group.</span><span class="sxs-lookup"><span data-stu-id="6f369-546">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="6f369-547">Il est destiné à être une version améliorée de la page groupes d’agents (accessible à partir de Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6f369-547">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="6f369-548">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-548">Purpose</span></span>

<span data-ttu-id="6f369-p161">L’application Response Group place les appels entrants en file d’attente avant de les acheminer vers des groupes d’agents. Pour identifier les appels à traiter de façon appropriée, les agents peuvent accéder à des informations en temps réel sur leurs groupes d’agents (agents disponibles, nombre d’appels en attente dans chaque file d’attente, etc.). Ces informations, à l’origine accessibles via le service Response Group uniquement, sont mises à disposition de façon intuitive par Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="6f369-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>
  
#### <a name="features"></a><span data-ttu-id="6f369-552">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6f369-552">Features</span></span>

<span data-ttu-id="6f369-553">L’outil Live de l’Agent groupe de réponse repose sur le service Response Group et le Skype pour Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="6f369-553">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="6f369-554">Il fournit aux agents Response Group les informations et fonctionnalités disponibles via le service Response Group (appartenance à des groupes, présence des autres agents, nombre d’appels en attente, etc.).</span><span class="sxs-lookup"><span data-stu-id="6f369-554">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>
  
<span data-ttu-id="6f369-555">La figure suivante illustre l’interface principale de Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="6f369-555">The figure below illustrates the main interface of Response Group Agent Live.</span></span>
  
![L’outil Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)
  
<span data-ttu-id="6f369-557">Les trois fonctionnalités principales suivantes sont accessibles aux agents dans Response Group Agent Live :</span><span class="sxs-lookup"><span data-stu-id="6f369-557">The following three main features are available for agents in Response Group Agent Live:</span></span>
  
- <span data-ttu-id="6f369-558">**Sign-in/out :** Contrairement à la page groupes d’agents (accessible via Skype pour Business Server 2015), Live de l’Agent groupe de réponse permet aux agents uniquement à la connexion ou agent de tous les groupes à la fois.</span><span class="sxs-lookup"><span data-stu-id="6f369-558">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="6f369-559">Cette application propose trois méthodes rapides pour les agents signer ou arrière :</span><span class="sxs-lookup"><span data-stu-id="6f369-559">This application provides three quick ways for agents to sign in or out:</span></span>
    
  - <span data-ttu-id="6f369-560">Cliquer sur les boutons Sign-in/out (Connexion/Déconnexion) (vert et rouge) dans l’application.</span><span class="sxs-lookup"><span data-stu-id="6f369-560">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
  - <span data-ttu-id="6f369-561">Cliquer avec le bouton droit sur la barre d’état système, et sélectionner Sign in (Connexion) ou Sign out (Déconnexion).</span><span class="sxs-lookup"><span data-stu-id="6f369-561">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
  - <span data-ttu-id="6f369-562">Utiliser des raccourcis clavier configurables.</span><span class="sxs-lookup"><span data-stu-id="6f369-562">Using configurable keyboard shortcuts.</span></span>
    
- <span data-ttu-id="6f369-563">**Groupe d’appartenance :** Lorsqu’un groupe d’agent est sélectionné, la réponse groupe Agent Live affiche la liste des agents de ce groupe dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="6f369-563">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="6f369-564">Si Skype pour Business Server 2015 est en cours d’exécution sur le même ordinateur que cette application, les informations de présence et de la fiche contact sont affichent dans la vie d’Agent de groupe de la réponse.</span><span class="sxs-lookup"><span data-stu-id="6f369-564">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="6f369-565">Les agents peuvent envoyer un message instantané ou appeler d’autres agents directement à partir de là.</span><span class="sxs-lookup"><span data-stu-id="6f369-565">Agents can send an IM or call other agents directly from there.</span></span>
    
- <span data-ttu-id="6f369-p165">**Statistiques en temps réel :** Response Group Agent Live fournit des statistiques en temps réel pour tous les groupes d’agents. La fréquence de mise à jour est d’une minute. Lorsqu’un Response Group répond à un appel, un indicateur visuel est ajouté près du nom du groupe et le nombre actuel d’appels placés en file d’attente est indiqué. Pour afficher le délai d’attente le plus long, il suffit de placer le pointeur de la souris sur un groupe.</span><span class="sxs-lookup"><span data-stu-id="6f369-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="6f369-570">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-570">Requirements</span></span>

<span data-ttu-id="6f369-571">Response Group Agent Live nécessite .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="6f369-571">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="6f369-572">En outre, pour tirer parti des fonctionnalités de fiche de présence et de contact, Skype pour Business doit être installé localement (et en cours d’exécution).</span><span class="sxs-lookup"><span data-stu-id="6f369-572">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>
  
#### <a name="configuration"></a><span data-ttu-id="6f369-573">Configuration</span><span class="sxs-lookup"><span data-stu-id="6f369-573">Configuration</span></span>

<span data-ttu-id="6f369-p167">Response Group Agent Live peut être personnalisé selon les préférences individuelles via la boîte de dialogue Options de l’application. L’administrateur peut également définir l’adresse de l’hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="6f369-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>
  
<span data-ttu-id="6f369-p168">La figure suivante illustre la boîte de dialogue Options qui permet aux agents de configurer l’adresse de l’hôte et les raccourcis clavier. Pour accéder à cette boîte de dialogue, il suffit de cliquer sur le bouton Options dans la partie supérieure droite de l’interface principale.</span><span class="sxs-lookup"><span data-stu-id="6f369-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>
  
![La boîte de dialogue Options de l’outil Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)
  
<span data-ttu-id="6f369-579">Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group Agent Live :</span><span class="sxs-lookup"><span data-stu-id="6f369-579">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>
  
- <span data-ttu-id="6f369-580">Adresse d’hôte : il s’agit généralement du web pool FQDN appartenant au pool de domicile de l’agent.</span><span class="sxs-lookup"><span data-stu-id="6f369-580">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="6f369-581">L’adresse exacte du service Response Group est dérivée automatiquement en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès correct après l’hôte).</span><span class="sxs-lookup"><span data-stu-id="6f369-581">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>
    
- <span data-ttu-id="6f369-582">Shortcuts (Raccourcis) : les raccourcis exacts pour la connexion/déconnexion peuvent être personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6f369-582">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="6f369-583">La seule limitation est que les deux raccourcis doivent contenir la clé « Windows Logo » (en plus d’au moins une autre clé).</span><span class="sxs-lookup"><span data-stu-id="6f369-583">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>
    
- <span data-ttu-id="6f369-584">Start with Windows (Démarrer avec Windows) : l’application peut être configurée pour démarrer automatiquement avec Windows.</span><span class="sxs-lookup"><span data-stu-id="6f369-584">Start with Windows: The application can be configured to start automatically with Windows.</span></span>
    
### <a name="examples"></a><span data-ttu-id="6f369-585">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-585">Examples</span></span>

<span data-ttu-id="6f369-586">La figure suivante illustre l’appel d’un autre agent ou l’envoi d’un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="6f369-586">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>
  
![Effectuer un appel ou envoyer un message instantané.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)
  
<span data-ttu-id="6f369-588">La figure suivante illustre l’affichage par Response Group Agent Live du nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="6f369-588">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>
  
![Affichage des informations sur la file d’attente.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)
  
### <a name="summary"></a><span data-ttu-id="6f369-590">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-590">Summary</span></span>

<span data-ttu-id="6f369-591">Les connexion et déconnexion rapides, l’appartenance aux groupes et les statistiques de base en temps réel constituent des fonctionnalités intéressantes de Response Group Agent seulement disponibles en dehors de l’application à partir du service Response Group.</span><span class="sxs-lookup"><span data-stu-id="6f369-591">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="6f369-592">Avec l’outil Kit de ressources Live de réponse groupe Agent, Skype pour les administrateurs d’entreprise serveur 2015 permettent à leurs agents avec une application Windows qui leur permet d’effectuer des tâches de manière plus rapide et graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-592">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>
  
## <a name="sefautil"></a><span data-ttu-id="6f369-593">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6f369-593">SEFAUtil</span></span>
<span data-ttu-id="6f369-594"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-594"></span></span>

<span data-ttu-id="6f369-595">SEFAUtil (activation de la fonctionnalité extension secondaire) est un outil de ligne de commande qui permet de Skype pour les administrateurs de logiciel des communications Business Server 2015 et les agents du support technique configurer l’appel de délégué, transfert d’appel, simultanées sonne, paramètres de l’appel à l’équipe et de groupe de prise d’appel au nom d’un Skype pour l’utilisateur de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-595">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="6f369-596">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels qui sont publiées pour un utilisateur particulier. L’outil SEFAUtil permet à l’administrateur pour activer/désactiver/modifier des appels de transfert ou une sonnerie simultanément au nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-596">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="6f369-597">L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible qui a déjà été publiée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-597">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="6f369-598">Cet outil permet également aux administrateurs d’ajouter ou supprimer des délégués de-appel d’équipe les membres du groupe pour le compte de l’utilisateur. Cet outil repose sur Microsoft Unified Communications Managed API (UCMA) 3.0 et demande aux administrateurs de créer une application de confiance dans le magasin Central de gestion de SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="6f369-598">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>
  
<span data-ttu-id="6f369-599">SEFAUtil (activation de la fonctionnalité extension secondaire) permet de Skype pour les administrateurs d’entreprise serveur 2015 et les agents du support technique configurer l’appel de délégué, transfert d’appel, simultanées sonnerie, appel d’équipe paramètres et groupe de prise d’appel au nom d’un Skype pour l’utilisateur de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-599">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="6f369-600">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="6f369-600">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-601">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-601">Description</span></span>

<span data-ttu-id="6f369-602">La version actuelle de SEFAUtil n’est qu’un outil en ligne de commande, sans interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="6f369-602">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="6f369-603">Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="6f369-603">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="6f369-604">Ses fonctionnalités permettent aux administrateurs et agents du support technique d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-604">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>
  
- <span data-ttu-id="6f369-605">afficher les paramètres de routage des appels d’un utilisateur (transfert d’appel, délégation, sonnerie simultanée, appel d’équipe et prise d’appel de groupe inclus) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-605">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>
    
- <span data-ttu-id="6f369-606">activer/désactiver/modifier les paramètres de transfert d’appel (destination et minuteur d’absence de réponse inclus) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-606">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>
    
- <span data-ttu-id="6f369-607">activer/désactiver/modifier les configurations immédiates de transfert d’appel ;</span><span class="sxs-lookup"><span data-stu-id="6f369-607">Enable/disable/modify call-forwarding immediate configurations</span></span>
    
- <span data-ttu-id="6f369-608">activer/désactiver/modifier les paramètres de délégation ;</span><span class="sxs-lookup"><span data-stu-id="6f369-608">Enable/disable/modify delegation settings</span></span>
    
- <span data-ttu-id="6f369-609">activer/désactiver/modifier les paramètres d’appel d’équipe ;</span><span class="sxs-lookup"><span data-stu-id="6f369-609">Enable/disable/modify team-call group settings</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f369-610">Nouveau dans Skype pour outil de Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6f369-610">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
- <span data-ttu-id="6f369-611">activer/désactiver/modifier les paramètres de sonnerie simultanée (destination incluse) ;</span><span class="sxs-lookup"><span data-stu-id="6f369-611">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f369-612">Nouveau dans Skype pour outil de Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6f369-612">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
- <span data-ttu-id="6f369-613">activer/désactiver/modifier les paramètres de prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="6f369-613">Enable/disable/modify group call pickup settings</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="6f369-614">Nouveau dans Skype pour outil de Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6f369-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
<span data-ttu-id="6f369-615">Cet outil présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-615">This tool has the following limitations:</span></span>
  
- <span data-ttu-id="6f369-616">Prise en charge uniquement pour les utilisateurs qui sont hébergés dans un Skype pour un pool de serveurs d’entreprise</span><span class="sxs-lookup"><span data-stu-id="6f369-616">Supported only for users homed in a Skype for Business Server pool</span></span>
    
- <span data-ttu-id="6f369-617">modification en bloc des paramètres de routage des appels de plusieurs utilisateurs non prise en charge.</span><span class="sxs-lookup"><span data-stu-id="6f369-617">Bulk-edit of call routing settings for several users is not supported</span></span>
    
### <a name="output"></a><span data-ttu-id="6f369-618">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-618">Output</span></span>

<span data-ttu-id="6f369-p175">La version actuelle de cet outil génère une sortie dans la fenêtre d’invite de commandes uniquement. Pour plus d’informations, voir la section Exemples plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="6f369-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="6f369-621">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-621">Purpose</span></span>

<span data-ttu-id="6f369-622">Voici certains des principaux scénarios d’utilisation de cet outil :</span><span class="sxs-lookup"><span data-stu-id="6f369-622">Following are some of the key scenarios where this tool may be used:</span></span>
  
- <span data-ttu-id="6f369-623">Bob est un dirigeant et a été déplacé à Skype pour la téléphonie Business Server.</span><span class="sxs-lookup"><span data-stu-id="6f369-623">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="6f369-624">Il dispose d’une délégation sur son système PBX existant.</span><span class="sxs-lookup"><span data-stu-id="6f369-624">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="6f369-625">Dans le cadre du déplacement à Skype pour Business Server 2015, l’administrateur peut configurer le routage de Bob pour refléter sa configuration préexistante de la délégation.</span><span class="sxs-lookup"><span data-stu-id="6f369-625">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>
    
- <span data-ttu-id="6f369-p177">En plein déplacement, Alice réalise qu’elle attend un appel important d’un de ses clients. Elle se trouve toutefois à l’hôtel et n’a accès à aucun ordinateur. Elle contacte le support technique pour leur demander de transférer vers son numéro de téléphone portable tous les appels reçus sur son numéro de téléphone professionnel. Les membres du personnel du support technique peuvent effectuer cette opération de configuration pour elle.</span><span class="sxs-lookup"><span data-stu-id="6f369-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>
    
- <span data-ttu-id="6f369-630">Appels de Joe à son nombre de travail vont à sa messagerie vocale mobile chaque fois qu’il est au travail ; Cependant, les choses semblent fonctionner correctement dans la plupart des autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="6f369-630">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="6f369-631">Le technicien du support technique est en mesure d’afficher la configuration du routage de Joe et découvre que Joe a la sonnerie simultanée configuré à son téléphone portable.</span><span class="sxs-lookup"><span data-stu-id="6f369-631">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="6f369-632">Le technicien vous demande de Joe sur la couverture mobile à son bureau et est en mesure de déterminer que la règle de sonnerie simultanée est ce qui provoque les appels accéder à la messagerie vocale mobile de Joe lorsque sa couverture réseau est mauvaise.</span><span class="sxs-lookup"><span data-stu-id="6f369-632">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>
    
- <span data-ttu-id="6f369-633">Mike est un nouvel employé de Contoso et il rejoint une nouvelle équipe sur lequel tous les membres sont configurés pour l’appel de l’équipe, lors de l’activation de Skype pour Business Server 2015, l’administrateur est en mesure de définir des paramètres de groupe pour inclure tous les membres de son équipe nouveau son appel d’équipe , en outre, l’administrateur ajoute Mike comme un membre du groupe équipe-appel pour chacun des membres de son équipe.</span><span class="sxs-lookup"><span data-stu-id="6f369-633">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>
    
- <span data-ttu-id="6f369-634">Une pratique du service client dépendant du service Ressources humaines de Contoso consiste à offrir un service personnel à tous les appelants dès le premier appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-634">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="6f369-635">Tous les membres du service étant assis à proximité les uns des autres, la sonnerie de tous les téléphones en même temps en raison de l’activation de l’appel d’équipe est très perturbant pour le personnel.</span><span class="sxs-lookup"><span data-stu-id="6f369-635">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="6f369-636">Pour offrir le meilleur service sans perturber les membres de l’équipe, le Skype pour l’administrateur d’entreprise serveur 2015 tire parti de la fonctionnalité de prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="6f369-636">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="6f369-637">Il ajoute tous les membres du service à un groupe de prise d’appel et communique le numéro de ce groupe au service.</span><span class="sxs-lookup"><span data-stu-id="6f369-637">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="6f369-638">Pierre remarque que le téléphone de Samira sonne, alors que celle-ci s’est absentée, et prend donc l’appel à partir de son propre bureau.</span><span class="sxs-lookup"><span data-stu-id="6f369-638">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="6f369-639">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-639">Requirements</span></span>

<span data-ttu-id="6f369-p180">L’outil SEFAUtil peut seulement être exécuté sur un ordinateur faisant partie d’un pool d’applications approuvées. UCMA 3.0 doit être installé sur cet ordinateur. Pour exécuter l’outil, une application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>
  
### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="6f369-643">Création d’une application approuvée pour l’outil SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="6f369-643">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="6f369-644">L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="6f369-644">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="6f369-645">Si nécessaire, ajoutez un pool sous la forme d’un pool d’applications de confiance peut être effectué via le Skype pour Business Server Management Shell avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f369-645">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>
    
  ```
  New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
  ```

    > [!NOTE]
    > <span data-ttu-id="6f369-646">UCMA 3.0 doit être installé sur les ordinateurs qui seront utilisés pour exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="6f369-646">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span> 
  
2. <span data-ttu-id="6f369-647">Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="6f369-647">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="6f369-648">Pour définir SEFAUtil comme une application approuvée, utilisez le Skype pour Business Server Management Shell et d’exécuter l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f369-648">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span> 
    
  ```
  New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
  ```

    > [!NOTE]
    > <span data-ttu-id="6f369-649">Un autre port peut être utilisé au besoin.</span><span class="sxs-lookup"><span data-stu-id="6f369-649">A different port can be used if needed.</span></span> 
  
3. <span data-ttu-id="6f369-650">Les modifications apportées à la topologie doivent être activées.</span><span class="sxs-lookup"><span data-stu-id="6f369-650">The topology changes need to be enabled.</span></span> <span data-ttu-id="6f369-651">L’activation de la modification de la topologie est possible via le Skype pour Business Server Management Shell par l’exécution de l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f369-651">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span> 
    
  ```
  Enable-CsToplogy
  ```

4. <span data-ttu-id="6f369-652">Si nécessaire, installez le Skype pour Business Server 2015 Resource Kit Tools sur le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit être la partie d’un pool d’applications de confiance).</span><span class="sxs-lookup"><span data-stu-id="6f369-652">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>
    
5. <span data-ttu-id="6f369-653">Vérifiez que SEFAUtil est correctement exécuté.</span><span class="sxs-lookup"><span data-stu-id="6f369-653">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="6f369-654">Pour ce faire, exécutez l’outil à partir d’une invite de commandes de Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="6f369-654">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="6f369-655">Par défaut, l’outil va se trouver dans : « ...\Program Files\Skype pour Business Server 2015\Reskit ».</span><span class="sxs-lookup"><span data-stu-id="6f369-655">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="6f369-656">Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f369-656">To display the call forwarding settings of a user, use the following command:</span></span> 
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
  ```

    <span data-ttu-id="6f369-657">Les paramètres de transfert d’appel de l’utilisateur doivent s’afficher.</span><span class="sxs-lookup"><span data-stu-id="6f369-657">The call forwarding settings of the user should be displayed.</span></span>
    
#### <a name="group-call-pickup"></a><span data-ttu-id="6f369-658">Prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="6f369-658">Group Call Pickup</span></span>

<span data-ttu-id="6f369-659">Collecte d’appeler groupe nécessite une configuration supplémentaire dans Skype pour 2015 de serveur Business pour la capacité à être totalement activée.</span><span class="sxs-lookup"><span data-stu-id="6f369-659">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="6f369-660">Avant d’affecter les groupes de prise d’appels aux utilisateurs, consultez la documentation sur la prise d’appel de groupe pour connaître les étapes de planification et de déploiement de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6f369-660">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-661">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-661">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="6f369-662">Afficher les paramètres actuels de gestion des appels</span><span class="sxs-lookup"><span data-stu-id="6f369-662">Display Current Call Handling Settings</span></span>

<span data-ttu-id="6f369-663">La commande suivante affiche le traitement des appels pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-663">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`
  
> [!NOTE]
> <span data-ttu-id="6f369-664">Cet exemple utilise le commutateur **/server** pour spécifier le Skype pour Business Server pour se connecter à.</span><span class="sxs-lookup"><span data-stu-id="6f369-664">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>
  
 <span data-ttu-id="6f369-665">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-665">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="6f369-666">Définir la destination du transfert d’appel/en cas d’absence de réponse</span><span class="sxs-lookup"><span data-stu-id="6f369-666">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="6f369-667">Cet exemple définit la destination de transfert/aucune réponse d’appel et le délai de l’anneau.</span><span class="sxs-lookup"><span data-stu-id="6f369-667">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="6f369-668">Ici, le commutateur/Server n’est pas fourni ; SEFAUtil essaie de découverte automatique la Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-668">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="6f369-669">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-669">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="6f369-670">Activer le transfert d’appel immédiatement</span><span class="sxs-lookup"><span data-stu-id="6f369-670">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="6f369-671">Cet exemple active immédiatement le transfert d’appel vers un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-671">This example immediately enables call-forwarding to another user.</span></span>
  
```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="6f369-672">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-672">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="6f369-673">Désactiver immédiatement le transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="6f369-673">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="6f369-674">Cet exemple désactivé immédiatement le transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="6f369-674">This example immediately disables call forwarding.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="6f369-675">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-675">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="6f369-676">Ajouter un utilisateur en tant que délégué et définir la sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="6f369-676">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="6f369-677">Cet exemple ajoute un utilisateur en tant que délégué et définit la sonnerie simultanée des délégués.</span><span class="sxs-lookup"><span data-stu-id="6f369-677">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="6f369-678">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-678">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="6f369-679">Modifier la règle de sonnerie simultanée des délégués</span><span class="sxs-lookup"><span data-stu-id="6f369-679">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="6f369-680">Cet exemple modifie la règle de sonnerie simultanée définie dans l’exemple précédent en règle de sonnerie différée.</span><span class="sxs-lookup"><span data-stu-id="6f369-680">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="6f369-681">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-681">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="6f369-682">Supprimer le délégué</span><span class="sxs-lookup"><span data-stu-id="6f369-682">Remove the Delegate</span></span>

<span data-ttu-id="6f369-683">Cet exemple supprime le délégué.</span><span class="sxs-lookup"><span data-stu-id="6f369-683">This example removes the delegate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f369-684">Une fois le dernier délégué supprimé, la sonnerie sur le poste de délégués est désactivée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6f369-684">When the last delegate is removed, delegate ringing is automatically disabled.</span></span> 
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="6f369-685">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-685">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="6f369-686">Ajouter un délégué et définir la règle de transfert d’appel aux délégués</span><span class="sxs-lookup"><span data-stu-id="6f369-686">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="6f369-687">Cet exemple ajoute un délégué et définit la règle de transfert d’appel aux délégués.</span><span class="sxs-lookup"><span data-stu-id="6f369-687">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="6f369-688">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-688">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="6f369-689">Activer la sonnerie simultanée et définir un numéro de destination</span><span class="sxs-lookup"><span data-stu-id="6f369-689">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="6f369-690">Cet exemple active la sonnerie simultanée et définit un numéro de destination pour la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="6f369-690">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="6f369-691">Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur /enablesimulring, sans quoi le numéro de destination ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="6f369-691">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span> 
  
 <span data-ttu-id="6f369-692">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-692">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="6f369-693">Désactiver la sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="6f369-693">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="6f369-694">Cet exemple désactive la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="6f369-694">This example disables simultaneous ringing.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="6f369-695">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-695">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="6f369-696">Ajouter un membre d’équipe pour l’appel d’équipe et définir la sonnerie simultanée sur le groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="6f369-696">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="6f369-697">Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée sur le groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6f369-697">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="6f369-698">L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur définit automatiquement les paramètres de sonnerie simultanée des utilisateurs sur la sonnerie simultanée de son groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6f369-698">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span> 
  
 <span data-ttu-id="6f369-699">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-699">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="6f369-700">Supprimer un membre du groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="6f369-700">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="6f369-701">Cet exemple supprime un membre d’équipe du groupe d’appel d’équipe d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-701">This example removes a team member of the team-call group of a user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="6f369-702">Si le membre supprimé est le seul du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.</span><span class="sxs-lookup"><span data-stu-id="6f369-702">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span> 
  
 <span data-ttu-id="6f369-703">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-703">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="6f369-704">Définir la sonnerie différée sur le groupe d’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="6f369-704">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="6f369-705">Cet exemple définit la sonnerie différée sur le paramètre d’heure du groupe d’appel d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6f369-705">This example changes the delayed ring to the team-call group time setting.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="6f369-706">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-706">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="6f369-707">Activer l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="6f369-707">Enable Team-Call</span></span>

<span data-ttu-id="6f369-708">Cet exemple active l’appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="6f369-708">This example enables team-call for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="6f369-709">Si le groupe d’appel à l’équipe de l’utilisateur ne possède aucun membre, appel d’équipe ne sont pas activé.</span><span class="sxs-lookup"><span data-stu-id="6f369-709">If the team-call group of the user has no members, team-call won't be enabled.</span></span> 
  
 <span data-ttu-id="6f369-710">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-710">**Output**</span></span>
  
#### <a name="disable-team-call"></a><span data-ttu-id="6f369-711">Désactiver l’appel d’équipe</span><span class="sxs-lookup"><span data-stu-id="6f369-711">Disable Team-Call</span></span>

<span data-ttu-id="6f369-712">Cet exemple désactive l’appel d’équipe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="6f369-712">This example disables team-call for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="6f369-713">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-713">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="6f369-714">Activer la prise d’appel de groupe et affecter un groupe de prise d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6f369-714">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="6f369-715">Cet exemple affecte un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="6f369-715">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="6f369-716">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="6f369-716">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="6f369-717">Désactiver la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="6f369-717">Disable Group Call Pickup</span></span>

<span data-ttu-id="6f369-718">Cet exemple désactive la prise d’appel de groupe pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="6f369-718">This example disables Group Call Pickup for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="6f369-p187">Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe affecté à cet utilisateur n’est pas conservé. Si vous souhaitez ultérieurement réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="6f369-p187">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span> 
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="6f369-721">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="6f369-721">SYSPrep.ps1</span></span>
<span data-ttu-id="6f369-722"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-722"></span></span>

### <a name="description"></a><span data-ttu-id="6f369-723">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-723">Description</span></span>

<span data-ttu-id="6f369-724">SYSPrep.ps1 est un script Windows PowerShell qui installera le Skype suivante pour les composants requis de Business Server 2015 sur votre machine du système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="6f369-724">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>
  
- <span data-ttu-id="6f369-725">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6f369-725">Microsoft .Net Framework 4.5</span></span>
    
- <span data-ttu-id="6f369-726">Microsoft SQL Server Express ;</span><span class="sxs-lookup"><span data-stu-id="6f369-726">Microsoft SQL Server Express</span></span>
    
- <span data-ttu-id="6f369-727">Windows Powershell version 3.0</span><span class="sxs-lookup"><span data-stu-id="6f369-727">Windows Powershell version 3.0</span></span>
    
- <span data-ttu-id="6f369-728">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="6f369-728">Visual C++ 2010 Redistributable</span></span>
    
- <span data-ttu-id="6f369-729">Mises à jour d’Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="6f369-729">Internet Information Server Updates</span></span>
    
- <span data-ttu-id="6f369-730">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="6f369-730">Windows Identity Foundation</span></span>
    
- <span data-ttu-id="6f369-731">Skype pour les fichiers de l’entreprise, Server Core 2015</span><span class="sxs-lookup"><span data-stu-id="6f369-731">Skype for Business Server 2015 Core files</span></span>
    
 <span data-ttu-id="6f369-732">Si le nom du script est semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont toutefois différents.</span><span class="sxs-lookup"><span data-stu-id="6f369-732">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="6f369-733">Ce script installe uniquement les composants requis pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-733">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="6f369-734">Une fois ceux-ci installés, l’outil Windows SYSPrep peut ensuite être utilisé pour créer une image du serveur.</span><span class="sxs-lookup"><span data-stu-id="6f369-734">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="6f369-735">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-735">Requirements</span></span>

<span data-ttu-id="6f369-736">Avant d’exécuter le script SYSPrep.ps1, vous devez copier les fichiers requis dans un dossier local sur l’ordinateur du système d’exploitation Windows Server 2008 (par exemple **D:\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="6f369-736">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="6f369-737">Ce dossier doit également inclure une copie de la Skype pour les fichiers de Business Server 2015, en particulier **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="6f369-737">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="6f369-738">Les fichiers des logiciels prérequis peuvent être téléchargés aux emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-738">The prerequisite files can be downloaded from the following locations:</span></span>
  
|<span data-ttu-id="6f369-739">**Condition préalable**</span><span class="sxs-lookup"><span data-stu-id="6f369-739">**Prerequisite**</span></span>|<span data-ttu-id="6f369-740">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="6f369-740">**Location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6f369-741">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6f369-741">Microsoft .Net Framework 4.5</span></span>  <br/> |http://go.microsoft.com/?linkid=9816306  <br/> |
|<span data-ttu-id="6f369-742">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6f369-742">Microsoft SQL Server Express 2008 R2</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=23650  <br/> |
|<span data-ttu-id="6f369-743">Windows Powershell version 3.0</span><span class="sxs-lookup"><span data-stu-id="6f369-743">Windows Powershell version 3.0</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34595  <br/> |
|<span data-ttu-id="6f369-744">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="6f369-744">Visual C++ 2010 Redistributable</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=5555  <br/> |
|<span data-ttu-id="6f369-745">Mises à jour d’Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="6f369-745">Internet Information Server Updates</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34869  <br/> |
|<span data-ttu-id="6f369-746">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="6f369-746">Windows Identity Foundation</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=17331  <br/> |
|<span data-ttu-id="6f369-747">Skype pour Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="6f369-747">Skype for Business Server 2015 Setup.exe</span></span>  <br/> |<span data-ttu-id="6f369-748">Copie de Skype Business Server 2015 media</span><span class="sxs-lookup"><span data-stu-id="6f369-748">Copy from Skype for Business Server 2015 media</span></span>  <br/> |
   
### <a name="parameter"></a><span data-ttu-id="6f369-749">Paramètre</span><span class="sxs-lookup"><span data-stu-id="6f369-749">Parameter</span></span>

<span data-ttu-id="6f369-750">Le paramètre **- SetupFolder** accepte comme argument l’emplacement du répertoire des fichiers requis</span><span class="sxs-lookup"><span data-stu-id="6f369-750">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-751">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-751">Examples</span></span>

<span data-ttu-id="6f369-752">Pour exécuter le script SYSPrep.ps1 et installez le Skype pour les composants requis de Business Server 2015, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :</span><span class="sxs-lookup"><span data-stu-id="6f369-752">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>
  
```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="6f369-753">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="6f369-753">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="6f369-754"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-754"></span></span>

<span data-ttu-id="6f369-755">L’outil de Migration d’annonces numéro non affecté permet un Skype pour administrateur Business Server 2015 déplacer la configuration de numéros non attribués est pris en charge par l’application d’annonce à partir d’une source de Skype à Business Server ou un Pool à un destination Skype pour Business Server ou le Pool.</span><span class="sxs-lookup"><span data-stu-id="6f369-755">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-756">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-756">Description</span></span>

<span data-ttu-id="6f369-757">L’outil Unassigned Number Announcements Migration est un script Windows PowerShell qui déplace la configuration des numéros non attribués pris en charge par l’application d’annonce entre un pool ou un serveur source et un autre pool ou serveur.</span><span class="sxs-lookup"><span data-stu-id="6f369-757">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>
  
<span data-ttu-id="6f369-758">Lorsqu’il est exécuté, le script Unassigned Number Announcements Migration effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-758">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>
  
1. <span data-ttu-id="6f369-759">Déplacer tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée sur le pool ou serveur source vers le magasin de fichiers du pool ou serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="6f369-759">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f369-760">Les fichiers audio sont supprimés de la liste source une fois qu’ils sont copiés vers le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="6f369-760">The audio files are removed from the source pool once they're copied to the destination pool.</span></span> 
  
2. <span data-ttu-id="6f369-761">Déplacer les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="6f369-761">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>
    
3. <span data-ttu-id="6f369-762">Réaffecter toutes les plages de numéros non attribués prises en charge par l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="6f369-762">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>
    
<span data-ttu-id="6f369-763">Une fois le script correctement exécuté, toutes les plages de numéros affectés prises en charge par l’application d’annonce hébergée dans le pool ou serveur source sont à présent prises en charge avec la même configuration par le pool ou le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="6f369-763">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>
  
### <a name="output"></a><span data-ttu-id="6f369-764">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-764">Output</span></span>

<span data-ttu-id="6f369-765">Le script de **Déplacement-CsAnnouncementConfiguration** indique la Skype pour fenêtre Business Server Management Shell à partir de l’endroit où il a exécuté la réussite ou l’échec de l’opération de migration.</span><span class="sxs-lookup"><span data-stu-id="6f369-765">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>
  
<span data-ttu-id="6f369-p190">Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués correctement déplacées vers la destination sont conservées dans la destination sous une forme opérationnelle et le reste des plages de numéros non attribués à migrer sont conservés dans la source sous une forme opérationnelle également. Pour migrer entièrement le reste de la configuration, exécutez à nouveau le script après avoir traité l’erreur.</span><span class="sxs-lookup"><span data-stu-id="6f369-p190">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="6f369-768">Objectif</span><span class="sxs-lookup"><span data-stu-id="6f369-768">Purpose</span></span>

<span data-ttu-id="6f369-769">Le script Unassigned Number Announcements Migration peut être utilisé dans le cadre des scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="6f369-769">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>
  
- <span data-ttu-id="6f369-770">**Paramètres de configuration de migration vers une nouvelle version de Skype pour Business Server :** Contoso est en cours de migration vers Skype pour Business Server 2015 et dans le cadre du processus de migration du Skype pour Business Server administrateur souhaite déplacer la configuration de numéros non attribués pris en charge par l’application de l’annonce de la Lync Déploiement de serveur 2013 pour le nouveau Skype pour le déploiement de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-770">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="6f369-771">Pour déplacer les paramètres de configuration, le Skype pour administrateur Business Server utilise l’outil de Migration d’annonces numéro non affecté.</span><span class="sxs-lookup"><span data-stu-id="6f369-771">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>
    
- <span data-ttu-id="6f369-772">**Restauration d’un déploiement de Skype pour Business Server 2015 à Lync Server 2013 :** Échéance de facteurs inattendus, Contoso doit restaurer la migration vers le nouveau Skype pour le déploiement de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f369-772">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="6f369-773">Pour minimiser les interruptions de service pour le service, le Skype pour administrateur Business Server utilise l’outil de Migration d’annonces numéro non affecté pour restaurer la configuration à partir de la Skype pour le déploiement de Business Server 2015 pour le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f369-773">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>
    
- <span data-ttu-id="6f369-774">**Déplacement de données entre les déploiements :** Contoso est en cours de remplacement de tous les serveurs d’un pool avec des serveurs plus récents.</span><span class="sxs-lookup"><span data-stu-id="6f369-774">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="6f369-775">Leur stratégie consiste à déployer un nouveau Skype pour le pool d’entreprise serveur 2015, de déplacer toutes les données de l’ancien vers le nouveau pool, puis Déconseiller le pool ancien.</span><span class="sxs-lookup"><span data-stu-id="6f369-775">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="6f369-776">Une fois le nouveau pool déployé, l’outil Unassigned Number Announcements Migration est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.</span><span class="sxs-lookup"><span data-stu-id="6f369-776">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>
    
#### <a name="requirements"></a><span data-ttu-id="6f369-777">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-777">Requirements</span></span>

<span data-ttu-id="6f369-778">Les principaux éléments de configuration suivants sont requis pour exécuter correctement l’outil :</span><span class="sxs-lookup"><span data-stu-id="6f369-778">The following are the main requirements needed to successfully run the tool:</span></span>
  
1. <span data-ttu-id="6f369-779">Le script doit être exécuté à partir d’un ordinateur a Skype pour Business Server Management Shell est installé.</span><span class="sxs-lookup"><span data-stu-id="6f369-779">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>
    
2. <span data-ttu-id="6f369-780">L’application de l’annonce doit être déployé avec succès dans la source et la destination Skype pour les serveurs de l’entreprise ou des grappes.</span><span class="sxs-lookup"><span data-stu-id="6f369-780">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>
    
#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="6f369-781">Script Move-CsAnnouncementConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6f369-781">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="6f369-782">Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau suivant. </span><span class="sxs-lookup"><span data-stu-id="6f369-782">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span> 
  
![Paramètres Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)
  
### <a name="examples"></a><span data-ttu-id="6f369-784">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-784">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="6f369-785">Déplacement de la Configuration des numéros d’annonces non affecté du pool Lync Server 2013 pour un Skype pour Business Server 2015 Pool</span><span class="sxs-lookup"><span data-stu-id="6f369-785">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="6f369-786">Cet exemple déplace les annonces de numéros non attribués à partir du pool de source (Lync Server 2013) vers le pool de destination (Skype pour Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="6f369-786">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>
  
```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com

```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="6f369-787">Déplacement de la Configuration des numéros d’annonces non affecté à partir d’un Skype pour Business Server 2015 Pool à un Pool de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f369-787">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="6f369-788">Cet exemple déplace les annonces de numéros non attribués à partir du pool de source (Skype pour Business Server 2015) vers le pool de destination (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="6f369-788">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>
  
```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="6f369-789">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="6f369-789">Web Conf Data</span></span>
<span data-ttu-id="6f369-790"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="6f369-790"></span></span>

<span data-ttu-id="6f369-791">L’outil de données Conf Web permet à un administrateur de Skype pour le logiciel de communication Business Server 2015 d’avoir davantage de contrôle sur les données associées aux conférences Web d’un organisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-791">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="6f369-792">Les scénarios incluent la possibilité de supprimer des données de réunion d’un utilisateur spécifique selon un critère de cachet de temps.</span><span class="sxs-lookup"><span data-stu-id="6f369-792">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>
  
### <a name="description"></a><span data-ttu-id="6f369-793">Description</span><span class="sxs-lookup"><span data-stu-id="6f369-793">Description</span></span>

<span data-ttu-id="6f369-794">Cet outil permet aux administrateurs d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f369-794">This tool allows the administrator to perform the following operations:</span></span>
  
1. <span data-ttu-id="6f369-795">Rechercher les données de conférence web associées à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-795">Find all Web conferencing data associated with a single user.</span></span>
    
2. <span data-ttu-id="6f369-796">Supprimer les données de conférence web associées à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-796">Delete all Web conferencing data associated with a single user.</span></span>
    
3. <span data-ttu-id="6f369-797">Supprimer les données de conférence web associées à un utilisateur antérieures à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="6f369-797">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>
    
4. <span data-ttu-id="6f369-798">Déplacer les données de conférence web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="6f369-798">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6f369-799">Les outils du Kit de ressources pour Lync Server 2010 pris en charge le déplacement de toutes les données de conférence Web associées à un seul utilisateur lorsque cet utilisateur est déplacé d’un pool à un autre.</span><span class="sxs-lookup"><span data-stu-id="6f369-799">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="6f369-800">Cette fonctionnalité a été supprimée de cet outil et remplacée par le paramètre  **MoveConferenceData**.</span><span class="sxs-lookup"><span data-stu-id="6f369-800">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="6f369-801">Pour plus d’informations sur ce paramètre, reportez-vous à l’applet de commande [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6f369-801">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>
  
<span data-ttu-id="6f369-p196">L’outil supprime les données de réunion uniquement pour les réunions inactives. Les réunions actives (ou réunions en sessions) ne peuvent pas être supprimées.</span><span class="sxs-lookup"><span data-stu-id="6f369-p196">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>
  
<span data-ttu-id="6f369-p197">Cet outil doit être exécuté à partir d’un ordinateur situé dans le même pool que l’utilisateur cible. L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f369-p197">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>
  
### <a name="output"></a><span data-ttu-id="6f369-806">Sortie</span><span class="sxs-lookup"><span data-stu-id="6f369-806">Output</span></span>

<span data-ttu-id="6f369-807">L’outil génère des résultats pour chacune des opérations :</span><span class="sxs-lookup"><span data-stu-id="6f369-807">This tool outputs the results of each of the operations:</span></span>
  
- <span data-ttu-id="6f369-808">Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données des réunions inactives organisées par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-808">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>
    
- <span data-ttu-id="6f369-809">En cas de suppression, l’outil génère la liste des dossiers de données de toutes les réunions pour lesquelles les données seront supprimées.</span><span class="sxs-lookup"><span data-stu-id="6f369-809">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="6f369-810">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f369-810">Requirements</span></span>

<span data-ttu-id="6f369-811">L’outil doit être exécuté dans le même pool qui héberge actuellement l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-811">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>
  
<span data-ttu-id="6f369-812">L’outil doit être exécuté à l’aide de privilèges d’administrateur avec un accès au magasin de fichiers de contenu.</span><span class="sxs-lookup"><span data-stu-id="6f369-812">The tool must be run using administrator privileges with access to the Content File Store.</span></span>
  
### <a name="examples"></a><span data-ttu-id="6f369-813">Exemples</span><span class="sxs-lookup"><span data-stu-id="6f369-813">Examples</span></span>

<span data-ttu-id="6f369-814">Le tableau suivant décrit les paramètres (certains d’entre eux sont utilisés dans les exemples).</span><span class="sxs-lookup"><span data-stu-id="6f369-814">The following table describes the parameters, some of which are used in the examples.</span></span>
  
![Paramètres de l’outil Web Conf Data.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="6f369-p198">L’exemple précédent montre le fonctionnement d’une commande de requête. La sortie d’une telle commande est une liste des dossiers de contenu de réunion affectés par cet outil.</span><span class="sxs-lookup"><span data-stu-id="6f369-p198">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="6f369-p199">L’exemple précédent est une commande de suppression. Cette commande supprime les dossiers des réunions inactives pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f369-p199">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>
  
### <a name="summary"></a><span data-ttu-id="6f369-820">Résumé</span><span class="sxs-lookup"><span data-stu-id="6f369-820">Summary</span></span>

<span data-ttu-id="6f369-821">Cet outil offre aux administrateurs un contrôle plus précis sur les données de réunion de conférence.</span><span class="sxs-lookup"><span data-stu-id="6f369-821">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
  

